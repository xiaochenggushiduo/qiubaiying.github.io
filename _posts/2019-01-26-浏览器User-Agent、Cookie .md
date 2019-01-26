一、基础知识篇：  
Http Header之User-Agent  
User Agent中文名为用户代理，是Http协议中的一部分，属于头域的组成部分，User Agent也简称UA。它是一个特殊字符串头，是一种向访问网站提供你所使用的浏览器类型及版本、操作系统及版本、浏览器内核、等信息的标识。通过这个标识，用户所访问的网站可以显示不同的排版从而为用户提供更好的体验或者进行信息统计；例如用手机访问谷歌和电脑访问是不一样的，这些是谷歌根据访问者的UA来判断的。UA可以进行伪装。  
浏览器的UA字串的标准格式：浏览器标识 (操作系统标识; 加密等级标识; 浏览器语言) 渲染引擎标识版本信息。但各个浏览器有所不同。  
1、浏览器标识  
出于兼容及推广等目的，很多浏览器的标识相同，因此浏览器标识并不能说明浏览器的真实版本，真实版本信息在 UA 字串尾部可以找到。

2、操作系统标识

![](//upload-images.jianshu.io/upload_images/1792439-807f719222d4b542.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/546/format/webp)

3、加密等级标识

N: 表示无安全加密  
I: 表示弱安全加密  
U: 表示强安全加密

4、浏览器语言  
在首选项 > 常规 > 语言中指定的语言

5、渲染引擎  
显示浏览器使用的主流渲染引擎有：Gecko、WebKit、KHTML、Presto、Trident、Tasman等，格式为：渲染引擎/版本信息

6、版本信息  
显示浏览器的真实版本信息，格式为：浏览器/版本信息

浏览器User-Agent的详细信息

PC端：

safari 5.1 – MAC  
User-Agent:Mozilla/5.0 (Macintosh; U; Intel Mac OS X 10_6_8; en-us) AppleWebKit/534.50 (KHTML, like Gecko) Version/5.1 Safari/534.50

safari 5.1 – Windows  
User-Agent:Mozilla/5.0 (Windows; U; Windows NT 6.1; en-us) AppleWebKit/534.50 (KHTML, like Gecko) Version/5.1 Safari/534.50

IE 9.0  
User-Agent:Mozilla/5.0 (compatible; MSIE 9.0; Windows NT 6.1; Trident/5.0;

IE 8.0  
User-Agent:Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.0; Trident/4.0)

IE 7.0  
User-Agent:Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)

IE 6.0  
User-Agent: Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)

Firefox 4.0.1 – MAC  
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.6; rv:2.0.1) Gecko/20100101 Firefox/4.0.1

Firefox 4.0.1 – Windows  
User-Agent:Mozilla/5.0 (Windows NT 6.1; rv:2.0.1) Gecko/20100101 Firefox/4.0.1

Opera 11.11 – MAC  
User-Agent:Opera/9.80 (Macintosh; Intel Mac OS X 10.6.8; U; en) Presto/2.8.131 Version/11.11

Opera 11.11 – Windows  
User-Agent:Opera/9.80 (Windows NT 6.1; U; en) Presto/2.8.131 Version/11.11

Chrome 17.0 – MAC  
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_7_0) AppleWebKit/535.11 (KHTML, like Gecko) Chrome/17.0.963.56 Safari/535.11

傲游（Maxthon）  
User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; Maxthon 2.0)

腾讯TT  
User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; TencentTraveler 4.0)

世界之窗（The World） 2.x  
User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1)

世界之窗（The World） 3.x  
User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; The World)

搜狗浏览器 1.x  
User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; Trident/4.0; SE 2.X MetaSr 1.0; SE 2.X MetaSr 1.0; .NET CLR 2.0.50727; SE 2.X MetaSr 1.0)

360浏览器  
User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; 360SE)

Avant  
User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; Avant Browser)

Green Browser  
User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1)

移动设备端：

safari iOS 4.33 – iPhone  
User-Agent:Mozilla/5.0 (iPhone; U; CPU iPhone OS 4_3_3 like Mac OS X; en-us) AppleWebKit/533.17.9 (KHTML, like Gecko) Version/5.0.2 Mobile/8J2 Safari/6533.18.5

safari iOS 4.33 – iPod Touch  
User-Agent:Mozilla/5.0 (iPod; U; CPU iPhone OS 4_3_3 like Mac OS X; en-us) AppleWebKit/533.17.9 (KHTML, like Gecko) Version/5.0.2 Mobile/8J2 Safari/6533.18.5

safari iOS 4.33 – iPad  
User-Agent:Mozilla/5.0 (iPad; U; CPU OS 4_3_3 like Mac OS X; en-us) AppleWebKit/533.17.9 (KHTML, like Gecko) Version/5.0.2 Mobile/8J2 Safari/6533.18.5

Android N1  
User-Agent: Mozilla/5.0 (Linux; U; Android 2.3.7; en-us; Nexus One Build/FRF91) AppleWebKit/533.1 (KHTML, like Gecko) Version/4.0 Mobile Safari/533.1

Android QQ浏览器 For android  
User-Agent: MQQBrowser/26 Mozilla/5.0 (Linux; U; Android 2.3.7; zh-cn; MB200 Build/GRJ22; CyanogenMod-7) AppleWebKit/533.1 (KHTML, like Gecko) Version/4.0 Mobile Safari/533.1

Android Opera Mobile  
User-Agent: Opera/9.80 (Android 2.3.4; Linux; Opera Mobi/build-1107180945; U; en-GB) Presto/2.8.149 Version/11.10

Android Pad Moto Xoom  
User-Agent: Mozilla/5.0 (Linux; U; Android 3.0; en-us; Xoom Build/HRI39) AppleWebKit/534.13 (KHTML, like Gecko) Version/4.0 Safari/534.13

BlackBerry  
User-Agent: Mozilla/5.0 (BlackBerry; U; BlackBerry 9800; en) AppleWebKit/534.1+ (KHTML, like Gecko) Version/6.0.0.337 Mobile Safari/534.1+

WebOS HP Touchpad  
User-Agent: Mozilla/5.0 (hp-tablet; Linux; hpwOS/3.0.0; U; en-US) AppleWebKit/534.6 (KHTML, like Gecko) wOSBrowser/233.70 Safari/534.6 TouchPad/1.0

Nokia N97  
User-Agent: Mozilla/5.0 (SymbianOS/9.4; Series60/5.0 NokiaN97-1/20.0.019; Profile/MIDP-2.1 Configuration/CLDC-1.1) AppleWebKit/525 (KHTML, like Gecko) BrowserNG/7.1.18124

Windows Phone Mango  
User-Agent: Mozilla/5.0 (compatible; MSIE 9.0; Windows Phone OS 7.5; Trident/5.0; IEMobile/9.0; HTC; Titan)

UC无  
User-Agent: UCWEB7.0.2.37/28/999

UC标准  
User-Agent: NOKIA5700/ UCWEB7.0.2.37/28/999

UCOpenwave  
User-Agent: Openwave/ UCWEB7.0.2.37/28/999

UC Opera  
User-Agent: Mozilla/4.0 (compatible; MSIE 6.0; ) Opera/UCWEB7.0.2.37/28/999

二、浏览器识别

1、IE浏览器（以IE 9.0 为例）

PC端：User-Agent:Mozilla/5.0 (compatible; MSIE 9.0; Windows NT 6.1; Trident/5.0;  
移动设备：User-Agent: Mozilla/5.0 (compatible; MSIE 9.0; Windows Phone OS 7.5; Trident/5.0; IEMobile/9.0; HTC; Titan)

由于遨游、世界之窗、360浏览器、腾讯浏览器以及搜狗浏览器、Avant、Green Browser均采用IE的内核，因此IE浏览器判断的标准是”MSIE“字段，MSIE字段后面的数字为版本号，但同时还需要判断不包含”Maxthon“、”The world“、”360SE“、”TencentTraveler“、”SE“、”Avant“等字段（Green Browser没有明显标识）。移动设备还需要判断IEMobile+版本号。

2、360浏览器

PC端：User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; Trident/4.0; InfoPath.2; .NET4.0C; .NET4.0E; .NET CLR 2.0.50727; 360SE)  
移动设备：暂无

360浏览器的判断标准是”360SE”字段，没有版本表示。

3、搜狗浏览器

PC端：User-Agent:Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; Trident/4.0; SE 2.X MetaSr 1.0; SE 2.X MetaSr 1.0; .NET CLR 2.0.50727; SE 2.X MetaSr 1.0)  
移动设备：暂无

搜狗浏览器的判断标准是”SE“、”MetaSr“字段，版本号为SE后面的数字。

4、Chrome

PC端：Mozilla/5.0 (Macintosh; Intel Mac OS X 10_7_0) AppleWebKit/535.11 (KHTML, like Gecko) Chrome/17.0.963.56 Safari/535.11

移动设备：User-Agent: Mozilla/5.0 (Linux; U; Android 2.2.1; zh-cn; HTC_Wildfire_A3333 Build/FRG83D) AppleWebKit/533.1 (KHTML, like Gecko) Version/4.0 Mobile Safari/533.1

PC端chrome浏览器的判断标准是chrome字段，chrome后面的数字为版本号；移动端的chrome浏览器判断”android“、”linux“、”mobile safari“等字段，version后面的数字为版本号。

5、Safari

PC端：User-Agent:Mozilla/5.0 (Macintosh; U; Intel Mac OS X 10_6_8; en-us) AppleWebKit/534.50 (KHTML, like Gecko) Version/5.1 Safari/534.50

移动设备：User-Agent:Mozilla/5.0 (iPhone; U; CPU iPhone OS 4_3_3 like Mac OS X; en-us) AppleWebKit/533.17.9 (KHTML, like Gecko) Version/5.0.2 Mobile/8J2 Safari/6533.18.5

由于Chrome及Nokia’s Series 60 browser也使用WebKit内核，因此Safari浏览器的判断必须是：包含safari字段，同时不包含chrome等信息，确定后”version/“后面的数字即为版本号。在以上条件下包含Mobile字段的即为移动设备上的Safari浏览器。

6、腾讯浏览器

PC端：User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; Trident/4.0; TencentTraveler 4.0; .NET CLR 2.0.50727)

移动设备：User-Agent: MQQBrowser/26 Mozilla/5.0 (Linux; U; Android 2.3.7; zh-cn; MB200 Build/GRJ22; CyanogenMod-7) AppleWebKit/533.1 (KHTML, like Gecko) Version/4.0 Mobile Safari/533.1

腾讯浏览器的判断标准是”TencentTraveler“或者”QQBrowser“，TencentTraveler或QQBrowser后面的数字为版本号。

7、Firefox

PC端：User-Agent:Mozilla/5.0 (Windows NT 6.1; rv:2.0.1) Gecko/20100101 Firefox/4.0.1

移动设备：User-Agent: Mozilla/5.0 (Androdi; Linux armv7l; rv:5.0) Gecko/ Firefox/5.0 fennec/5.0

Firefox的判断标准是Firefox字段，firefox后面的数字为版本号。

8、The world

PC端：User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; The World)

移动设备：暂无

Theworld浏览器的判断标准是”The world“字段，没有标示版本号。

需要注意的是：The world 2.x版本的User-Agent中没有”The world“的字段。

9、遨游

PC端：User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; Maxthon 2.0)

移动设备：暂无

遨游浏览器的判断标准是”Maxthon“，Maxthon后面的数字为版本号。

10、Opera

PC端：User-Agent:Opera/9.80 (Windows NT 6.1; U; en) Presto/2.8.131 Version/11.11

移动设备：User-Agent: Opera/9.80 (Android 2.3.4; Linux; Opera mobi/adr-1107051709; U; zh-cn) Presto/2.8.149 Version/11.10

opera浏览器的判断标准是opera字段，opera字段后面的数字为版本号。

11、UC浏览器

UC Web有多种模式浏览方式，对应的User-Agent为：

UC无  
User-Agent: UCWEB7.0.2.37/28/999

UC标准  
User-Agent: NOKIA5700/ UCWEB7.0.2.37/28/999

UCOpenwave  
User-Agent: Openwave/ UCWEB7.0.2.37/28/999

UC Opera  
User-Agent: Mozilla/4.0 (compatible; MSIE 6.0; ) Opera/UCWEB7.0.2.37/28/999

UC浏览器的判断标准是”UCWEB“字段，UCWEB后面的数字为版本号。

操作系统定向

操作系统定向依赖于各个浏览器在打开页面时所传输的http header信息中的User-Agent，关于User-Agent的说明，请参见Http header之User-Agent。  
User-Agent的详细信息，请参见浏览器User-Agent的详细信息。

我们来了解User-Agent中的不同操作系统的识别方法。

PC端：

![](//upload-images.jianshu.io/upload_images/1792439-cfefe9e45aaaeaa4.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/546/format/webp)

移动设备端：

![](//upload-images.jianshu.io/upload_images/1792439-847dce01027d059a.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/404/format/webp)

用户追踪之基础技术——Cookie  
前言

Cookie是如此的重要，以至于我们后面要讲到的回头客定向、访客频次定向、用户定向等等都需要基于此技术才可以实现，并且我们日常工作中所能见到的第三方监测工具如doubleclick、99click、秒针等也都要利用cookie技术，网站分析工具如GA、百度统计、CNZZ等也需要利用cookie。如果没有Cookie，互联网广告市场将受到巨大打击，尤其对于目前我们谈论的精准广告而言。如果没有Cookie，网站分析也不从做起，遑论优化了。

Cookie是什么

Cookie在英文中是小甜品的意思，但在计算机语言中，Cookie指的是当你浏览某网站时，网站存储在你电脑上的一个小文本文件，伴随着用户请求和页面在 Web 服务器和浏览器之间传递。它记录了你的用户ID，密码、浏览过的网页、停留的时间等信息，用于用户身份的辨别。Cookie通常是以user@domain格式命名的，user是你的本地用户名，domain是所访问的网站的域名。

为什么要Cookie

因为HTTP协议是无状态的，对于一个浏览器发出的请求，服务器无法区分是不是同一个来源，无法知道上一次用户做了什么。所以，需要额外的数据用于维护会话。 Cookie 正是这样的一段随HTTP请求一起被传递的额外数据，用于维护浏览器和服务器的会话。我们可以想象一个场景，你没有登录京东时在京东上购物，选择了3件商品放入购物车，在结算时，京东为什么还能知道这三件商品是什么？没错，是Cookie！

Cookie的工作原理

Cookie利用网页代码中的HTTP头信息，伴随着用户请求和页面在 Web 服务器和浏览器之间传递。例如：当你在浏览器地址栏中键入了Amazon的URL，浏览器会向Amazon发送一个读取网页的请求，并将结果在显示器上显示。在发送之前，该网页在你的电脑上寻找Amazon网站设置的Cookie文件，如果找到，浏览器会把Cookie文件中的数据连同前面输入的URL一同发送到Amazon服务器。服务器收到Cookie数据，就会在他的数据库中检索你的ID，你的购物记录、个人喜好等信息，并记录下新的内容，增加到数据库和Cookie文件中去。如果没有检测到Cookie或者你的Cookie信息与数据库中的信息不符合，则说明你是第一次浏览该网站，服务器的CGI程序将为你创建新的ID信息，并保存到数据库中。（此例子来源于百度百科——Cookie）

关于Cookie的一些知识点

1、Cookie是基于浏览器的，因此当电脑上安装多个浏览器时，服务器会生成多个Cookie。虽然是同一个人，但服务器是识别为多个用户。  
2、Cookie是基于浏览器的，因此当同一台电脑有多个人使用时，服务器也只会生成一个Cookie。虽然是多个人，但服务器会认为是一个用户。  
3、Cookie是无法跨设备进行设置的。比如我们在单位和家里分别使用两台电脑，即使我们使用同一种同一版本的浏览器，我们还是生成了两个Cookie，服务器会认为是两个用户。（PS：现在有些浏览器可以同步数据，比如Chrome、Friefox，可以避免这种问题）

请注意：以上所说的Cooke指的全部是Http Cookie。有一种Cookie——Flash Cookie，可以解决多浏览器的问题。

关于Flash Cookie

FlashCookie是由FlashPlayer控制的客户端共享存储技术，鉴于目前Flash技术的普遍性，几乎所有的网站都采用，所以具有同Http Cookie一样的作用。在技术上，通过使用JavaScript与ActionScript可以将Http Cookie和Flash Cookie进行互通。

Flash cookie的优势在于：  
1、跨浏览器  
不管用户的计算机上安装了多少个浏览器或者浏览器的不同版本，使用Flash Cookie能够使所有的浏览器共用一个Cookie。  
2、不易删除  
所有的浏览器均提供了清除Http Cookie的快捷方式，但Flash Cookie并没有此种方式，并且其保存位置非常隐蔽，网民难以删除。  
3、容量更大  
Flash Cookie可以容纳最多100千字节的数据，而一个标准的HTTP Cookie只有4千字节。

作为网络广告行业的销售人员，了解以上知识就已经绰绰有余了。如果想了解更多，可以接着往下看。

Cookie的数量

1、大多数浏览器支持最大为 4096 字节的 Cookie。因此最好用 Cookie 来存储用户 ID 之类的标识符，用户的详细信息则通过用户 ID从数据库或其他数据源中读取。  
2、浏览器还限制站点可以在用户计算机上存储的 Cookie 的数量。大多数浏览器只允许每个站点存储 20 个 Cookie；当存储更多 Cookie时，最旧的 Cookie 便会被丢弃。有些浏览器还会对它们将接受的来自所有站点的 Cookie 总数作出绝对限制，通常为 300 个。

Cookie的失效时间

1、浏览器的Cookie设置会决定是否保存Cookie数据。如果浏览器不允许Cookie保存，则关掉浏览器后，这些数据就消失。  
2、如果浏览器允许保存Cookie，那么Cookie的时间由服务器的设置决定。Cookie有一个Expires（有效期）属性，这个属性决定了Cookie的保存时间，服务器可以通过设定Expires字段的数值，来改变Cookie的保存时间。如果不设置该属性，那么Cookie只在浏览网页期间有效，关闭浏览器，这些Cookie自动消失，绝大多数网站属于这种情况。通常情况下，Cookie包含Server、Expires、Name、value这几个字段，其中对服务器有用的只是Name和value字段，Expires等字段的内容仅仅是为了告诉浏览器如何处理这些Cookies。

1、  
Cookie的样例

![](//upload-images.jianshu.io/upload_images/1792439-8d2ebf746cb6aeb2.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/597/format/webp)

2、Cookie的内容

![](//upload-images.jianshu.io/upload_images/1792439-f014e28c79163168.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/271/format/webp)

3、从页面代码监测工具看Cookie

![](//upload-images.jianshu.io/upload_images/1792439-ec125a911c636230.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/720/format/webp)

Cookie的位置

1、Http Cookie的位置  
Windows 9X系统 C:WindowsCookies  
Windows NT/2000/XP系统 C:\Documents and Settings\用户名\Cookies  
win7系统 C:\Users*\AppData\Roaming\Microsoft\Windows\Cookies*  
OS X系统 ～/Users/用户名/Library/Cookies

2、Flash Cookie的位置

非Win7系统  
C:\Documents and Settings[username你的用户名]\Application Data\Macromedia\Flash Player#SharedObjects

Win7  
C:\Users[username你的用户名]\Application Data\Macromedia\Flash Player  
其中：Users可能显示为“用户”

OS X系统  
~/Users/用户名/Library/Preferences/Macromedia/Flash Player/#SharedObjects  
~/Users/用户名/Library/Preferences/Macromedia/Flash Player/macromedia.com/support/flashplayer/sys/

第一方Cookie和第三方Cookie

大多数的第三方监测工具和网站分析工具都会采用第三方Cookie。所谓第一方和第三方的说法，是用来确定Cookie的归属的，这个归属是指Cookie中记录的域（domain）。第一方和第三方的唯一区别只是：Cookie中的域名是否和被访问网站的域一样，是就是第一方，否就是第三方。举个例子：如果你访问网站[www.chinawebanalytics.cn](https://link.jianshu.com?t=http://www.chinawebanalytics.cn)的时候，网站在你的电脑上设置了一个Cookie，里面的记录的域名也是[www.chinawebanalytics.cn](https://link.jianshu.com?t=http://www.chinawebanalytics.cn)，那么这个Cookie就是第一方的，归你访问的网站[www.chinawebanalytics.cn](https://link.jianshu.com?t=http://www.chinawebanalytics.cn)所有。而如果你访问网站[www.chinawebanalytics.cn](https://link.jianshu.com?t=http://www.chinawebanalytics.cn)时，在你的计算机中设置的Cookie的域名是[www.abc.com](https://link.jianshu.com?t=http://www.abc.com)，那么这个Cookie就是第三方Cookie，归[www.abc.com](https://link.jianshu.com?t=http://www.abc.com)所有。

所以，第一方Cookie并不一定需要由某个网站自己的服务器给自己建立，别的网站也能为它建立；而且，第一方Cookie也不一定是能由某个网站自己读取的，它完全可能由第三方读取。（以上内容和例子来自于捍卫Cookie——没有Cookie，我们什么都没有了）

二、定向技术介绍：  
语言定向  
1、语言的来源

简单理解，语言指的是用户的浏览器语言，是从浏览器的Http Header的Accept-Language的字段来的。

![](//upload-images.jianshu.io/upload_images/1792439-4eeebefed4e2c866.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/495/format/webp)

2、浏览器的Accept-Language是由浏览器的语言设置所决定的。  

![](//upload-images.jianshu.io/upload_images/1792439-3c785c57604c2e8d.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/640/format/webp)

27492062_7.jpg

3、浏览器的默认语言设置和浏览器语言无关，默认继承操作系统的语言。**  
浏览器定向  
浏览器定向同样需要依赖于各个浏览器在打开页面时所传输的Http header信息中的User-Agent，关于User-Agent的说明，请参见[Http header之User-Agent](https://link.jianshu.com?t=http://www.iamniu.com/2012/02/17/http-header%E4%B9%8Buser-agent/)。User-Agent的详细信息，请参见[浏览器User-Agent的详细信息](https://link.jianshu.com?t=http://www.iamniu.com/2012/02/23/%E6%B5%8F%E8%A7%88%E5%99%A8user-agent%E7%9A%84%E8%AF%A6%E7%BB%86%E4%BF%A1%E6%81%AF/)。  
我们来了解User-Agent中浏览器及版本识别的方法：  
一、浏览器的使用率说明

![](//upload-images.jianshu.io/upload_images/1792439-98d615a95c324f33.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/479/format/webp)

27492062_8.jpg

我们针对以上的浏览器进行说明，另外再针对移动设备上的几款浏览器进行说明。  
**二、浏览器识别**  
**1、IE浏览器（以IE 9.0 为例）**  
PC端：User-Agent:Mozilla/5.0 (compatible; MSIE 9.0; Windows NT 6.1; Trident/5.0;移动设备：User-Agent: Mozilla/5.0 (compatible; MSIE 9.0; Windows Phone OS 7.5; Trident/5.0; IEMobile/9.0; HTC; Titan)  
由于遨游、世界之窗、360浏览器、腾讯浏览器以及搜狗浏览器、Avant、Green Browser均采用IE的内核，因此IE浏览器判断的标准是”MSIE“字段，MSIE字段后面的数字为版本号，但同时还需要判断不包含”Maxthon“、”The world“、”360SE“、”TencentTraveler“、”SE“、”Avant“等字段（Green Browser没有明显标识）。移动设备还需要判断IEMobile+版本号。  
**2、360浏览器**  
PC端：User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; Trident/4.0; InfoPath.2; .NET4.0C; .NET4.0E; .NET CLR 2.0.50727; 360SE)移动设备：暂无  
360浏览器的判断标准是”360SE”字段，没有版本表示。  
**3、搜狗浏览器**  
PC端：User-Agent:Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; Trident/4.0; SE 2.X MetaSr 1.0; SE 2.X MetaSr 1.0; .NET CLR 2.0.50727; SE 2.X MetaSr 1.0)移动设备：暂无  
搜狗浏览器的判断标准是”SE“、”MetaSr“字段，版本号为SE后面的数字。  
**4、Chrome**  
PC端：Mozilla/5.0 (Macintosh; Intel Mac OS X 10_7_0) AppleWebKit/535.11 (KHTML, like Gecko) Chrome/17.0.963.56 Safari/535.11  
移动设备：User-Agent: Mozilla/5.0 (Linux; U; Android 2.2.1; zh-cn; HTC_Wildfire_A3333 Build/FRG83D) AppleWebKit/533.1 (KHTML, like Gecko) Version/4.0 Mobile Safari/533.1  
PC端chrome浏览器的判断标准是chrome字段，chrome后面的数字为版本号；移动端的chrome浏览器判断”android“、”linux“、”mobile safari“等字段，version后面的数字为版本号。  
**5、Safari**  
PC端：User-Agent:Mozilla/5.0 (Macintosh; U; Intel Mac OS X 10_6_8; en-us) AppleWebKit/534.50 (KHTML, like Gecko) Version/5.1 Safari/534.50  
移动设备：User-Agent:Mozilla/5.0 (iPhone; U; CPU iPhone OS 4_3_3 like Mac OS X; en-us) AppleWebKit/533.17.9 (KHTML, like Gecko) Version/5.0.2 Mobile/8J2 Safari/6533.18.5  
由于Chrome及Nokia’s Series 60 browser也使用WebKit内核，因此Safari浏览器的判断必须是：包含safari字段，同时不包含chrome等信息，确定后”version/“后面的数字即为版本号。在以上条件下包含Mobile字段的即为移动设备上的Safari浏览器。  
**6、腾讯浏览器**  
PC端：User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; Trident/4.0; TencentTraveler 4.0; .NET CLR 2.0.50727)  
移动设备：User-Agent: MQQBrowser/26 Mozilla/5.0 (Linux; U; Android 2.3.7; zh-cn; MB200 Build/GRJ22; CyanogenMod-7) AppleWebKit/533.1 (KHTML, like Gecko) Version/4.0 Mobile Safari/533.1  
腾讯浏览器的判断标准是”TencentTraveler“或者”QQBrowser“，TencentTraveler或QQBrowser后面的数字为版本号。  
**7、Firefox**  
PC端：User-Agent:Mozilla/5.0 (Windows NT 6.1; rv:2.0.1) Gecko/20100101 Firefox/4.0.1  
移动设备：User-Agent: Mozilla/5.0 (Androdi; Linux armv7l; rv:5.0) Gecko/ Firefox/5.0 fennec/5.0  
Firefox的判断标准是Firefox字段，firefox后面的数字为版本号。  
**8、The world**  
PC端：User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; The World)  
移动设备：暂无  
Theworld浏览器的判断标准是”The world“字段，没有标示版本号。  
需要注意的是：The world 2.x版本的User-Agent中没有”The world“的字段。  
**9、遨游**  
PC端：User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; Maxthon 2.0)  
移动设备：暂无  
遨游浏览器的判断标准是”Maxthon“，Maxthon后面的数字为版本号。  
**10、Opera**  
PC端：User-Agent:Opera/9.80 (Windows NT 6.1; U; en) Presto/2.8.131 Version/11.11  
移动设备：User-Agent: **O**pera/9.80 (Android 2.3.4; Linux; Opera mobi/adr-1107051709; U; zh-cn) Presto/2.8.149 Version/11.10  
opera浏览器的判断标准是opera字段，opera字段后面的数字为版本号。  
**11、UC浏览器**  
UC Web有多种模式浏览方式，对应的User-Agent为：  
UC无User-Agent: UCWEB7.0.2.37/28/999  
UC标准User-Agent: NOKIA5700/ UCWEB7.0.2.37/28/999  
UCOpenwaveUser-Agent: Openwave/ UCWEB7.0.2.37/28/999  
UC OperaUser-Agent: Mozilla/4.0 (compatible; MSIE 6.0; ) Opera/UCWEB7.0.2.37/28/999  
UC浏览器的判断标准是”UCWEB“字段，UCWEB后面的数字为版本号。  
操作系统定向  
操作系统定向依赖于各个浏览器在打开页面时所传输的http header信息中的User-Agent，关于User-Agent的说明，请参见[Http header之User-Agent](https://link.jianshu.com?t=http://www.iamniu.com/2012/02/17/http-header%E4%B9%8Buser-agent/)。User-Agent的详细信息，请参见[浏览器User-Agent的详细信息](https://link.jianshu.com?t=http://www.iamniu.com/2012/02/23/%E6%B5%8F%E8%A7%88%E5%99%A8user-agent%E7%9A%84%E8%AF%A6%E7%BB%86%E4%BF%A1%E6%81%AF/)。  
我们来了解User-Agent中的不同操作系统的识别方法。

PC端：

![](//upload-images.jianshu.io/upload_images/1792439-c1d80182db3a3c0d.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/546/format/webp)

27492062_9.jpg

移动设备端：  

![](//upload-images.jianshu.io/upload_images/1792439-cc8499f0f2ea192b.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/404/format/webp)

27492062_10.jpg

**以下为原文：**  
截止今天，关于精准广告定向技术的介绍已经全部写完。介绍的写作初衷是总结自己的知识，将知识从片段的、隐形的转化为可以向别人讲述、能够给人帮助的。在总结的过程中自己也提升了很多，同时希望这些内容能够切实的给刚进入这个行业的同学们以帮助。  
**一、基础知识篇：**  
Http Header之User-Agent  
User Agent中文名为用户代理，是Http协议中的一部分，属于头域的组成部分，User Agent也简称UA。它是一个特殊字符串头，是一种向访问网站提供你所使用的浏览器类型及版本、操作系统及版本、浏览器内核、等信息的标识。通过这个标识，用户所访问的网站可以显示不同的排版从而为用户提供更好的体验或者进行信息统计；例如用手机访问谷歌和电脑访问是不一样的，这些是谷歌根据访问者的UA来判断的。UA可以进行伪装。  
浏览器的UA字串的标准格式：浏览器标识 (操作系统标识; 加密等级标识; 浏览器语言) 渲染引擎标识版本信息。但各个浏览器有所不同。  
字串说明：  
**1、浏览器标识**出于兼容及推广等目的，很多浏览器的标识相同，因此浏览器标识并不能说明浏览器的真实版本，真实版本信息在 UA 字串尾部可以找到。  
**2、操作系统标识**  

![img1_the-user-agent-introduction](http://image55.360doc.com/DownloadImg/2012/10/1221/27492062_1.jpg)

img1_the-user-agent-introduction

**3、加密等级标识**N: 表示无安全加密I: 表示弱安全加密U: 表示强安全加密  
**4、浏览器语言**在首选项 > 常规 > 语言中指定的语言  
**5、渲染引擎**显示浏览器使用的主流渲染引擎有：Gecko、WebKit、KHTML、Presto、Trident、Tasman等，格式为：渲染引擎/版本信息  
**6、版本信息**显示浏览器的真实版本信息，格式为：浏览器/版本信息  
注：1、在广告定向设定中，浏览器定向和操作系统定向均是针对User-Agent中的信息进行定向。2、欲了解更多的User-Agent信息，请参考User-agent 字串史  
浏览器User-Agent的详细信息  
PC端：  
safari 5.1 – MACUser-Agent:Mozilla/5.0 (Macintosh; U; Intel Mac OS X 10_6_8; en-us) AppleWebKit/534.50 (KHTML, like Gecko) Version/5.1 Safari/534.50  
safari 5.1 – WindowsUser-Agent:Mozilla/5.0 (Windows; U; Windows NT 6.1; en-us) AppleWebKit/534.50 (KHTML, like Gecko) Version/5.1 Safari/534.50  
IE 9.0User-Agent:Mozilla/5.0 (compatible; MSIE 9.0; Windows NT 6.1; Trident/5.0;  
IE 8.0User-Agent:Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.0; Trident/4.0)  
IE 7.0User-Agent:Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)  
IE 6.0User-Agent: Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)  
Firefox 4.0.1 – MACUser-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.6; rv:2.0.1) Gecko/20100101 Firefox/4.0.1  
Firefox 4.0.1 – WindowsUser-Agent:Mozilla/5.0 (Windows NT 6.1; rv:2.0.1) Gecko/20100101 Firefox/4.0.1  
Opera 11.11 – MACUser-Agent:Opera/9.80 (Macintosh; Intel Mac OS X 10.6.8; U; en) Presto/2.8.131 Version/11.11  
Opera 11.11 – WindowsUser-Agent:Opera/9.80 (Windows NT 6.1; U; en) Presto/2.8.131 Version/11.11  
Chrome 17.0 – MACUser-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_7_0) AppleWebKit/535.11 (KHTML, like Gecko) Chrome/17.0.963.56 Safari/535.11  
傲游（Maxthon）User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; Maxthon 2.0)  
腾讯TTUser-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; TencentTraveler 4.0)  
世界之窗（The World） 2.xUser-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1)  
世界之窗（The World） 3.xUser-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; The World)  
搜狗浏览器 1.xUser-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; Trident/4.0; SE 2.X MetaSr 1.0; SE 2.X MetaSr 1.0; .NET CLR 2.0.50727; SE 2.X MetaSr 1.0)  
360浏览器User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; 360SE)  
AvantUser-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; Avant Browser)  
Green BrowserUser-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1)  
移动设备端：  
safari iOS 4.33 – iPhoneUser-Agent:Mozilla/5.0 (iPhone; U; CPU iPhone OS 4_3_3 like Mac OS X; en-us) AppleWebKit/533.17.9 (KHTML, like Gecko) Version/5.0.2 Mobile/8J2 Safari/6533.18.5  
safari iOS 4.33 – iPod TouchUser-Agent:Mozilla/5.0 (iPod; U; CPU iPhone OS 4_3_3 like Mac OS X; en-us) AppleWebKit/533.17.9 (KHTML, like Gecko) Version/5.0.2 Mobile/8J2 Safari/6533.18.5  
safari iOS 4.33 – iPadUser-Agent:Mozilla/5.0 (iPad; U; CPU OS 4_3_3 like Mac OS X; en-us) AppleWebKit/533.17.9 (KHTML, like Gecko) Version/5.0.2 Mobile/8J2 Safari/6533.18.5  
Android N1User-Agent: Mozilla/5.0 (Linux; U; Android 2.3.7; en-us; Nexus One Build/FRF91) AppleWebKit/533.1 (KHTML, like Gecko) Version/4.0 Mobile Safari/533.1  
Android QQ浏览器 For androidUser-Agent: MQQBrowser/26 Mozilla/5.0 (Linux; U; Android 2.3.7; zh-cn; MB200 Build/GRJ22; CyanogenMod-7) AppleWebKit/533.1 (KHTML, like Gecko) Version/4.0 Mobile Safari/533.1  
Android Opera MobileUser-Agent: Opera/9.80 (Android 2.3.4; Linux; Opera Mobi/build-1107180945; U; en-GB) Presto/2.8.149 Version/11.10  
Android Pad Moto XoomUser-Agent: Mozilla/5.0 (Linux; U; Android 3.0; en-us; Xoom Build/HRI39) AppleWebKit/534.13 (KHTML, like Gecko) Version/4.0 Safari/534.13  
BlackBerryUser-Agent: Mozilla/5.0 (BlackBerry; U; BlackBerry 9800; en) AppleWebKit/534.1+ (KHTML, like Gecko) Version/6.0.0.337 Mobile Safari/534.1+  
WebOS HP TouchpadUser-Agent: Mozilla/5.0 (hp-tablet; Linux; hpwOS/3.0.0; U; en-US) AppleWebKit/534.6 (KHTML, like Gecko) wOSBrowser/233.70 Safari/534.6 TouchPad/1.0  
Nokia N97User-Agent: Mozilla/5.0 (SymbianOS/9.4; Series60/5.0 NokiaN97-1/20.0.019; Profile/MIDP-2.1 Configuration/CLDC-1.1) AppleWebKit/525 (KHTML, like Gecko) BrowserNG/7.1.18124  
Windows Phone MangoUser-Agent: Mozilla/5.0 (compatible; MSIE 9.0; Windows Phone OS 7.5; Trident/5.0; IEMobile/9.0; HTC; Titan)  
UC无User-Agent: UCWEB7.0.2.37/28/999  
UC标准User-Agent: NOKIA5700/ UCWEB7.0.2.37/28/999  
UCOpenwaveUser-Agent: Openwave/ UCWEB7.0.2.37/28/999  
UC OperaUser-Agent: Mozilla/4.0 (compatible; MSIE 6.0; ) Opera/UCWEB7.0.2.37/28/999  
用户追踪之基础技术——Cookie  
**前言**  
Cookie是如此的重要，以至于我们后面要讲到的回头客定向、访客频次定向、用户定向等等都需要基于此技术才可以实现，并且我们日常工作中所能见到的第三方监测工具如doubleclick、99click、秒针等也都要利用cookie技术，网站分析工具如GA、百度统计、CNZZ等也需要利用cookie。如果没有Cookie，互联网广告市场将受到巨大打击，尤其对于目前我们谈论的精准广告而言。如果没有Cookie，网站分析也不从做起，遑论优化了。  

![img2_cookie](http://image55.360doc.com/DownloadImg/2012/10/1221/27492062_2.jpg)

img2_cookie

**Cookie是什么**  
Cookie在英文中是小甜品的意思，但在计算机语言中，Cookie指的是当你浏览某网站时，网站存储在你电脑上的一个小文本文件，伴随着用户请求和页面在 Web 服务器和浏览器之间传递。它记录了你的用户ID，密码、浏览过的网页、停留的时间等信息，用于用户身份的辨别。Cookie通常是以user@domain格式命名的，user是你的本地用户名，domain是所访问的网站的域名。  
**为什么要Cookie**  
因为HTTP协议是无状态的，对于一个浏览器发出的请求，服务器无法区分是不是同一个来源，无法知道上一次用户做了什么。所以，需要额外的数据用于维护会话。 Cookie 正是这样的一段随HTTP请求一起被传递的额外数据，用于维护浏览器和服务器的会话。我们可以想象一个场景，你没有登录京东时在京东上购物，选择了3件商品放入购物车，在结算时，京东为什么还能知道这三件商品是什么？没错，是Cookie！  
**Cookie的工作原理**  
Cookie利用网页代码中的HTTP头信息，伴随着用户请求和页面在 Web 服务器和浏览器之间传递。例如：当你在浏览器地址栏中键入了Amazon的URL，浏览器会向Amazon发送一个读取网页的请求，并将结果在显示器上显示。在发送之前，该网页在你的电脑上寻找Amazon网站设置的Cookie文件，如果找到，浏览器会把Cookie文件中的数据连同前面输入的URL一同发送到Amazon服务器。服务器收到Cookie数据，就会在他的数据库中检索你的ID，你的购物记录、个人喜好等信息，并记录下新的内容，增加到数据库和Cookie文件中去。如果没有检测到Cookie或者你的Cookie信息与数据库中的信息不符合，则说明你是第一次浏览该网站，服务器的CGI程序将为你创建新的ID信息，并保存到数据库中。（此例子来源于百度百科——Cookie）  
**关于Cookie的一些知识点**  
1、Cookie是基于浏览器的，因此当电脑上安装多个浏览器时，服务器会生成多个Cookie。虽然是同一个人，但服务器是识别为多个用户。2、Cookie是基于浏览器的，因此当同一台电脑有多个人使用时，服务器也只会生成一个Cookie。虽然是多个人，但服务器会认为是一个用户。3、Cookie是无法跨设备进行设置的。比如我们在单位和家里分别使用两台电脑，即使我们使用同一种同一版本的浏览器，我们还是生成了两个Cookie，服务器会认为是两个用户。（PS：现在有些浏览器可以同步数据，比如Chrome、Friefox，可以避免这种问题）  
请注意：以上所说的Cooke指的全部是Http Cookie。有一种Cookie——Flash Cookie，可以解决多浏览器的问题。  
**关于Flash Cookie**  
FlashCookie是由FlashPlayer控制的客户端共享存储技术，鉴于目前Flash技术的普遍性，几乎所有的网站都采用，所以具有同Http Cookie一样的作用。在技术上，通过使用JavaScript与ActionScript可以将Http Cookie和Flash Cookie进行互通。  
Flash cookie的优势在于：1、跨浏览器不管用户的计算机上安装了多少个浏览器或者浏览器的不同版本，使用Flash Cookie能够使所有的浏览器共用一个Cookie。2、不易删除所有的浏览器均提供了清除Http Cookie的快捷方式，但Flash Cookie并没有此种方式，并且其保存位置非常隐蔽，网民难以删除。3、容量更大Flash Cookie可以容纳最多100千字节的数据，而一个标准的HTTP Cookie只有4千字节。  
作为网络广告行业的销售人员，了解以上知识就已经绰绰有余了。如果想了解更多，可以接着往下看。  
**Cookie的数量**  
1、大多数浏览器支持最大为 4096 字节的 Cookie。因此最好用 Cookie 来存储用户 ID 之类的标识符，用户的详细信息则通过用户 ID从数据库或其他数据源中读取。2、浏览器还限制站点可以在用户计算机上存储的 Cookie 的数量。大多数浏览器只允许每个站点存储 20 个 Cookie；当存储更多 Cookie时，最旧的 Cookie 便会被丢弃。有些浏览器还会对它们将接受的来自所有站点的 Cookie 总数作出绝对限制，通常为 300 个。  
**Cookie的失效时间**  
1、浏览器的Cookie设置会决定是否保存Cookie数据。如果浏览器不允许Cookie保存，则关掉浏览器后，这些数据就消失。2、如果浏览器允许保存Cookie，那么Cookie的时间由服务器的设置决定。Cookie有一个Expires（有效期）属性，这个属性决定了Cookie的保存时间，服务器可以通过设定Expires字段的数值，来改变Cookie的保存时间。如果不设置该属性，那么Cookie只在浏览网页期间有效，关闭浏览器，这些Cookie自动消失，绝大多数网站属于这种情况。通常情况下，Cookie包含Server、Expires、Name、value这几个字段，其中对服务器有用的只是Name和value字段，Expires等字段的内容仅仅是为了告诉浏览器如何处理这些Cookies。  
**Cookie的样例**  
1、Cookie的名称

![img3_cookies](http://image55.360doc.com/DownloadImg/2012/10/1221/27492062_3.jpg)

img3_cookies

2、Cookie的内容

![img4_cookies](http://image55.360doc.com/DownloadImg/2012/10/1221/27492062_4.jpg)

img4_cookies

3、从页面代码监测工具看Cookie

![img5_cookies](http://image55.360doc.com/DownloadImg/2012/10/1221/27492062_5.jpg)

img5_cookies

**Cookie的位置**  
1、Http Cookie的位置Windows 9X系统 C:WindowsCookiesWindows NT/2000/XP系统 C:\Documents and Settings\用户名\Cookieswin7系统 C:\Users*\AppData\Roaming\Microsoft\Windows\Cookies*OS X系统 ～/Users/用户名/Library/Cookies  
2、Flash Cookie的位置  
非Win7系统C:\Documents and Settings[username你的用户名]\Application Data\Macromedia\Flash Player#SharedObjects  
Win7C:\Users[username你的用户名]\Application Data\Macromedia\Flash Player其中：Users可能显示为“用户”  
OS X系统~/Users/用户名/Library/Preferences/Macromedia/Flash Player/#SharedObjects~/Users/用户名/Library/Preferences/Macromedia/Flash Player/macromedia.com/support/flashplayer/sys/  
**第一方Cookie和第三方Cookie**  
大多数的第三方监测工具和网站分析工具都会采用第三方Cookie。所谓第一方和第三方的说法，是用来确定Cookie的归属的，这个归属是指Cookie中记录的域（domain）。第一方和第三方的唯一区别只是：Cookie中的域名是否和被访问网站的域一样，是就是第一方，否就是第三方。举个例子：如果你访问网站[www.chinawebanalytics.cn](https://link.jianshu.com?t=http://www.chinawebanalytics.cn)的时候，网站在你的电脑上设置了一个Cookie，里面的记录的域名也是[www.chinawebanalytics.cn](https://link.jianshu.com?t=http://www.chinawebanalytics.cn)，那么这个Cookie就是第一方的，归你访问的网站[www.chinawebanalytics.cn](https://link.jianshu.com?t=http://www.chinawebanalytics.cn)所有。而如果你访问网站[www.chinawebanalytics.cn](https://link.jianshu.com?t=http://www.chinawebanalytics.cn)时，在你的计算机中设置的Cookie的域名是[www.abc.com](https://link.jianshu.com?t=http://www.abc.com)，那么这个Cookie就是第三方Cookie，归[www.abc.com](https://link.jianshu.com?t=http://www.abc.com)所有。  
所以，第一方Cookie并不一定需要由某个网站自己的服务器给自己建立，别的网站也能为它建立；而且，第一方Cookie也不一定是能由某个网站自己读取的，它完全可能由第三方读取。（以上内容和例子来自于捍卫Cookie——没有Cookie，我们什么都没有了）  
**二、定向技术介绍：**  
语言定向  
**1、语言的来源**  
简单理解，语言指的是用户的浏览器语言，是从浏览器的Http Header的Accept-Language的字段来的。  

![language01](http://image55.360doc.com/DownloadImg/2012/10/1221/27492062_6.jpg)

language01

**2、浏览器的Accept-Language是由浏览器的语言设置所决定的。**  

![language02](http://image55.360doc.com/DownloadImg/2012/10/1221/27492062_7.jpg)

language02

**3、浏览器的默认语言设置和浏览器语言无关，默认继承操作系统的语言。**  
浏览器定向  
浏览器定向同样需要依赖于各个浏览器在打开页面时所传输的Http header信息中的User-Agent，关于User-Agent的说明，请参见[Http header之User-Agent](https://link.jianshu.com?t=http://www.iamniu.com/2012/02/17/http-header%E4%B9%8Buser-agent/)。User-Agent的详细信息，请参见[浏览器User-Agent的详细信息](https://link.jianshu.com?t=http://www.iamniu.com/2012/02/23/%E6%B5%8F%E8%A7%88%E5%99%A8user-agent%E7%9A%84%E8%AF%A6%E7%BB%86%E4%BF%A1%E6%81%AF/)。  
我们来了解User-Agent中浏览器及版本识别的方法：  
**一、浏览器的使用率说明：**  

![browser01](http://image55.360doc.com/DownloadImg/2012/10/1221/27492062_8.jpg)

browser01

——数据来源于CNZZ数据中心  
我们针对以上的浏览器进行说明，另外再针对移动设备上的几款浏览器进行说明。  
**二、浏览器识别**  
**1、IE浏览器（以IE 9.0 为例）**  
PC端：User-Agent:Mozilla/5.0 (compatible; MSIE 9.0; Windows NT 6.1; Trident/5.0;移动设备：User-Agent: Mozilla/5.0 (compatible; MSIE 9.0; Windows Phone OS 7.5; Trident/5.0; IEMobile/9.0; HTC; Titan)  
由于遨游、世界之窗、360浏览器、腾讯浏览器以及搜狗浏览器、Avant、Green Browser均采用IE的内核，因此IE浏览器判断的标准是”MSIE“字段，MSIE字段后面的数字为版本号，但同时还需要判断不包含”Maxthon“、”The world“、”360SE“、”TencentTraveler“、”SE“、”Avant“等字段（Green Browser没有明显标识）。移动设备还需要判断IEMobile+版本号。  
**2、360浏览器**  
PC端：User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; Trident/4.0; InfoPath.2; .NET4.0C; .NET4.0E; .NET CLR 2.0.50727; 360SE)移动设备：暂无  
360浏览器的判断标准是”360SE”字段，没有版本表示。  
**3、搜狗浏览器**  
PC端：User-Agent:Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; Trident/4.0; SE 2.X MetaSr 1.0; SE 2.X MetaSr 1.0; .NET CLR 2.0.50727; SE 2.X MetaSr 1.0)移动设备：暂无  
搜狗浏览器的判断标准是”SE“、”MetaSr“字段，版本号为SE后面的数字。  
**4、Chrome**  
PC端：Mozilla/5.0 (Macintosh; Intel Mac OS X 10_7_0) AppleWebKit/535.11 (KHTML, like Gecko) Chrome/17.0.963.56 Safari/535.11  
移动设备：User-Agent: Mozilla/5.0 (Linux; U; Android 2.2.1; zh-cn; HTC_Wildfire_A3333 Build/FRG83D) AppleWebKit/533.1 (KHTML, like Gecko) Version/4.0 Mobile Safari/533.1  
PC端chrome浏览器的判断标准是chrome字段，chrome后面的数字为版本号；移动端的chrome浏览器判断”android“、”linux“、”mobile safari“等字段，version后面的数字为版本号。  
**5、Safari**  
PC端：User-Agent:Mozilla/5.0 (Macintosh; U; Intel Mac OS X 10_6_8; en-us) AppleWebKit/534.50 (KHTML, like Gecko) Version/5.1 Safari/534.50  
移动设备：User-Agent:Mozilla/5.0 (iPhone; U; CPU iPhone OS 4_3_3 like Mac OS X; en-us) AppleWebKit/533.17.9 (KHTML, like Gecko) Version/5.0.2 Mobile/8J2 Safari/6533.18.5  
由于Chrome及Nokia’s Series 60 browser也使用WebKit内核，因此Safari浏览器的判断必须是：包含safari字段，同时不包含chrome等信息，确定后”version/“后面的数字即为版本号。在以上条件下包含Mobile字段的即为移动设备上的Safari浏览器。  
**6、腾讯浏览器**  
PC端：User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; Trident/4.0; TencentTraveler 4.0; .NET CLR 2.0.50727)  
移动设备：User-Agent: MQQBrowser/26 Mozilla/5.0 (Linux; U; Android 2.3.7; zh-cn; MB200 Build/GRJ22; CyanogenMod-7) AppleWebKit/533.1 (KHTML, like Gecko) Version/4.0 Mobile Safari/533.1  
腾讯浏览器的判断标准是”TencentTraveler“或者”QQBrowser“，TencentTraveler或QQBrowser后面的数字为版本号。  
**7、Firefox**  
PC端：User-Agent:Mozilla/5.0 (Windows NT 6.1; rv:2.0.1) Gecko/20100101 Firefox/4.0.1  
移动设备：User-Agent: Mozilla/5.0 (Androdi; Linux armv7l; rv:5.0) Gecko/ Firefox/5.0 fennec/5.0  
Firefox的判断标准是Firefox字段，firefox后面的数字为版本号。  
**8、The world**  
PC端：User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; The World)  
移动设备：暂无  
Theworld浏览器的判断标准是”The world“字段，没有标示版本号。  
需要注意的是：The world 2.x版本的User-Agent中没有”The world“的字段。  
**9、遨游**  
PC端：User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; Maxthon 2.0)  
移动设备：暂无  
遨游浏览器的判断标准是”Maxthon“，Maxthon后面的数字为版本号。  
**10、Opera**  
PC端：User-Agent:Opera/9.80 (Windows NT 6.1; U; en) Presto/2.8.131 Version/11.11  
移动设备：User-Agent: **O**pera/9.80 (Android 2.3.4; Linux; Opera mobi/adr-1107051709; U; zh-cn) Presto/2.8.149 Version/11.10  
opera浏览器的判断标准是opera字段，opera字段后面的数字为版本号。  
**11、UC浏览器**  
UC Web有多种模式浏览方式，对应的User-Agent为：  
UC无User-Agent: UCWEB7.0.2.37/28/999  
UC标准User-Agent: NOKIA5700/ UCWEB7.0.2.37/28/999  
UCOpenwaveUser-Agent: Openwave/ UCWEB7.0.2.37/28/999  
UC OperaUser-Agent: Mozilla/4.0 (compatible; MSIE 6.0; ) Opera/UCWEB7.0.2.37/28/999  
UC浏览器的判断标准是”UCWEB“字段，UCWEB后面的数字为版本号。  
操作系统定向  
操作系统定向依赖于各个浏览器在打开页面时所传输的http header信息中的User-Agent，关于User-Agent的说明，请参见[Http header之User-Agent](https://link.jianshu.com?t=http://www.iamniu.com/2012/02/17/http-header%E4%B9%8Buser-agent/)。User-Agent的详细信息，请参见[浏览器User-Agent的详细信息](https://link.jianshu.com?t=http://www.iamniu.com/2012/02/23/%E6%B5%8F%E8%A7%88%E5%99%A8user-agent%E7%9A%84%E8%AF%A6%E7%BB%86%E4%BF%A1%E6%81%AF/)。  
我们来了解User-Agent中的不同操作系统的识别方法。  
**PC端：**  

![operating-system-orientation01](http://image55.360doc.com/DownloadImg/2012/10/1221/27492062_9.jpg)

operating-system-orientation01

**移动设备端：**  

![operating-system-orientation02](http://image55.360doc.com/DownloadImg/2012/10/1221/27492062_10.jpg)

operating-system-orientation02

地域定向  
地域定向依赖于对IP地址的识别，而IP协议是互联网的基础协议，因此从网络诞生的第一天起，地域定向就可以被使用了。  
欲详细了解IP协议，请查看百度百科——[TCP/IP协议](https://link.jianshu.com?t=http://baike.baidu.com/view/7649.htm)。有关IP地址的详细信息，请查看百度百科——[IP](https://link.jianshu.com?t=http://baike.baidu.com/view/8370.htm)。  
**通俗来讲，IP地址就是互联网上的门牌号，接入互联网的所有主机就是我们的一个个住所，其中有个人的，有单位的。个人住所一家一个门牌号，单位的多家公用一个门牌号，由于规划的原因，有的住所会有多个门牌号，也是规划的原因，门牌号有时会发生变化。IP地址也有此特点，一台主机可以具有多个IP地址，而多台主机也可以公用一个IP地址。**  
**现实中，不管如何规划，通过门牌号我们能找到我们要找的住所，也能清楚住所所在的具体位置。同样，在网络中，通过IP地址我们也能定位到我们所需要找的主机，并且清楚知道主机所在的地理位置。这样我们就能进行广告的地域定向了。**  
从技术层面讲，地域定向的工作逻辑是：  
当一个请求发送给服务器时，服务器根据配置（以Apache为例，在[Apache Httpd](https://link.jianshu.com?t=http://www.php100.com/html/webkaifa/apache/2009/0418/1192.html)中进行配置）记录下请求的相关数据，组成日志文件，日志基本会包括请求时间、请求IP、请求的URL、请求的Reffer、请求的User-Agent以及其他信息，将收集到的IP地址与已有的IP数据库进行比对，即可以确定请求者的地理位置了，比如山西省太原市。  
国内目前免费的IP库有 [QQ IP数据库 纯真版](https://link.jianshu.com?t=http://www.crsky.com/soft/2611.html)，即我们通常所说的纯真IP库，收集了包括中国电信、中国网通、长城宽带、网通宽带、聚友宽带等 ISP 的最新准确 IP 地址数据，包括最全的网吧数据。IP数据库每5天更新一次，企业可以在此基础上修正后使用。  
目前的地域定向更多的是针对省份以及地级城市的定向，针对县级市或者区级的定向基本上都十分不准确。  
回头客定向  
随着电商网站的火爆，从2010年开始，互联网广告行业出现了一种定向方式——回头客定向。回头客定向是随着精准理念的发展而提出来的。顾名思义，回头客定向是指针对到达过广告主网站的某一个点的用户或者发生过某一个行为的用户进行定向。  
从概念中，我们可以发现回头客定向的三个基本点：**1、到达过；2、某一个点或某个行为；3、定向投放。这三点也是回头客定向和人群定向的区别之处。**  
*从营销的角度讲，针对不同到达深度的用户或者不同行为的用户，我们需要采取的营销策略可能会有不同。我们以电商网站的购物流程来举例子。电商网站的购物流程分为以下几个步骤：*

![](//upload-images.jianshu.io/upload_images/1792439-a1aac1676aa13711.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/255/format/webp)

作者：iPhone  
链接：https://www.jianshu.com/p/5f1964fe31e6  
來源：简书  
简书著作权归作者所有，任何形式的转载都请联系作者获得授权并注明出处。
