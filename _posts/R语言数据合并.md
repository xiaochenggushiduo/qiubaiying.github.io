---
layout:     post
title:      浏览器User-Agent、Cookie   
date:       2019-01-24
author:     余醉
header-img: img/post-bg-internet worm.jpg
catalog: true
tags:
    - 数据处理
    - R
---
## 数据的合并

### 需要的函数

```
cbind(),rbind(),bind_rows()
```

### 准备数据

​    我们先构造一组数据，以便下面的演示

```R
> data1<-data.frame(
+   namea=c("海波","立波","秀波"),
+   value=c("一波","接","一波")
+ )
> data1
  namea value
1  海波  一波
2  立波    接
3  秀波  一波
> data2<-data.frame(
+   nameb=c("柯震东","刘强东","何盛东"),
+   value=c("东去","又","东来")
+ )
> data2
   nameb value
1 柯震东  东去
2 刘强东    又
3 何盛东  东来
```

### 按列合并

```R
> cbind(data1,data2)
  namea value  nameb value
1  海波  一波 柯震东  东去
2  立波    接 刘强东    又
3  秀波  一波 何盛东  东来
```

### 按行合并

​    按列合并是cbind()，那么按行合并自然是rbind()

```R
> rbind(data1,data2)
Error in match.names(clabs, names(xi)) : 名字同原来已有的名字不相对
```

出现了错误，这是因为”namea“ 和”nameb“不同造成的，如果都为"namea" :

```R
> data1<-data.frame(
+   namea=c("海波","立波","秀波"),
+   value=c("一波","接","一波")
+ )
> data1
  namea value
1  海波  一波
2  立波    接
3  秀波  一波
> data2<-data.frame(
+   namea=c("柯震东","刘强东","何盛东"),
+   value=c("东去","又","东来")
+ )
> data2
   namea value
1 柯震东  东去
2 刘强东    又
3 何盛东  东来
> #cbind(data1,data2)
> rbind(data1,data2)
   namea value
1   海波  一波
2   立波    接
3   秀波  一波
4 柯震东  东去
5 刘强东    又
6 何盛东  东来
```

对数据修改后，没有出现错误。如果 不修改数据该怎么做：

​    为了解决这个问题，使用dplyr包中的bind_rows()函数，不要求合并字段的名称必须相同，这个函数会自己做判断。

```R
> library(dplyr)
> dplyr::bind_rows(data1,data2)
  namea value  nameb
1  海波  一波   <NA>
2  立波    接   <NA>
3  秀波  一波   <NA>
4  <NA>  东去 柯震东
5  <NA>    又 刘强东
6  <NA>  东来 何盛东
```

### merge()

```R
merge(x, y, by = intersect(names(x), names(y)),
      by.x = by, by.y = by, all = FALSE, 
      all.x = all, all.y = all,
      sort = TRUE, suffixes = c(".x",".y"),
      incomparables = NULL, ...)
```

  merge函数参数的说明:

    x,y:用于合并的两个数据框
    
    by,by.x,by.y:指定依据哪些行合并数据框,默认值为相同列名的列.
    
    all,all.x,all.y:指定x和y的行是否应该全在输出文件.
    
    sort:by指定的列是否要排序.
    
    suffixes:指定除by外相同列名的后缀.
    
    incomparables:指定by中哪些单元不进行合并.

#### 重新构建数据

```R
data3<-data.frame(
  name = c("波","东","波","波"),
  type = c("秀","震","秀","秀"),
  class = c(10,5,4,11),
  num = c(85,50,90,90)
);data3
data4<-data_frame(
  name = c("波","东"),
  type = c("海","震"),
  class = c(5,5),
  num = c(88,81)
);data4
```

```r
#合并data3和data4
> merge(data3,data4,all =T)
  name type class num
1   波   秀     4  90
2   波   秀    10  85
3   波   秀    11  90
4   波   海     5  88
5   东   震     5  50
6   东   震     5  81
```

```r
#按照name,type,class合并data3.data4
> merge(data3, data4, by =c("name","type","class") , all = T)
  name type class num.x num.y
1   波   秀     4    90    NA
2   波   秀    10    85    NA
3   波   秀    11    90    NA
4   波   海     5    NA    88
5   东   震     5    50    81
```
