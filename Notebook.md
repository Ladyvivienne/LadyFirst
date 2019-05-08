# I. Git

```
C：Hi vivienne，git是分布式版本控制系统。 什么是分布式？
```
##### 定义：
* 分布式系统是若干独立计算机的集合。
* 通过网络进行信息交换的系统。（■种子库？）
* 一个大系统，拆分成多个子系统（process），分布到不同设备通信。（■网络替代本地实现共享？）
##### 特性：
* 分布式系统，通过多台机器<u>提高系统的负载能力</u>。
* 因为有了分布，一个子系统坏了不会影响其他系统。每一次的提取操作，实际上都是一次对代码仓库的完整备份。所以<u>运维可靠</u>。
* 分布式系统的四大要素：<u>Process进程</u>、<u>通信协议</u>、<u>命名法</u>、<u>协作</u>。
##### 难点
* 分布式系统 vs 集中式系统，集中式系统没有分布式的特性。
* 分布式不等于并行计算。
  
```
C：Hey Vivienne，了解一下git的基本原理。
```
##### Git的由来
* Github是一个开放源码的分布式控制系统，当初被开发，是为了替代Bitkeeper（遍布全球的Linux开发成员，用此作为源代码工具）。
* Git的两个主要功能：
  - 版本管理
  版本控制是一种记录若干文件内容变化，以便将来查阅特定版本修订情况的系统。即修改/删除代码后的新项目，上传到github托管，能追踪历史和还原，实现方式为Repositionery里的file。
  - 协作开发
  同步大家更新的版本，一直存储最新的代码库，所以有了fork功能。
  
##### Git的特性
* Git只关心文件数据的<u>整体是否发生变化</u>
  大多数其他系统则只关心文件内容的具体差异，而Git 更像是把变化的文件作快照后，记录在一个微型的文件系统中。每次提交更新时，它会纵览一遍所有文件的指纹信息并对文件作一快照，然后保存一个<u>指向这次快照的索引</u>。
* Git支持离线工作
  本地操作→本地提交→再上传到服务器上。
  Git对修改文件进行快照→保存到暂存区域→提交更新，快照永久转储到 Git 目录。（■快照是哪个？）
* Git的三种文件形态
  已提交（Committed）、已修改（modified）、已暂存（staged）。
 
##### Git的使用流程
* Fork一个自己喜欢的项目。
* 建立本地的资源池（Local Repo），将项目clone到本地（SSH/HTTP形式）。
* Clone完成后，一个名为“origin”的远端生成指向我在github的版本，此时需要另一个远端“upstream”来获取原始项目的更新。
* 推送提交Push Commits。

```
C：Vivienne，你今天要学会用GUI界面操作喔，add、commit、push、brach、stash的用法。
```
* Add，是指在本地仓库里添加一个工程文件（txt、py）。
* commit，是指在Gui里面写注释，push后会同步到github上的pull resquest里可见。
* push，是把txt文件上传到github。
* brach，是创造一个跟github上原项目版本一样的项目，新命名名字。
* ■stash，在哪里，没遇到诶诶诶诶
  
  <br />
  <br />
  <br />
  
# Ⅱ. Front End

```
C：Vivienne，了解一下浏览器基本原理。
```
##### 浏览器的主要构成
* 浏览器由两部分组成：Shell+内核。
* Shell：提供给用户界面操作、参数设置等，通过调用内核来实现各种功能。如菜单、工具栏等。
* 内核：就是渲染引擎和js引擎，常见有：Trident、Gecko、Presto、Webkit。

##### 浏览器的主要功能
* 用户用URI来指定所请求的资源位置，浏览器将该资源显示出来。资源格式为：Html、PDF、image等。
* 常见的用户界面元素：地址栏、前进/后退按钮、书签、刷新/暂停按钮、主页按钮（约定俗成，没有统一规范）

##### 浏览器的主要组件
* 用户界面 - 浏览器界面
* 渲染引擎 - 显示请求的内容，即渲染html文档。如请求为html，则解析html及css后显示结果。
* 网络 - 完成网络调用，发送和响应http请求。
* UI后端 - 绘制组合框、对话框等基本组件，具有不特定于某个平台的通用接口，底层使用操作系统的用户接口。
* JS引擎 - 用来解释执行JS代码。
* 数据存储 - 浏览器持久层，在硬盘中保存cookie、localStorage、database（html5）等数据。
[https://www.2cto.com/uploadfile/Collfiles/20180531/20180531091635172.png][图示]

##### 渲染引擎的工作原理
* 请求HTML ==> 解析HTML ==> 构建DOM树 ==> 构建render树 ==> 布局render树 ==> 绘制render树
* Step1：渲染引擎开始解析html，并将标签转化为内容树中的dom节点。（DOM是文档对象模型的缩写，是html文档的对象表示，作为html元素的外部接口供js等调用。）
* Step2：渲染引擎解析外部CSS文件及style标签中的样式信息。
* Step3：前两步解析出的信息被构建为render树———由一些包含有颜色和大小等属性的矩形组成，它们将被按照正确的顺序显示到屏幕上。 
* Step4：Render树构建后，开始执行布局过程，它将确定每个节点在屏幕上的确切坐标。
* Step5：绘制，即遍历render树，并使用UI后端层绘制每个节点。 

##### 渲染引擎的特性
* 它是解析完一部分内容就显示一部分内容，同时，可能还在通过网络下载其余内容。（怪不得有时候部分东西加载不出来）

```
C：准备开始上手了喔，先了解html+css+javascript分别是什么？
```
##### html是什么？
* 定义：全称为超文本标记语言(Hyper Text Markup Language)，是网页的本质。
* 功能：超文本指非文字元素，标记语言=通过标记符号来标记要显示的网页中的各部分。
* 特性：
  - 结构包括“头”部分（英语：Head）、和“主体”部分（英语：Body），其中“头”部提供关于网页的信息，“主体”部分提供网页的具体内容。
  - html其实是文本，它需要浏览器来解释。
  
##### css是什么？
* 定义：全称为层叠样式表（Cascading Style Sheets），样式定义如何显示 HTML 元素并存储在样式表中。
* 功能：
  - 网页的布局、颜色、背景、宽度、高度、字体进行「美工设计」的控制。
  - 可以静态地修饰网页，还可以配合各种脚本语言动态地对网页各元素进行格式化。
  - 外部样式表可以极大提高工作效率，外部样式表通常存储在 CSS 文件中。
* 特性：
  - 层叠性。层叠就是对一个元素多次设置同一个样式，这将使用最后一次设置的属性值。
  - 弱体积性。将样式的声明单独放到CSS样式表中，可以大大的减小页面的体积。
  - 便于修改和归类。一个样式定义多个子样式、一个样式应用到所有同名Html标签中、一个样式指定到某个页面元素中。
  - 统一性。多个样式定义可层叠为一，实现多个页面风格的统一。
  - 层叠次序。浏览器缺省设置-外部样式表-内部样式表（位于 <head> 标签内部）-内联样式（在 HTML 元素内部，优先权最高）。
  
##### javascript是什么？
* 定义：一种面向Web的是解释性脚本语言，被JS引擎解析，
* 功能：用来给HTML网页添加交互行为，实现动态功能。
  - 嵌入动态文本于HTML页面。
  - 对浏览器事件做出响应。
  - 读写HTML元素。
  - 在数据被提交到服务器之前验证数据。 
  - 检测访客的浏览器信息。
  - 控制cookies，包括创建和修改等。
  - 基于Node.js技术进行服务器端编程。
* 特性：
  - 脚本语言。在程序的运行过程中逐行进行解释，与此相反的C、C++等语言是先编译后执行。
  - 基于对象。JavaScript是一种基于对象的脚本语言,它不仅可以创建对象,也能使用现有的对象。
  - 动态性。采用事件驱动，如在网页中进行鼠标点击或上下移、窗口移动等操作，JavaScript都可直接给出相应的响应。
  - 跨平台性。可以带到任意机器上使用，不依赖于操作系统，不需要服务器的支持，但因此安全性差。
  
```
C：可爱的少女Vivienne，今天麻烦你学习一下CSS、JS的语法哦
```
  
  <br />
  <br />
  <br />
  
# Ⅲ. CSS

##### CSS的组成：
  
* 基本语法：
  ```
  selector {property: value}
  h1 { color: red; fonrt-size: 14px；}
  ```
  - 缩写 - 十六进制的颜色有CSS缩写
  - 引号 - 如果值为若干个单词，则要加引号。
  - 行 - 每行只描述一个属性，单条声明末尾加引号。
  - 分组 - 选择器可以分组，分享相同的声明。
  ```
  h1,h2,h3,h4,h5,h6
    {
    color: green;
    }
  ```
  - 继承 - 子元素从父元素选择属性。
  
  
* 选择器
  - 派生选择器：依据元素位置的上下文关系来定义样式，目的使代码更简洁。
  ```
  strong
    {
    color: red;
    }
  
  h2
    {
    color: red;
    }

  h2 strong
    {
    color: blue;
    }
  ```

  - ID选择器：为标有「特定ID」的HTML元素，指定「特定样式」。常用于建立派生选择器。
  ```
  /*即使ID只能在每个HTML文档中出现一次，但它作为派生选择器，可以被使用很多次*/
  # sidebar p 
    {
    front-style: italic;
    text-align: right;
    margin-top: 0.5em;
    }
    
  # sidebar h2 
    {
    font-size: 1em;
    front-weight: normal;
    font-style: italic;
    margin: 0;
    line-height: 1.5;
    text-align: right;
    }
  ```
  
  - 类选择器：以「点号」显示，以一种「独立于文档元素」的方式来「指定样式」。
  ```
  /*将class指定为适当的值=归类，由此将「类选择器的样式」与元素关联*/
  <head>
  <style type="text/css">
  .important {cololr:red}
  </style>
  </head>

  <body>
  <h1 class="important">This heading is very important.</h1>
  <p class="important">This paragraph is very important.</p>
  <p>This is a paragraph.</p>
  ```
 
  - 属性选择器：为「拥有指定属性」的HTML元素设置样式，而不仅限于class和id属性。 
  ```
  /*只有规定了 !DOCTYPE时，IE7和IE8才支持属性选择器*/
  /*为带有 title 属性的所有元素设置样式*/
  <head>
  <style type="text/css">
  [title]
    {
    color:red;
    }
  </style>
  <head>

  <body>
  <h1>可以应用样式：</h1>
  <h2 title="Hello world">Hello world</h2>
  <a title="Vivienne's dream">Vivienne's dream</a>

  <hr />

  <h1>无法应用样式：</h1>
  <h2>Hellow world</h2>
  <body>
  
  /*为包含指定值的 title 属性的所有元素设置样式。适用于由空格分隔的属性值*/
  [title~=hello] {color:red;}

  /*为带有包含指定值的 lang 属性的所有元素设置样式。适用于由连字符分隔的属性值*/
  [lang|=en] { color:red; }

  /*为不带有class或id的表单设置样式*/
  <head>
  <style>
  input[type="text"]
    {
    width:150px;
    display:block;
    margin-bottom:10px;
    background-color:yellow;
    font-family: Verdana, Arial;
    }

  input[type="button"]
    {
    width:120px;
    margin-left:35px;
    display:block;
    font-family: Verdana, Arial;
    }
  </style>
  </head>
  <body>

  <form name="input" action="" method="get">
  <input type="text" name="Name" value="Bill" size="20">
  <input type="text" name="Name" value="Gates" size="20">
  <input type="button" value="Example Button">

  </form>
  </body>
  ```

* 插入样式表
  - 外部样式表
  ```
  /*应用于很多页面*/ 
  /*通过改变一个文件，来改变整个站点的外观*/
  /*每个页面使用<link>标签链接到样式表。<link>标签在（文档的）头部*/  
  <head>
  <link rel="stylesheet" type="text/css" href="theme.css" />
  </head>

  /*外部样式表可以在任何文本编辑器中进行编辑。不能包含任何html标签，样式表应该以.css扩展名进行保存。
  /*不要再属性值与单位之间留有空格。
  ```
  
  - 内部样式表
  ```
  /*当单个文档需要特殊的样式时，就使用内部样式表*/ 
  /*使用<style>标签在文档头部定义内部样式表*/ 
  <head>
  <style type="text/css">
  hr {color: sienna;}
  p {margin-lift:20px}
  body {background-image: url("images/back40.gif");}
  </style>
  </head>  
  ```

##### CSS样式：
* CSS背景：可以用纯色或图像作为背景；但所有背景属性都不能继承。
  - 背景色：使用「 background-color 」属性设置。
  ```
  /*设置背景色*/：
  P {background-color: gray;}
  
  /*设置背景色后作一点延伸*/：
  p {background-color: gray; padding: 20px;}
  
  /*所有元素都可以设置背景色，从body到em和a等行内元素*/
  /*background-color不能继承，默认值是transparent。*/
  ```
  
  - 背景图像：使用「 background-image 」属性设置。默认值是 none，表示背景上没有放置任何图像。
  ```
  /*设置背景图像前，要先为这个图像属性设置一个URL值*/
  body {background-image: url(/i/eg_bg_04.gif);}
  
  /*设置body元素以外的背景，如以下是对段落的设置*/
  p.flower {background-image: url(/i/eg_bg_03.gif);}
  
  /*设置行内元素的背景图像，如以下是对链接的设置*/
  a.radio {background-image: url(/i/eg_bg_07.gif);}
  ```
  
  - 背景重复：使用「 background-repeat」属性设置，即对背景图像进行平铺。
  ```
  /*repeat-x 和 repeat-y 分别导致图像只在水平或垂直方向上重复*/
  /*no-repeat 则不允许图像在任何方向上平铺*/
  /*背景图像默认从左上角开始平铺*/
  body
    { 
    background-image: url(/i/eg_bg_03.gif);
    background-repeat: repeat-y;
    }
  ```
  
  - 背景定位：使用「 background-position」属性设置,改变图像在背景的位置。
  ```
  /*以下是使一个背景图像居中*/
  body
    { 
    background-image:url('/i/eg_bg_03.gif');
    background-repeat:no-repeat;
    background-position:center;
    }
  
  /*关键词*/
  /*定位值有许多关键字，如top、bottom、left、right 和 center*/
  /*关键词可按任何顺序出现，不能超过两个：一个对应水平方向，另一个对应垂直方向*/
  /*关键词如只出现了一个，另一个默认为center*/
  
  /*百分数值*/
  /*以下是使一个图像居中，百分数值同时应用于元素和图像*/
  body
    { 
    background-image:url('/i/eg_bg_03.gif');
    background-repeat:no-repeat;
    background-position:50% 50%;
    }
  /*如果只提供一个百分数值，所提供的这个值将用作水平值，垂直值将假设为 50%/
  /*以下是把图像放在水平方向 2/3、垂直方向 1/3 处*/
  body
    { 
    background-image:url('/i/eg_bg_03.gif');
    background-repeat:no-repeat;
    background-position:66% 33%;
    }

  /*长度值*/
  /*长度值，指元素内「边距区」左上角的偏移，偏移点是图像的左上角*/
  /*以下是把图像的左上角置于元素内「边距区」左上角向右 50 像素、向下 100 像素*/
  body
    { 
    background-image:url('/i/eg_bg_03.gif');
    background-repeat:no-repeat;
    background-position:50px 100px;
    }
  /*偏移只是从一个左上角到另一个左上角，即图像的左上角与 background-position 声明中的「指定点」对齐*/
   ```
  
