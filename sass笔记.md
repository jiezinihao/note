---
date: 2019-07-30 18:57
status: public
title: sass笔记
---

#属性部分
##1.变量名规则
使用下划线与中划线互通，只是指向一个变量。
##2.css嵌套规则
(```)
.content article h1 { color: #333 }
.content article p { margin-bottom: 1.4em }
.content aside { background-color: #EEE }
(```)

||||||||||||||||||||||||||||||||||||||
(```)
.content {
  article {
    h1 { color: #333 }
    p { margin-bottom: 1.4em }
  }
  aside { background-color: #EEE }
}
(```)

第二种方式可读性更高，为sass编译，编译后则为第一种
##3.子组合选择器和同层组合选择器> +和~
1.第二个选择器只会选择article下紧跟着的子元素中命中section选择器的元素
`article > section { border: 1px solid #ccc }`
2.+ 同层相邻选择器
选择紧跟在article后的同层article元素
`header + p{......}`
3.~ 同层全体选择器
选择所有跟在article后的article元素
`article~article{.....}`
##4.嵌套属性
把属性名从中划线-的地方断开，在根属性后边添加一个冒号:，紧跟一个{ }块，把子属性部分写在这个{ }块中。
###示例：
(```)
nav {
  border: {
  style: solid;
  width: 1px;
  color: #ccc;
  }
}
(```)

###等同于：
(```)
nav {
  border-style: solid;
  border-width: 1px;
  border-color: #ccc;
}
(```)


---

#文件部分
##1.使用SASS部分文件
1.通过@import导入局部sass文件
2.可以使用文件名已下划线开头，含义是此文件不会单独编译为CSS文件
只用于导入到其他的sass文件的局部文件
##2.默认变量值
语法：！default
含义：如果这个变量被定义，则使用定义的值，如果没有被定义，则使用默认值（默认值自己设置）

#混合器
>含义:可以重用一部分sass代码，相当于片段版的变量

1.使用@mixin <name>来定义混合器名称
2.用@include <name>来引用变量
3.可以给混合器传入参数
(```)
@mixin link-colors($normal, $hover, $visited) {
  color: $normal;
  &:hover { color: $hover; }
  &:visited { color: $visited; }
}
(```)
>引用时注意参数顺序

可以指定$name:value形式给指定变量传参数，注意不要漏参数

4.可以给参数赋予默认值$name:defaut-value
(```)
@mixin link-colors(
    $normal,
    $hover: $normal,
    $visited: $normal
  )
(```)


