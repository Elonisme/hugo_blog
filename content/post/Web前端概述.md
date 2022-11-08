---
layout:     post
title:      "Web前端概述"
date:    2021-07-04T12:00:00
author:     "Elon Li"
image: "/img/post-bg-coffee.jpg"
tags:
    - Linux
categories: [ note ]
---



## Web前端概述

概述题就是各个章节的主要理论知识


## web通信

### HTTP协议

Hyper Text Transfer Protocol 超文本传输协议，是一种建立在TCP上的无状态连接应用层协议。

### B/S体系结构

浏览器/服务器端（Browser/Server），这种模式将数据和核心业务逻辑都放在服务器上，客户端即浏览器。

### 静态网页与动态网页

1. 静态网页一般指HTML及其相关的CSS、JavaScript片段或文档，一经发布就不能改变
2. 动态页面除了HTML标记语言之外，还包括一些特定功能的程序代码、这些代码可以使得浏览器和服务器进行交互。

### HTML、CSS与JavaScript

1. Hyper Text Mark-up Language 超文本标记语言是web应用程序客户端开发的基础，它是一种文本形式的标记符号语言，主要是描述网页信息。所谓超文本是指可以包含图片、链接、甚至音乐、程序等非文字元素。
2. Cascading Style Sheet 称为级联或层叠样式表，用于控制页面的显示风格，如页面的布局、字体、颜色、背景、动画等。
3. JavaScript是一种广泛用于Web前端开发的解释型脚本语言，不需要编译，具有跨平台性，脚本镶入到网页中，常用来为网页添加动态功能，随同网页被下载到客户端，由浏览器执行。

## html标记语言与表单

### html标记语言

1. Hyper Text Mark-up Language 超文本标记语言是web应用程序客户端开发的基础，它是一种文本形式的标记符号语言，主要是描述网页信息。所谓超文本是指可以包含图片、链接、甚至音乐、程序等非文字元素。

### 列表

1. 有序标签:

   ```html
   <ol type=...>
       <li></li>
       .....
       <li></li>
   </ol>
   ```

   其中type可以等于：

   ”1“、”a“,"A"、”i“、"I"

2. 无序标签：

   ```html
   <ul type=..>
       <li></li>
       .....
       <li></li>
   </ul>
   ```

   其中type可以等于：

   disc:实心圆
   circle：空心圆

   square：实心方块

### 表单

1. 表单的处理过程：

   1. 设计表单，并放置一些输入域，或者称之为表单元素
   2. 访问者在客户端上填写上述输入域，并提交到服务器端
   3. 服务器端处理数据并返回

2. 基本语法：

   ```html
   <form action="..." method="get">
       <input type="text" name="user"/>
       <select name="habit">
           <option value="football">足球</option>
       </select>
       <input type="submit" value="提交"/>
   </form>
   ```

   action:指提交到哪个服务器，url地址

   method：指提交的方式

   1. get：在http请求的URL地址后嵌入表单数据，以”？“开始，每一项数据按照”name=value"格式，使用“&”相连，数据开放。通过地址栏传递
   2. post：安全性高。通过报文传递。慢，内容多。

## CSS概念 

HTML诞生于20世纪90年代初

缺陷：代码臃肿；定位困难；维护困难；标记不足；

```html
<style type="text/css">
    p{
        font-size:20px;
    }
</style>
```

### 选择器

1. 标签选择器:<p>

2. 类选择器:.aa

3. ID选择器#bb

4. 全局选择器：**{}*

5. 复合选择器：

   1. 并集选择器 E1，E2 E3{ ........}
   2. 交集选择器E.myclass{...}或者E#myid{....}
   3. 包含选择器：E F（子子孙孙）
   4. 子选择器：E>F （只有子代，没有孙子）
   5. 相邻选择器：E+F （与E之后紧密相邻的F）
   6. 兄弟选择器：E~F （E之后所有的兄弟元素F）

6. 伪对象选择器

   1. E:first-letter
   2. E:first-line
   3. E::selection
   4. E:before
   5. E:after

7. 属性选择器

8. 结构伪类选择器:

   ![image-20220108195733754](C:\Users\41630\AppData\Roaming\Typora\typora-user-images\image-20220108195733754.png)

9. 元素伪类选择器：

10. 元素状态

    1. E：link
    2. E:visited
    3. E:hover
    4. E:active
    5. E:focus
    6. E：checked

### 布局模式

#### 弹性盒布局

1. display：指定HTML元素盒子类型
2. flex-direction：指定弹性容器中子元素的排列方式
3. justify-content：横轴方向上对齐方式
4. align-items：纵轴方向上对齐方式
5. flex-wrap：超出后是否换行
6. align-content：设置行对齐
7. flex-flow：包含flex-direction和flex-wrap的复合属性
8. order：排序
9. align-self：弹性子元素
10. flex：设置弹性盒子的子元素如何分配弹性容器的剩余空间

#### 弹性盒子CSS样式设置

1. display：flex（块级元素）/inline-flex（行内元素）

   

1. ```css
   #container{
       display:flex;
   }
   ```

   多栏布局

   ```css
   #container{
       column-count:3;
       column-width:300px;
   }c
   ```

### 文档流

1. 文档流：HTML元素就是河里的水，水从左到右分布，从上到下“流”。类似于流，浏览器从上到下一行一行（即一个一个块级元素）的加载和显示，每一行里又是从左到右加载一个一个行内元素。

### 盒子模型

1. 在CSS3中，所有页面元素都包含在一个矩形框内，称之为盒子（Box）。盒子模型是由以下四部分组成的。
2. margin-外边距
3. border-边框
4. padding-内边距
5. content-盒子的内容

## JS主要功能：

### 背景知识

1. 脚本语言
   1. 依据一定的格式编写的描述性程序性语言，它以文本形式存在，是一种不必事先编译，只要利用适当的解释器就可以执行的简单的解释性程序，也就是说，它并不产生机器代码，只是由解释器将其动态处理成可执行的代码。
   2. 面向web应用的，基于对象和事件驱动的轻量级的解释型或者即时编译型的客户端脚本语言。
   3. 主要应用于web的页面开发，通过嵌入在html中来实现自身的作用，为网页添加动态交互效果，检验表单数据，HTML5 API编程（如视频播放器、canvas绘图】、传感器应用），以及与服务器通信（AJAX），等等。
2. 作用
   1. 动态改变网页内容，即增删查改HTML元素
   2. 动态改变网页外观，即修改HTML元素的CSS样式
   3. 验证表单数据，减少服务器负担和网络带宽压力
   4. 响应浏览器和网页事件
   5. HTML5API编程

###  bom和dom树

1. BOM（浏览器对象模型）
   1. 浏览器对象模型BOM提供了用户与浏览器对象之间的交互和操作的接口。在BOM中，对象之间存在层次关系，window为顶层对象，所有其他对象都是window的子对象。
2. DOM（文档对象模型）
   1. DOcument Object Model，简称DOM，采取直观、一致的方式对结构化文档（HTML、XML）进行模式化处理，形成一颗结构化的文档树。每当HTML文档被加载后都会在内存中初始化一个document对象，该对象存放整个网页HTML内容，从该对象中可获取页面任何元素，包括表单的各种信息。

###  web存储

#### Web存储

1. 以key-value（键值对）字符串形式存储。特点：存储容量更大（每个域5M以上），安全性更高、效率也更高。
2. sessionStorage：会话存储，针对一个会话期的数据存储，一旦窗口或者标签被关闭，那么存储的数据将被清空
3. localStorage：本地存储，生命周期为永久，除非通过脚本语言或手动清除，存储的数据可被同源的每一个窗口或者标签页共享。

#### Cookie

1. 客户端本地存储如用户信息、状态等不超过4KB的小型文本数据集合，每个数据项都由一个名称（Name）、一个值（Value）和其他几个用于控制Cookie有效期、安全性、使用范围的可选属性组成。在用户下一次访问该页面时，可以在Cookie中读取用户的信息。
2. Cookie的缺陷
   1. 容量小和数量有限。上限为4kb，且多数浏览器只支持30-50个Cookie
   2. 安全性差。以文本形式储存在客户端，容易被拦截窃取。
   3. 效率低。虽然Cookie是存储在客户端·，但由于每一个对服务器的请求来传递，即客户端浏览器请求时将Cookie发给服务器，服务器再根据用户需要回传cookie信息给客户端浏览器，这使得cookie读写速度很慢、效率低，且需要网络。

#### 地图api 

1. Geolocation
   1. HTML5新增的地理位置应用程序接口，它提供了一个可以感知用户或者设备当前地理位置（如：经纬度、海拔、甚至是移动方向和速度）的方法。注意可能侵犯用户的隐私，因此必须得到用户的许可才可以使用。
2. 定位技术
   1. IP定位：精度低、错误率高、运算代价大。
   2. WIFI定位：室内可用、简单快捷
   3. 基站定位：精度高、室内可用、简单快捷、受基站数量影响
   4. 卫星定位：精度最高、但耗时、耗电、室内效果差

## AJAX

1. Ajax（Asynchronous JavaScript and XML）是运用JavaScript和可扩展语言（XML）实现浏览器与服务器异步交互的技术，对用户请求的响应不需要刷新整个页面，只需要刷新局部页面即可，不会中断用户的操作。

## jQuery的使用方法

1. jQuery是一个轻量级的JavaScrip函数库，若在网页设计中使用，必须先下载jQuery有关的Jar包，并将Jar包添加到网页中。