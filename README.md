# something-i-need
### base64图片转换
> 在编写发邮件的代码时，发现无法加载图片，于是去百度如何转换
```html
<img src="image/png;base64,base码"> 
```
> 获取base码的最简便的方法就是将图片拖到chrome浏览器中，打开控制台点击source下面的图片资源就可以复制base码了

### 如何解决跨域问题
#### 1.jsonp
#### 2.document.domain
#### 3.服务器跨域
#### 4.cors
> jsonp:json with padding,原理就是通过创建动态脚本发送跨域请求
```html
var script = document.createElement("script");
script.type = "text/javascript";
script.src = "htttp://XXX?callback=demo";
```
> 利用jsonp,服务端会接受这个callback参数，将json数据填充到回调函数之中
> 缺点：1.只支持GET请求 2.不安全 3.没有错误处理机制
#### document.domain
> 只要基础域名相同，就可以通过修改document.domain为基础域名的方式来进行通信，但是需要注意的是协议和端口必须相同

#### 服务器跨域
> 通过nginx反向代理来实现服务端和客户端的通信
#### cors(跨域资源共享)
> 其核心思想是通过添加一系列的http头信息实现客户端和服务端的通信
> cors请求分为2类：简单请求和非简单请求，简单请求方法只支持GET、POST、HEAD；非简单请求会在发送请求之前先发送一个带有OPTIONS方法的请求来确保安全性
