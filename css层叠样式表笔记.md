

## css层叠样式表笔记

### 1.什么是css

用于美化网页，布局页面

#### 1.1html的局限

只注重内容的语义，只管内容的元素显示（最基本的样子）

#### 1.2css修饰网页（级联样式表 cascading style sheets）

是一种标记语言，可以用来设置页面文本内容，图片外形和版面布局等。用来美化html，使页面更好看。

**结构和样式相分离，css专注样式，html专门做结构呈现。**

#### 1.3css语法规范

选择器+样式组成（一条或者多条声明）

![image-20230303163823347](C:\Users\Tsing\AppData\Roaming\Typora\typora-user-images\image-20230303163823347.png)

***css一般写在head标签里***

```
<head>
<style>
选择器{样式}
/** 给谁改样式{改成什么样} **/
</style>
</head>
```

选择器是用于指定css样式的***<u>html</u>***标签，花括号里是具体的样式

#### 1.4css代码风格：实际书写方式

1.样式格式书写

①紧凑格式

```
h3{color:deeppink;font-size:20px}
```

**②展开格式**（实际书写用这个）

```
h3{
color:pink;
font-size:20px;
}
```

2.全部用小写

3.空格要求：

属性值前面，冒号后面，都要写一个空格

选择器与大括号之间保留一个空格

### 2.css基础选择器

#### 2.1选择器的作用

选择标签用的。

#### 2.2标签选择器

##### 基础选择器：标签选择器，类选择器，id选择器，通配符选择器

###### ①标签选择器

标签名作为选择器的名字，为页面里***某一类标签全部统一***添加css样式，缺点：不可以做出差异化。

###### ②类选择器

**可以单独选择一个或者某几个标签，可以实现差异化。 结构用class属性来调用。**

```
.类名{
属性1：属性值1；
}
```

eg:

```
.red {
color:red; 
}
/****定义类****/
<li class='red'>文字</li>
/*** 调用 ***/
```

- 口诀：样式点定义，结构类（class）调用，一个或多个，开发最常用。
- ***<u>先定义一个样式，谁需要这个样式谁用class结构来调用这个样式就可以。</u>***

- 不可以用标签的名字来作为类名字。长类名可以用-来间隔。

- 不要使用纯数字，中文等命名，尽量使用英文名来表示。拼音尽量写全程。
- 有一些约定俗成的命名规范：见手则。

###### ③类选择器-多类名

多类名的使用：***class可以调用多个类名，***类名之间必须***用空格***隔开。**有统一属性的（共同 大部分）可以放在同一个类名里，节省代码，方便修改。**

###### ④id选择器

html以id属性来设置id选择器，css中用**#**定义。

id选择器口诀：样式#定义，结构id调用，只能调用一次。

```
<head>
<style>
  #jack {
    color: red;
        }
</style>
</head>
<body>
<div id='jack'>迈克尔·杰克逊</div>
</body>
```

~~id选择器和类选择器的区别：类选择器就好比名字，可以给多个人使用。id选择器就像身份证号码，只能使用一次~~。最大的区别在于使用次数不同。

**类选择器实际中修改样式使用的最多，id选择器一般用于页面唯一元素，与js搭配使用。**

###### ⑤通配符选择器

用 ***** 定义，表示选取页面中所有的标签，统一修改。

```
* {
color： red;
}
```

通配符选择器不需要调用，自动使用。特殊场景才使用。



![image-20230303174437236](C:\Users\Tsing\AppData\Roaming\Typora\typora-user-images\image-20230303174437236.png)

#### 2.3字体属性系列

fonts属性用于定义字体系列，大小，颜色，粗细和文字样式等。

###### 1.font-family属性来定义文本的字体系列

![image-20230303180535445](C:\Users\Tsing\AppData\Roaming\Typora\typora-user-images\image-20230303180535445.png)

###### 2.font-size属性来定义字体的大小

![image-20230303181121767](C:\Users\Tsing\AppData\Roaming\Typora\typora-user-images\image-20230303181121767.png)

标题要单独指定大小。**数字大小后面必须要加px；**

###### 3.font-weight属性来定义文字粗细

实际开发中更提倡用**number**来更改。

400=normal

```
h2{
font-weight: 400;
font-weight: normal;
}
/***上面代表的是一样的意义***/
```

![image-20230303181919889](C:\Users\Tsing\AppData\Roaming\Typora\typora-user-images\image-20230303181919889.png)

###### 4.font-style属性来定义文字样式

![image-20230303182225881](C:\Users\Tsing\AppData\Roaming\Typora\typora-user-images\image-20230303182225881.png)

###### 5.字体复合属性

```
body {
font： font-style font-weight font-size/line-height font-family
}
```

- 简写的方式：必须按照**固定的顺序**写：<u>***字体样式-字体粗细-字体大小/行高-字体名字***</u>
- <u>**必须保留font-size和font-family属性**</u>，否则font属性均不生效。

![image-20230303183052466](C:\Users\Tsing\AppData\Roaming\Typora\typora-user-images\image-20230303183052466.png)

#### 2.4css文本属性

可以定义文本的外观，比如颜色/对齐方式/装饰文本/文本缩进/行间距等。

###### 1.文本颜色

***color***属性用来定义文本的颜色，可以用**颜色英文**（预定义的颜色值）/**十六进制字符**（#ffffff)/**RGB格式**【rgb(255,0,0)】表示。

开发中最常用的是十六进制。

```
div {
  color: red;
}
```

###### 2.对齐文本

***text-align***属性用于设置元素内文本的***水平对齐***方式。left/right/center三个属性。

```
h1 {
 text-align: center;
}
/***本质是让h1盒子里的文字居中对齐***/
```

###### 3.装饰文本

***text-decoration***属性来添加下划线，上划线，删除线等。

```
div {
 text-decoration: none;
}
```

```
a {
text-decoration: none;
}
/*** 取消链接的下划线***/
```

none：默认，没有装饰线，***常用来取消链接a自带的下划线。***

underline：下划线，链接a自带下划线。

line-through：删除线

overline：上划线

![image-20230303184558060](C:\Users\Tsing\AppData\Roaming\Typora\typora-user-images\image-20230303184558060.png)

###### 4.文本缩进

***text-lident***属性指定<u>***文本的第一行缩进***</u>，***通常用于段落首行缩进。***

```
p {
text-indent: 20px;
}
```

**em单位**：相对单位，*<u>**当前元素**</u>*一个文字的大小。若当前元素没有设置大小，会根据父级文字大小显示。

```
p {
text-indent: 2em;
}
/*** 2em表示缩进当前元素两个文字大小的距离 ***/
```

###### 5.行间距

***line-height***属性用于设置行间的距离，可以控制行与行之间的距离。

```
p {
line-height: 26px;
}
```

![image-20230303185450756](C:\Users\Tsing\AppData\Roaming\Typora\typora-user-images\image-20230303185450756.png)

**上间距+文本高度+下间距=行间距**，更改行间距改变的是***<u>上间距和下间距的距离。</u>***

测量工具：FScap/qq截图直接测量。

![image-20230303190407566](C:\Users\Tsing\AppData\Roaming\Typora\typora-user-images\image-20230303190407566.png)

#### 2.5 css引入方式

##### 按照书写的位置，样式表可以分为三类：行内样式表（行内式），内部样式表（嵌入式），外部样式表（链接式）

###### 1.内部样式表（控制一个页面）

写在html内部，单独放在一个<style>标签里。**可以修改当前页面里所有元素的样式。**

![image-20230303191021925](C:\Users\Tsing\AppData\Roaming\Typora\typora-user-images\image-20230303191021925.png)

###### 2.行内样式表（控制一个标签）

在<u>**元素标签**</u>内部的**<u>style属性</u>**中设置css样式，适合做简单修改。<u>**style就等于标签的属性。**</u>

```
<p style="color: red;"> 文字</p>
```

![image-20230303191408791](C:\Users\Tsing\AppData\Roaming\Typora\typora-user-images\image-20230303191408791.png)

###### ※3.外部样式表（控制多个页面）

实际开发中都是外部样式表，适合样式比较多的情况。***<u>核心是：样式单独写在css文件中，将css文件引入html页面中使用。</u>***

***<u>两步：①新建个css样式：style.css （里面只有样式，没有标签）②调用：在html中使用<link>标签来引用文件</u>***

```
<link rel="stylesheet"  href="css文件路径">
```

- rel表示
- 横线标签  <hr>

***<u>实际案例：先写HTML框架，再写css样式。</u>***

### 3.chrome调试工具

![image-20230304151104954](C:\Users\Tsing\AppData\Roaming\Typora\typora-user-images\image-20230304151104954.png)

左边是HTML，右边是css样式

### 4.Emmet语法

前身是zen coding，可以用来提升编写速度。vscode内部已经集成。

#### 快速生成标签

1.标签名+tab键就可以快速生成

2.生成多个标签，加上 * 数字就可以

3.**父子级标签**，用>,比如ul>li，可以快速生成

4.**兄弟关系标签**，用+，比如div+p

5.生成带有类名或者id名字的，直接写.demo **（默认生成一个div ，引用了class=”demo"的类）**或者 #two **（生成引用id为two的）**tab键就可以了。 

【p.demo 】**<u>*tab一下会生成一个带demo类的p标签*</u>**。

6.如果生成的div类名各有顺序，可以用**自增符号$**。

7.生成的标签默认显示几个文字，用div { 文字文字}，会生成<div> 文字文字</div>

#### 快速生成css样式：采取首字母简写的形式，tab快速生成。

eg：***<u>w200 tab一下，会直接生成width: 200px ;</u>***

#### 快速格式化代码（变整洁）：shift+alt+f （右键就有）

![image-20230304152954032](C:\Users\Tsing\AppData\Roaming\Typora\typora-user-images\image-20230304152954032.png)

新版勾选format选项里formatontype:ture 和formatforsave:true 勾上就可以了。

### 5.复合选择器

后代选择器，子选择器，并集选择器，伪类选择器等。复合选择器可以更高效准确的选择标签。

#### 5.1后代选择器

包含选择器，可以选择父元素里的所有子元素。

```
元素1 元素2 {样式声明}
```

**①元素1是元素2的父级**。

eg：

```
ul li {样式声明} /* 选择ul里的所有li标签元素 */
```

②元素1和元素2 用空格隔开，最终选择的是元素2。元素2 只要属于父级里，都可以选择。

Eg：

```
ul li a {样式声明} /*选择ul里的li标签里的a标签元素，只更改a*/
```

③元素1和元素2可以是任意基础选择器。

eg：

```
.nav ul li {样式声明}
/* 类标签里的li*/
<ul class="nav"> 
   <li> 文字文字 </li>
</ul>
```

#### 5.2子选择器

只能选择离某元素***最近的***最近一级子元素

```
元素1>元素2 {样式声明}
```

eg:

```
.nav>a {样式声明}
/* 选择的是第一个a进行修改，p标签里的a不影响*/
<div class="nav"> 
   <a href="#">第一个a</a>
   <p>
      <a href="#"> 第二个a </a>
   <p>
</div>
```

#### 5.3并集选择器

可以选择多组标签，同时定义相同的样式。通常用于集体声明。***<u>用（，）连接。</u>***

```
元素1，元素2 { 样式声明}
```

eg：

![image-20230304155934309](C:\Users\Tsing\AppData\Roaming\Typora\typora-user-images\image-20230304155934309.png)

***并集选择器竖着写***

#### 5.4伪类选择器

给某些元素添加特殊样式，比如给链接添加特殊效果。***用（：）表示***。

常见的链接伪类，结构伪类。

##### 5.4.1链接伪类选择器

![image-20230304160350059](C:\Users\Tsing\AppData\Roaming\Typora\typora-user-images\image-20230304160350059.png)

注意事项：

①为了确保生效，按照LVHA的顺序来声明  **:link -** **:visited** - **:hover** - **:active**

②实际开发中，因为a链接有默认的样式，所以链接要单独指定样式。

③实际开发中的写法。

![image-20230304161530281](C:\Users\Tsing\AppData\Roaming\Typora\typora-user-images\image-20230304161530281.png)

##### 5.4.2   :focus伪类选择器

用于选取获得焦点的表单元素。焦点就是光标，一般情况<input>类表单元素才能获取，因此这个选择器也只针对表单元素来说。

```
input:focus {
  background-color: green;
}
```

![image-20230304162115380](C:\Users\Tsing\AppData\Roaming\Typora\typora-user-images\image-20230304162115380.png)

### 6.css元素的显示模式

html一般分为块元素（独占一行）和行内元素（一行放很多个）两种类型。

#### 6.1块元素

**div是最典型的块元素**

- 独占一行

- 高度/宽度/内外边距都可以设置

- 宽度默认为容器（父级宽度）的100%

- 是一个容器级盒子，里面可以放行内元素和块元素。

***<u>文字类的元素内不可以使用块级元素</u>***，比如<p>标签里不可以再放<div>标签。

#### 6.2行内元素

**span是最典型的行内元素**，也叫内联元素

- 相邻的行内元素可以显示在一行，一行可以显示多个
- 宽度和高度不能直接设置
- 默认宽度就是本身内容的宽度
- ***行内元素只能容纳文本或者其他行内元素***

**<u>链接里不可以再放链接。</u>** **<u> *特殊标签<a>里面可以放其他块级元素，要给<a>转换一下块级模式最安全。*</u>**

#### 6.3行内块元素

**<u><img/> <input/> <td></u>** 同时具有行内元素和块元素的特点。

- 一行可以显示多个元素（行内元素特征），但是每个元素之间有空隙
- 默认宽度就是本身内容的宽度
- 行高，宽度和高度可以设置（块元素特征）

#### 6.4元素显示模式的转换

<a> 元素转换，比如加大a的选择范围

- 转换成块元素： **display:block ;**
- 转换成行内元素：**display:inline ;**
- 转换成行内块元素： **display:inline-block ;**

**案例做法：小米侧边栏**

![image-20230304173410295](C:\Users\Tsing\AppData\Roaming\Typora\typora-user-images\image-20230304173410295.png)

单行文字垂直居中的代码：**文字的行高等于盒子的高度**，就可以垂直居中。