---
date: 2019-08-15 21:07
status: public
title: js笔记
---

### window对象

整个浏览器激素window对象

### 1.comfirm:

有确定和取消的提示框，确定和取消按钮是true和false

### 2.prompt（）：

带输入的提示框，两个参数，标题和默认值，返回值是输入的内容，

### 3.open()：

加载URL，可以传入打开窗口的长宽,opener是父窗口对象

### 4.location:

​    location.hash:锚点，实现页内跳转
​    location.host:端口号，默认为80
​    location.hostname:主机名，域名/IP  
​    location.href:整个URL
​    location.pathname:路径名称
​    location:port:端口号
​    location.protocal:协议，如:file/http/https..
​    location.search:查询字符串，更在？后的内容      
​    >方法：
​    assign():跳转到指定的URL
​    reload():重载当前的URL,参数为true，强制重载
​    replace(): 

### history

​    history.lenth：返回当前history对象中记录历史记录的条数
​    方法：
​    history.back()：返回上一条历史记录
​    history.forword():前进到下一条历史记录
​    history.go():指定参数，进入到指定历史记录 

### Symbol()

​	给变量设置一个唯一标识传入一个参数，作为标识符

​	有Symbol的裂变或者对象，不能遍历

​	可以使用

```js
Object.getOwnPropertySymbols(对象名).map(sym => 变量名.sym)
```



# DOM对象 Document Object Model

>所有DOM节点在js里都是对象

### document对象

​    document.getElementBId(id)获取此ID的元素节点
​    document.getElementsByTagName(标签名)获取所有此标签的数组
​    document.getElementsByName(name的属性值)返回装有所有name的数组
​    document.getElementsByClassName(class的属性值)返回所有class的数组
​        获取元素之后的属性
​        var.tagName
​        var.innerHTML
​        var.id
​        var.title
​        var.className等
​        同时可以修改style的属性值(注意属性中的‘-要使用驼峰式命名来写属性
​        var.style.backgroundColor

## 节点操作

​    document.createElement(标签名):添加标签
​    parent.appendChild(元素节点)：将元素节点插入到parent节点尾
​    document.createTextNode(文本内容)：创建一个Node文本内容，之后要进行插入
​    
事件event

### document.onclick：

​    属性：
​        event.clientX,clientY：相对于页面的高和宽
​        event.pageX,pageY:绝对的高和宽
​        event.offsetX,offsetY:此元素的宽和高
​        

### document.onkeypress:监听字符键

### document.onkeydown:监听键盘，按下触发事件

​    属性：
​        altkey,shiftkey,ctrlkey监听键盘，按下返回true
​        keyCode:返回键盘代码

### 事件的触发机制（三个阶段：捕获，目标，冒泡）

### 冒泡(阶段理解：不允许同时触发多个事件)

​     event.cancelBubble = true；全部浏览器，默认为false
​     event.stopropagetion();现代浏览器IE8以下不支持

### 事件委托机制 

>利用事件冒泡的原理，把本应添加给某元素上的事件委托给他的父级

### 阻止事件默认行为

​    event.preventDefault();
​    event.returnValue = false;
​    return false;

>浏览器右键阻止默认行为  document.oncontextmenu

# DOM2级事件处理程序

​    添加事件监听器：
​        addEventListener(事件名（不带on），处理函数，布尔值（ture：捕获，false（默认）：冒泡）
​    移除事件监听器：
​        removeEventListener（事件名，处理函数）
​    IE下的事件按监听器：
​        attachEvent(事件名，处理函数）
​        删除：datachEvent（时间名，处理函数）

缓存数据
cookie
>存储在本地服务器上的数据

```js
 设置cookie
document.cookie = string（接受一个字符串）
属性
     name：cookie名称
    expries：cookie过期的时间
删除cookie：
    就是将expries设置成当前时间
```

