---
layout:     post
title:      Objective-C：RunLoop
subtitle:   深入理解RunLoop
date:       2016-11-28
author:     BY
header-img: img/post-bg-ios9-web.jpg
catalog: true
tags:
    - iOS
    - RunLoop
    - Obj-C
---

当前R语言中能做到解析动态网页的有以下几个包（欢迎补充）：

RSelenium（推荐）

Rwebdriver(不很成熟)

seleniumpipes(结合RSelenium更高效)

rdom（高级封装，灵活性不够）

Rcrawler（支持多进程）

webshot（专门用于动态网页截图）

本节以下内容正式分享今日案例，目标是拉勾网

在介绍案例之前，请确保系统具备以下条件：

本地有selenium服务器并添加系统路径；

本地有plantomjs浏览器并添加系统路径；

安装了RSelenium包。

因为涉及到自动化点击操作，Chrome浏览器倒腾一下午硬是在点击环节出故障，找到了原因，因为拉勾网页面很长，而下一页按钮不在默认视窗范围内，使用了js脚本控

制滑动条失败，原因不明，看到有人用firefox浏览器测试成功，我还没有试过，这里改用plantomjs无头浏览器(无需考虑元素是否被窗口遮挡的问题。)

	#！！！这两句是在cmd或者PowerShell中运行的！

	#RSelenium服务未关闭之前，请务必保持该窗口状态！

	###启动selenium服务：

	cd D:\
	java -jar selenium-server-standalone-3.3.1.jar

	##selenium服务器也可以直接在R语言中启动（无弹出窗口）

	system("java -jar \"D:/selenium-server-standalone-2.53.1.jar\"",wait = FALSE,invisible = FALSE)

	#加载包

	library("RSelenium")
	library("magrittr")
	library("xml2")

# 启动服务

	#给plantomjs浏览器伪装UserAgent

	eCap <- list(phantomjs.page.settings.userAgent = "Mozilla/5.0 (Windows NT 6.1; WOW64; rv:29.0) Gecko/20120101 Firefox/29.0")

	### 伪装浏览器UserAgent,为什么即使使用plantomjs这种浏览器也需要伪装UA呢，

	### 因为plantomjs是专门用于web端页面测试的，通常都是在自己的web项目中测试web端功能，直接拿去抓别人的网站，默认的UA就是plantomjs；

	### 这是公然的挑衅！

	### 连接plantomjs服务

	remDr <- remoteDriver(browserName = "phantomjs", extraCapabilities = eCap)

# 构建自动化抓取函数：

#自动化抓取函数：

myresult<-function(remDr,url){

###初始化一个数据框，用作后期收据收集之用！
    
    myresult<-data.frame() 
    
    ###调用后台浏览器（因为是plantomjs这种无头浏览器（headless），所以你看不到弹出窗口）
    
    remDr$open()
    
    ###打开导航页面（也就是直达要抓取的目标网址）
    
    remDr$navigate(url) 
    
    ###初始化一个计时器（用于输出并查看任务进度）
    
    i = 0
    
    while(TRUE){
        
	#计时器开始计数：
        
	i = i+1
        
	#范回当前页面DOM
        
	pagecontent<-remDr$getPageSource()[[1]]
        
	#以下三个字段共用一部分祖先节点，所以临时建立了一个根节点（节省冗余代码）
        
	con_list_item       <- pagecontent %>% read_html() %>% xml_find_all('//ul[@class="item_con_list"]/li')
        
	#职位名称
        
	position.name       <- con_list_item %>% xml_attr("data-positionname") 
        
	#公司名称
        
	position.company    <- con_list_item %>% xml_attr("data-company") 
        
	#职位薪资
        
	position.salary     <- con_list_item %>% xml_attr("data-salary") 
        
	#职位详情链接
        
	position.link       <- pagecontent %>% read_html() %>% xml_find_all('//div[@class="p_top"]/a') %>% xml_attr("href")
        
	#职位经验要求
        
	position.exprience  <- pagecontent %>% read_html() %>% xml_find_all('//div[@class="p_bot"]/div[@class="li_b_l"]') %>% xml_text(trim=TRUE) 
        
	#职位所述行业
        
	position.industry   <- pagecontent %>% read_html() %>% xml_find_all('//div[@class="industry"]') %>% xml_text(trim=TRUE) %>% gsub("[[:space:]\\u00a0]+|\\n", "",.)
        
	#职位福利
        
	position.bonus      <- pagecontent %>% read_html() %>% xml_find_all('//div[@class="list_item_bot"]/div[@class="li_b_l"]') %>% xml_text(trim=TRUE) %>% gsub("[[:space:]\\u00a0]+|\\n", "/",.)
        
	#职位工作环境
        
	position.environment<- pagecontent %>% read_html() %>% xml_find_all('//div[@class="li_b_r"]') %>% xml_text(trim=TRUE) 
        
	#收集数据
        
	mydata<- data.frame(position.name,position.company,position.salary,position.link,position.exprience,position.industry,position.bonus,position.environment,stringsAsFactors = FALSE)
        
	#将本次收集的数据写入之前创建的数据框
        
	myresult<-rbind(myresult,mydata)
        
	#系统休眠0.5~1.5秒
        
	Sys.sleep(runif(1,0.5,1.5))
        
	#判断页面是否到尾部
        
	if ( pagecontent %>% read_html() %>% xml_find_all('//div[@class="page-number"]/span[1]') %>% xml_text() !="30"){
           
	   #如果页面未到尾部，则点击下一页
           
	   remDr$findElement('xpath','//div[@class="pager_container"]/a[last()]')$clickElement()
           
	   #但因当前任务进度
           
	   
	  cat(sprintf("第【%d】页抓取成功",i),sep = "\n")
        
	} else {
            
	    #如果页面到尾部则跳出while循环
            
	    break
        
	}
    
    }
    
    #跳出循环后关闭remDr服务窗口
    
    remDr$close() 
    
    #但因全局任务状态（也即任务结束）
    
    cat("all work is done!!!",sep = "\n")
    
    #返回最终数据
    
    return(myresult)

}

# 运行抓取函数
![预览](https://pic2.zhimg.com/80/v2-82ee0fd56ff0d31765d9a5c334ea7711_hd.jpg)

	url <- "https://www.lagou.com/zhaopin"

	myresult <- myresult(remDr,url)

# 预览

	DT::datatable(myresult) 

![预览](https://pic1.zhimg.com/80/v2-9cfeeed51f127c05b345ee622b6fa838_hd.jpg)
