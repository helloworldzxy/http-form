# http-form
《了不起的Node.js》chap-7 example HTTP 服务器 

这里以git commit的msg为分界线对代码进行说明：

1. initial commit: 

提交请求后只有URL变化了，展示的内容仍然是请求前的内容，相当于浏览器把URL仍然当做`localhost:3000`了。

2. POST/GET /url:

服务器发送响应前会检测url，如果是POST表单url变化会显示不同的页面，此时`req.method`是`POST`；如果是直接访问`localhost:3000/url`页面，此时`req.method`是`GET`.

这里用到了两个属性：`req.url`和`req.method`.

`req.url`: 主机名后的所有内容
`req.method`: HTTP/1.1协议定义的方法：GET（默认）,POST,PUT,DELETE,PATCH。


3. print req content-type

不仅响应头有`Content-Type`属性，请求头也有：`req.headers['content-type']`。
