# network-base
network
HTTP POST和GET的在多数浏览器中区别(1)			        本质区别
	              POST	          GET	
用途	    向服务器传送数据	  从服务器上获取数据	    GET/POST都能向服务器传输数据
传送方式	在HTTP 请求的内容	  在HTTP 的头部传送	    都是TCP连接，没有本质区别
显示	    不显示	            显示	                都显示
安全	    安全	             不安全	              都不安全
大小	    2M	              1024byte	            无大小限制

GET和POST 只是 HTTP 协议中两种请求方式，而 HTTP 协议是基于 TCP/IP 的应用层协议,无论 GET 还是 POST,用的都是同一个传输层协议，所以在传输上，没有区别。

GET产生一个TCP数据包；POST产生两个TCP数据包。
  对于GET方式的请求，浏览器会把http header和data一并发送出去，服务器响应200（返回数据）;
  而对于POST，浏览器先发送header，服务器响应100 continue，浏览器再发送data，服务器响应200 ok（返回数据）。
  
  
总结
  1、cookie数据存放在客户的浏览器上，session数据放在服务器上。

  2、cookie不是很安全，别人可以分析存放在本地的cookie并进行cookie欺骗，考虑到安全应当使用session。

  3、session会在一定时间内保存在服务器上。当访问增多，会比较占用你服务器的性能，考虑到减轻服务器性能方面，应当使用cookie。

  4、单个cookie保存的数据不能超过4K，很多浏览器都限制一个站点最多保存20个cookie。

  5、可以考虑将登陆信息等重要信息存放为session，其他信息如果需要保留，可以放在cookie中。
  

