```
C：可爱的少女Vivienne，今天麻烦你学习一下CSS、JS的语法哦
```

# CSS的组成
  
### 基本语法
  ```
  selector {property: value}
  h1 { color: red; fonrt-size: 14px；}
  ```
  * 缩写 - 十六进制的颜色有CSS缩写
  * 引号 - 如果值为若干个单词，则要加引号。
  * 行 - 每行只描述一个属性，单条声明末尾加引号。
  * 分组 - 选择器可以分组，分享相同的声明。
  ```
  h1,h2,h3,h4,h5,h6
  {
    color: green;
  }
  ```
  - 继承 - 子元素从父元素选择属性。
  
 ---
  
### 选择器
  * 派生选择器：依据元素位置的上下文关系来定义样式，目的使代码更简洁。
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

  * ID选择器：为标有「特定ID」的HTML元素，指定「特定样式」。常用于建立派生选择器。
    - 即使ID只能在每个HTML文档中出现一次，但它作为派生选择器，可以被使用很多次。
  ```
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
  
  * 类选择器：以「点号」显示，以一种「独立于文档元素」的方式来「指定样式」。
    - 将class指定为适当的值=归类，由此将「类选择器的样式」与元素关联。
  ```
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
 
  * 属性选择器：为「拥有指定属性」的HTML元素设置样式，而不仅限于class和id属性。 
    - 只有规定了 !DOCTYPE时，IE7和IE8才支持属性选择器。
    - 为带有 title 属性的所有元素设置样式。
    ```
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
    ```
  
    - 为包含指定值的 title 属性的所有元素设置样式。适用于由空格分隔的属性值。
    ```
    [title~=hello] {color:red;}
    ```
  
    - 为带有包含指定值的 lang 属性的所有元素设置样式。适用于由连字符分隔的属性值。
    ```
    [lang|=en] { color:red; }
    ```
  
    - 为不带有class或id的表单设置样式。
    ```
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
  ---

### 插入样式表
  * 外部样式表
    - 应用于很多页面。
    - 通过改变一个文件，来改变整个站点的外观。
    - 每个页面使用<link>标签链接到样式表。<link>标签在（文档的）头。
    ```
    <head>
    <link rel="stylesheet" type="text/css" href="theme.css" />
    </head>
    ```
    - 外部样式表可以在任何文本编辑器中进行编辑。不能包含任何html标签，样式表应该以.css扩展名进行保存。
    - 不要再属性值与单位之间留有空格。
  
  * 内部样式表
    - 当单个文档需要特殊的样式时，就使用内部样式表。
    - 使用<style>标签在文档头部定义内部样式表。
  
    ```
    <head>
    <style type="text/css">
    hr {color: sienna;}
    p {margin-lift:20px}
    body {background-image: url("images/back40.gif");}
    </style>
    </head>  
    ```
---

# CSS样式

### CSS背景：可以用纯色或图像作为背景；但所有背景属性都不能继承。
  * 背景色：使用「 background-color 」属性设置。
  ```
  /*设置背景色*/
  P {background-color: gray;}
  
  /*设置背景色后作一点延伸*/
  p {background-color: gray; padding: 20px;}
  
  /*所有元素都可以设置背景色，从body到em和a等行内元素*/
  /*background-color不能继承，默认值是transparent。*/
  ```
  
  * 背景图像：使用「 background-image 」属性设置。默认值是 none，表示背景上没有放置任何图像。
  ```
  /*设置背景图像前，要先为这个图像属性设置一个URL值*/
  body {background-image: url(/i/eg_bg_04.gif);}
  
  /*设置body元素以外的背景，如以下是对段落的设置*/
  p.flower {background-image: url(/i/eg_bg_03.gif);}
  
  /*设置行内元素的背景图像，如以下是对链接的设置*/
  a.radio {background-image: url(/i/eg_bg_07.gif);}
  ```
  
  * 背景重复：使用「 background-repeat」属性设置，即对背景图像进行平铺。
    - repeat-x 和 repeat-y 分别导致图像只在水平或垂直方向上重复
    - no-repeat 则不允许图像在任何方向上平铺。
    - 背景图像默认从左上角开始平铺。
    ```
    body
    { 
    background-image: url(/i/eg_bg_03.gif);
    background-repeat: repeat-y;
    }
    ```
  
  * 背景定位：使用「 background-position」属性设置,改变图像在背景的位置。
  ```
  /*使一个背景图像居中*/
  body
  { 
    background-image:url('/i/eg_bg_03.gif');
    background-repeat:no-repeat;
    background-position:center;
  }
  ```
  
  - 关键词
    - 定位值有许多关键字，如top、bottom、left、right 和 center。
    - 关键词可按任何顺序出现，不能超过两个：一个对应水平方向，另一个对应垂直方向。
    - 关键词如只出现了一个，另一个默认为center。
  
  - 百分数值
    - 以下是使一个图像居中，百分数值同时应用于元素和图像。
    ```
    body
    { 
    background-image:url('/i/eg_bg_03.gif');
    background-repeat:no-repeat;
    background-position:50% 50%;
    }
    
    ```
    - 如果只提供一个百分数值，所提供的这个值将用作水平值，垂直值将假设为50%。
    - 以下是把图像放在水平方向 2/3、垂直方向 1/3 处。
    ```
    body
    { 
    background-image:url('/i/eg_bg_03.gif');
    background-repeat:no-repeat;
    background-position:66% 33%;
    }
    ```
  - 长度值
    - 指元素内「边距区」左上角的偏移，偏移点是图像的左上角。
    ```
    /*以下是把图像的左上角置于元素内「边距区」左上角向右 50 像素、向下 100 像素*/
    body
    { 
      background-image:url('/i/eg_bg_03.gif');
      background-repeat:no-repeat;
      background-position:50px 100px;
    }
  
   - 偏移只是从一个左上角到另一个左上角，即图像的左上角与 background-position 声明中的「指定点」对齐。
     ```
  
  * 背景锁定：使文档向下滚动时，背景图像不受影响，即锁定背景。
    ```
    body
    {
    background-image:url(/i/eg_bg_02.gif);
    background-repeat:no-repeat;
    background-attachment:fixed
    }
    ```
   - background-attachment 属性的默认值是scroll，意指在默认情况下，背景会随文档滚动。

---

### CSS文本：定义文本的外观，包括颜色、字符间距、对齐、装饰、缩进等。
  - 缩进文本：使用「text-indent」属性设置，实现文本缩进。所有元素的第一行都可以缩进一个给定的长度，该长度甚至可以是负值。
  ```
  p {text-indent; 5em;}
  /*无法对行内元素、图像之类的替换元素应用*/
  /*如果一个块级元素的首行有一个图像，它会随该行的其余文本移动*/
  /*如果想把一个行内元素的第一行缩进，可以用左内边距或外边距创造这种效果*/
  
  /*设置负值*/
  p {text-indent; -5em;}
  /*可以实现很多有趣效果，比如“悬挂缩进”*/
  /*对段落设置负值后，首行某些文本可能超出浏览器窗口的左边界，建议设置外边距或内边距*/
  p {text-indent: -5em; padding-left: 5em;}
  
  /*使用百分值*/
  /*百分值要相对于缩进元素父元素的宽度。如果缩进值设置为20%，所影响元素的第一行会缩进其父元素宽度的20%*/
  div {width: 500px;}
  p {text-indent:20%}
  
  /*继承*/
  /*text-indent属性可以继承*/
  ```
  
  - 水平对齐：使用「text-align」属性设置一个元素中的文本行互相之间的对齐方式，默认值是left。（希伯来语和阿拉伯语之类的语言，默认值是right）
  1. 「text-align: center」与「CENTER」不同。前者不会控制元素的对齐，只影响内部内容，使文本受影响，后者会把整个元素居中。
  2. 「justify」是使两端对齐。
  
    <br />
    
  - 字间隔：使用「word-spacing」属性设置，默认值是normal即为设置值0。设置正长度为增加间隔，负值为拉近。
  ```
  p. spread {word-spacing: 30px;}
  p.tight {word-spacing: -0.5em;}
  ```
  
    <br />
    
  - 字母间隔：使用「letter-spacing」属性设置，修改的是字符或字母之间的间隔。（语法跟字间隔一样）
    
    <br />
   
   - 字符转换：使用「text-transform」属性处理文本的大小写。
   1. 拥有四个值分别是：none、uppercase（大写）、loswercase（小写）、capitalize（首字母大写）。
   ```
   h1 {text-transform: uppercase}
   ```
  
    <br />
   
   - 文本装饰：使用「text-decoration」属性。
   1. 拥有5个值分别是：none、underline、overline、line-through、blink（文本闪烁）。
   2. none值会关闭原本应用到一个元素上的所有装饰。
   ```
   /*多种装饰*/
   a:link a:visited {text-decoration: underline overline;}
   
   /*两个不同的装饰都与同一元素匹配时，胜出的值会替代另一个*/
   h2.stricken {text-decoration: line-through;}
   h2 {text-decoration: underline overline;}
   ```
   
    <br />
     
   - 处理空白符：使用「white-space」属性进行空格、换行和tab字符的处理。
   1. XHTML默认将所有空白符，合并为一个空格；回车也会转换成空格。
  ```
  p {white-space: normal;}
  ```
   2. 拥有4个值分别是：pre（不合并空白符，保留换行符）、nowrap（合并空白符，防止换行）、prew-arap(不合并空白符，保留换行符且自动换行，）、pre-line（合并空白符，保留换行符且自动换行）
   
    <br />
      
   * CSS字体：定义文本的字体系列、大小、加粗、风斜（如斜体）和变形（如小型大写字母）。
   1. 通用字体系列 - 拥有相似外观的字体系统组合：Serif、Sans-serif、Monospace、Cursive、Fantasy
   2. 特定字体系列 - 具体的字体系列 （如"Times"）
   
    <br />
      
   - 指定字体系列：使用「font-family」属性定义文本的字体系列。
   1. 如果用户代理上没有安装指定的字体，则显示用户代理的默认字体。
   2. 可以通过一次设置候选字体，不限数目，按照优先顺序排列，用逗号衔接，让用户代理按顺序找到能用的字体。
   ```
   p {font-family: Times, Georgia, serif;}
   ```
   3. 当字体名中有一个或以上的空格，或者包含#或$等符号，就需要被加上引号。
   
    <br />
      
   - 字体风格：使用「font-style」属性，通常用于规定斜体文本。
   1. 拥有三个值分别是：normal、italic、oblique（竖直文本的倾斜版本）。后二者在web浏览器上看上去完全一样。
   
    <br />
    
    - 字体变形：使用「font-variant」属性设定小型大写字母。
    ```
    p{font-variant:small-caps;}
    ```
     
    <br />
    
   - 字体加粗：使用「font-weight」属性设置文本的粗细。
   1. 加粗度分为9级，从100=900。（Normal=400，Bold=700）
   2. 设置「bolder」时，显示的字体将会比其继承值更粗。
     
    <br />
    
    - 字体大小：使用「font-size」属性设置文本大小。
    1. 可以设置为绝对值和相对值。
    2. 普通文本（如段落）的默认大小是16像素（16px=1em）。
    3. 可以使用em单位替代pixels。
    4. 结合使用百分比和EM为常用手段。
    ```
    body {font-size:100%;}
    h1{font-size:3/75em;}
    p{font-size:0.875em;}
  
