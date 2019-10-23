---
date: 2019-08-30 08:49
status: public
title: Vue的一些随手笔记
---

#动画
    v-enter:进入动画前的状态
    v-enter-active：动画过度的状态，是一个过程，用transition包裹起来
    v-enter-to：在v-enter结束的下一秒生效，相当于动画完成的状态
    v-leave：离开动画的开始状态，通常与v-enter-to一起定义
    v-leave-active：定义离开是生效的状态，通常与v-enter-active一起定义
    v-leave-to：离开动画的结束状态，通常与v-enter一起定义
    
    
##插槽
    插槽的作用是将页面模板内的内容在模板定义里面获取
    获取方式为slot
    具名插槽：意义是在页面内容的一部分命名，在模板用v-slot：name获取指定的内容
    作用域：
    
#cli
##vue-cli-service serve
    用法：vue-cli-service serve [options] [entry]
    选项：    
      --open    在服务器启动时打开浏览器
      --copy    在服务器启动时将 URL 复制到剪切版
      --mode    指定环境模式 (默认值：development)
      --host    指定 host (默认值：0.0.0.0)
      --port    指定 port (默认值：8080)
      --https   使用 https (默认值：false)
      
##vue-cli-service bulid
    用法:vue-cli-service bulid[options][entry|pattern]
    选项：
    --mode  指定环境模式（默认值：production)
    --dest 指定输出目录（默认值：dist）
    --modern    面向现代浏览器带自动回退的构建应用
    --target    app|lib|wc|wc-async
    --name        库或 Web Components 模式下的名(默认值：package.json 中的 "name" 字段或入口文件名)
    --no-clean    在构建项目之前不清除目标目录
    --report      生成 report.html 以帮助分析包内容
    -report-json 生成 report.json 以帮助分析包内容
    --watch       监听文件变化