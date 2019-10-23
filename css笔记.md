---
date: 2019-08-19 04:43
status: public
title: css笔记
---

>rgba（最后一个参数指定透明度（transparent））
list-style-tyle:none 移除列表前的小标志
text-decoration:none 移除字体下划线
z-index:number 堆叠顺序，也就是元素显示优先级，number越大，优先级越大
inherit 从父元素哪里继承指定的属性
inline-block 联合块级内联元素，使元素可以放在一行，并且可以设置宽高，padding的左右和margin的上下
opacity 图像的透明度，1最大，0完全透明；
box-sizing 设置此属性使会将盒子的padding和边框计算到其width和height里

# 圆角（border-radius）

​    1.border-radius指定每个圆角
​    四个值: 第一个值为左上角，第二个值为右上角，第三个值为右下角，第四个值为左下角。
​    三个值: 第一个值为左上角, 第二个值为右上角和左下角，第三个值为右下角
​    两个值: 第一个值为左上角与右下角，第二个值为右上角与左下角
​    一个值： 四个圆角值相同

# 渐变（linear-gradient）

​    指定一个方向（left right，to rigt），然后指定开始颜色和过度后颜色
​    shape（第一个参数）参数定义形状，circle是圆形，ellipse是椭圆形
​    

# 伪类

​    伪类选择元素基于的是当前元素处于的状态，或者说元素当前所具有的特性，而不是元素的   id、class、属性等静态的标志。由于状态是动态变化的，所以一个元素达到一个特定状态时，它可能得到一个伪类的样式；当状态改变时，它又会失去这个样式。由此可以看出，它的功能和class有些类似，但它是基于文档之外的抽象，所以叫伪类。

### a:link {color:FF0000;} /* 未访问的链接 */

### a:visited {color:00FF00;} /* 已访问的链接 */

### a:hover {color:FF00FF;} /* 鼠标划过链接 */

### a:active {color:0000FF;} /* 已选中的链接 */

​    注意，hover必须在link和visited之后才有效
​    active必须在hover之后才有效

### ：first-child选中父元素的第一个子元素

### :before 在每一个父元素之前插入内容

### :after 在每一个父元素之后插入内容

### :firsts-line 每个父元素的第一行

# display

​    display:inline 将块元素改变成内联元素
​    display:block 将内联元素改变成块元素
​    

>块元素：是占用了页面全部的宽度，前后都是换行符
内联元素：是指需要必要的宽度，不强制换行，

# position

​    static HTML的默认值，即没有定位，遵循正常的文档流对象
​    fixed 元素的位置相对于浏览器窗口的固定位置，即使窗口是滚动的他也不会移动
​    relative 相对定位元素，相对其正常位置，其原本所占空间不会改变
​    absolute 绝对定位 其位置i相对于最近的以定位父元素，如果没有以定位的父元素，位置相当于<html>
​    sticky 粘性定位，根据用户窗口位置，在static和relative之间切换（可实现回到顶部功能）

>如果两个定位元素重叠，没有指定z - index，最后定位在HTML代码中的元素将被显示在最前面。
指定left，right，bottom，top值

# overflow

​    visible 默认值，内容不会被修建，会出现在元素之外
​    hidden 超出内容会被修剪，并不可见
​    scroll 内容会被修剪，但是会显示滚动条
​    auto 如果内容被修剪，显示滚动条
​    

# transform

​    2D属性：
​    translate(x,y)根据给定的x轴和Y轴移动和
​    rotate（deg）给定一个度数旋转，可以为负数
​    scale（x，y）根据给定的宽和高增加或减少元素的大小
​    skew（x，y）根据x轴或者Y轴倾斜，y轴默认为0

    3D属性：
    rotaleX（deg）给定一个度数X轴旋转
    rotateY（deg）给定一个度数Y轴旋转

# 过渡

​    在元素style里生命过渡属性transition，意义是当元素变化时，需要此时间
​    transition的属性是style里属性加上时间，意义是在此属性在这段时间里的变化
​    然后就可以写使此元素变化的时间比如：hover等，在其中写出属性的变化

# 动画

​    

    定义一个@keyframes规则，在animation里使用此规则,并定义时长
```
        div
    {
        animation: myfirst 5s;
        -webkit-animation: myfirst 5s; /* Safari 与 Chrome */
    }
```
    @keyframes规则
    事件定义规则
    1.有0-100%的动画过程，可以指定其过程
    2.直接设置至少from-to个属性，为0%和100%（默认0）
    列如：
    1.@keyframes myfirst
    {
        0%   {background: red;}
        25%  {background: yellow;}
        50%  {background: blue;}
        100% {background: green;}
    }
    2。2keyframes myfirst{
        from {background: red;}
        to {background: yellow;}
    }

# flex布局

​    基本属性：
​        flex-direction: 
​        1.row：横向从左到右排列（左对齐），默认的排列方式。
​        2.row-reverse：反转横向排列（右对齐，从后往前排，最后一项排在最前面。
​        3.column：纵向排列。
​        4.column-reverse：反转纵向排列，从后往前排，最后一项排在最上面。
​        justity-content:
​        1.flex-start: 相当于float：left，当然是弹性盒子
​        2.flex-end： 相当于flex-start 的reverse版
​        3.center: 居中紧挨着布局
​        4.space-between： 弹性项目平均的分布在改行（列）上，第二个在最后
​        5.space-around： 从中央像两边均匀分布弹性项目