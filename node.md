---
date: 2019-09-22 14:29
status: public
title: node
---

#node的一些模块
##node的一些小知识
    1.node中没有全局作用域，内部模块访问不到外部模块的方法或者变量，（引用模板之后用模板对象暴露的方法实现除外）外部也访问不到内部（个人理解：这是避免了var会污染全局作用域的弊端）
    2，状态码
    302，临时重定向  
    3.JSON.parse（data）是将data转化成对象
        JSON.stringify(data)是将data转化为字符串
##用require引入
1.fs（filesystem)文件系统
    `fs.readFile('读取文件路径'function(error,data(){...})`
    `fs.writeFile('写入文件路径'，'写入文件内容'function(error){...})`
    
2.http( you know)
    `var server = http.createServer()`创建一个服务器，返回一个server实例
    `server.on('request',function(request,response){})`注册request请求事件，自动触发服务器的request请求事件，执行第二个参数，（处理函数）
    `server.listen(端口号，function(){})`绑定端口号，启动服务器，成功时处理第二个函数(处理函数)
    `response.end(响应内容)`结束响应，同时发送响应内容，一个resquest，一个response
    `request.socket.remoteAddress`获取请求的ip地址
     `request.socket.remotePort`获取请求的端口号
     `request.setHeader('声明标签'，'解析方式(可以有集中，用“;”隔开)')`给浏览器的响应开头 
    
>    处理函数：
    request：请求对象
        用来获取客户端的一些请求信息  
    response:响应对象
            相应对象可以用来给客户端发送响应消息
对response进行操作时，一定要用response.end()来结束响应，不然客户端会一直等待响应结束