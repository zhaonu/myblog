<h1>从url输入到页面展现发生了什么</h1>
<p>一.在浏览器输入URL</p>
<p>&nbsp&nbsp&nbsp&nbsp&nbsp用浏览器访问网页时会在地址栏里输入相应的网址，这个网站地址就是URL地址。URL(Universal Resource Locator)即统一定位资源符，是对可以从互联网上得到的资源的位置和访问方法的一种简洁的表示，是互联网上标准资源的地址。互联网上的每个文件都有一个唯一的URL，它包含的信息指出文件的位置以及浏览器应该怎么处理它。基本URL包含模式（或称协议）、服务器名称（或IP地址）、路径和文件名。</p>
<p>&nbsp&nbsp&nbsp&nbsp&nbspURL有几种最常见的传输协议：1.http超文本传输协议；2.ftp文件传输协议；3.file，主要用于访问本地计算机中的文件；4.https，用安全套接字层传送的超文本传输协议，数据经过了加密。开头只有//代表该URL的协议与当前页面一致。</p>
<p>二.域名解析</p>
<p>&nbsp&nbsp&nbsp&nbsp&nbsp IP地址对应着网络上一台计算机，如果访问的地址是域名而不是IP地址，就需要通过DNS（域名解析系统）将该域名解析成IP地址才能访问。每个处于互联网中的设备都有IP 地址，形如 192.168.0.1。局域网 IP 和公网 IP 是有差别的。IP地址具有唯一性。浏览器查找域名的 IP 地址这一步包括 DNS 具体的查找过程，包括：</p>
<p> &nbsp&nbsp&nbsp&nbsp&nbsp1.浏览器缓存 ，浏览器会缓存DNS记录一段时间。 操作系统没有告诉浏览器储存DNS记录的时间，这样不同浏览器会储存各自固定的一个时间（2分钟到30分钟不等）。</p>
<p> &nbsp&nbsp&nbsp&nbsp&nbsp 2.系统缓存 ，如果在浏览器缓存里没有找到需要的记录，浏览器会做一个系统调用（windows里是gethostbyname），从Hosts文件中查找是否有该域名对应的IP。</p>
<p> &nbsp&nbsp&nbsp&nbsp&nbsp3.路由器缓存 ，一般路由器也会缓存域名信息，如果前面的查询没有结果，那么请求会发向路由器。</p>
<p> &nbsp&nbsp&nbsp&nbsp&nbsp4.ISP DNS 缓存 ， 接下来要查找的就是ISP缓存DNS的服务器，比如电信的DNS服务。在这一般都能找到相应的缓存记录。</p>
<p> &nbsp&nbsp&nbsp&nbsp&nbsp5.递归搜索 。如果都没有找到，则向根域名服务器查找域名对应 IP，根域名服务器把请求转发到下一级，知道找到 IP。一般DNS服务器的缓存中会有.com域名服务器中的域名，所以到顶级服务器的匹配过程不是那么必要了。</p>
<p>三.浏览器向 web 服务器发送一个 HTTP 请求</p>
<p>四.服务器处理</p>
<p>&nbsp&nbsp&nbsp&nbsp&nbsp服务器是一台安装系统的机器，常见的系统如Linux、windows server 2012系统里安装的处理请求的应用叫 Web server。常见的 web服务器有 Apache、Nginx、IIS、Lighttpd。web服务器接收用户的请求交给网站代码，或者接受请求反向代理到其他 web服务器。请求成功后，服务器会返回相应的HTML文件。</p>
<p>五.浏览器处理</p>
<p>&nbsp&nbsp&nbsp&nbsp&nbspHTML字符串被浏览器接受后被一句句读取解析，解析到link 标签后重新发送请求获取css，解析到 script标签后发送请求获取 js，并执行代码，解析到img 标签后发送请求获取图片资源。</p>
<p>六.绘制网页</p>
<p>&nbsp&nbsp&nbsp&nbsp&nbsp浏览器根据 HTML 和 CSS 计算得到渲染树，绘制到屏幕上。js 会被执行通过网站代码，渲染出我们所看到的网站。</p>