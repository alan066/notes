# 文档内容
1. 学习笔记包括所有基础视频, 以及部分前端工具, 前端工程的视频.
2. 本机环境初始化完成, 并成功运行antd-init创建的demo项目. 所有环境正常. 随附截图.
3. sofamvc环境正常. 随附截图.
4. 其他参考资料阅读: pro-git, 深入浅出node.js, React:引领未来的用户界面开发框架

#  学习笔记

## 基础系列

### Web技术概述

#### Web发展史

互联网诞生-- 1989年
第一个浏览器但是, by Tim Berners-Lee -- 1990.12.25
JavaScript--1995
HTML4标准发布--1997
IE6发布--2001, 95%份额,支持HTML4/CSS2,胜出
Ajax成熟--2005,来着Jesse James Garrett的论文
jQuery--2006
Chrome--2008
HTML5制定完成--2014
未来--基于网络的通用客户端技术,最好的视觉技术,没有之一

> Web技术是一个不断进化的,连接全世界的,符合历史的,通用客户端技术.
> 这是给所有人的.--Tim Berners-Lee 2012伦敦奥运会

#### 前端工作的工作定位
产品需求分解
面向用户编程
基于浏览器编程
视觉还原--1像素都不要差!
交互实现

上接视觉/产品/交互,后依web后端

> 注意:会写前端和写好前端是两码事,前端技术的精进,需要经验的积累和学习能力.

#### Web工作原理,网页渲染模型

<font color=green><b>一个有趣的问题: </b></font>
	从输入URL到网页最终展现,都发生了什么?

参考:
[从输入 URL 到页面加载完成的过程中都发生了什么事情？](http://fex.baidu.com/blog/2014/05/what-happen/)
[What happens when...](https://github.com/alex/what-happens-when)
[现代浏览器的工作原理](http://taligarsiel.com/Projects/howbrowserswork1.htm)

### HTML基础

#### 课程目标

> 1. 掌握HTML语言的基本概念
> 2. 能够正确书写符合规范的HTML代码
> 3. 理解常见的HTML元素
> 4. 掌握属性的正确使用方法，理解常用属性

HTML（Hyper Text Markup Language）是用来描述网页的一种 标记语言，它使用标签来标记描述网页的内容和结构。  
HTML（结构和内容）相当于Model，CSS（展现和样式）相当于View，JavaScript（行为控制）相当于Control，三者构成前端的MVC结构。

#### 语法
<b>HTML元素</b>
* HTML元素是由开始标签、结束标签和中间的内容构成；
* 标签由一对尖括号<>括起；
* HTML元素也有可能没有结束标签，叫做单标签元素。
如：

```
<a href="https://alipay.com">Hello Alipay</a>
<img src="img.png" />
```

<b>HTML属性</b>
* HTML标签可以拥有属性，属性提供了有关HTML元素的更多信息；
* 属性总是以名称/值对的形式出现，比如name="value"；
* 属性总是在HTML元素的开始标签中定义。

<b>HTML编码规范</b>
1. 标签名、属性名要小写；
2. 如果有结束标签就必须带上结束标签；
3. 如果是单标签，建议结束时带上“/”
4. 属性必须写在开始标签中
5. 属性值建议使用双引号，多个属性建议用空格隔开

#### 元素分类

##### 基本HTML
`<!DOCTYPE>` 定义文档类型  
`<html>` 定义一个html文档，是html文档的根节点  
`<title>` 定义文档标题  
`<body>` 定义文档主体  
`<h1> to <h6>` 头部标题标签  
`<p>` 段落标签  
`<br>` 换行标签  
`<hr>` 分割线标签  
`<!-- ... -->` 注释标签  

##### 格式化

`<b>` 加粗  
`<code>` 显示代码  
`<del>` 删除  
`<i>` 斜体  
`<pre>` 按代码中文字格式显示  
`<small>` 小号文字  
`<strong>` 加粗  
`<sub>` 下角标  
`<sup>` 上角标  

> 注意: 不要使用格式化标签来定义内容样式, 请用css来定义内容样式.

##### 表单

表单是用来进行数据交互的. 常用表单元素有:   
`<form>` form表单, 所有其他表单元素都需包含在该元素之内   
`<input>` 输入控件, type类型   
`<textarea>` 可输入多行文字的控件  
`<button>` 可点击的按钮  
`<select>` 下拉菜单  
`<option>` 下拉菜单中的选项, 与select嵌套使用  
`<label>` 输入控件的标签, 用以显示输入的是什么内容   

常用`<form>`属性:

|属性名|属性值|含义|
|:--|:--|:--|
|action| url| 定义提交数据去哪|
|method|get/post|定义发送数据的方式|
|name|text|表单名字|
|target|_blank/_self/_parent/_top|提交数据完成后跳转方式|

input/select/textarea都有的属性:

name  表单提交数据的字段名  
value 表单提交数据的字段值     

常用`<input>`属性:

|属性名|属性值|含义|
|:--|:--|:--|
|checked|checked|type='radio'或type='checkbox'默认选中|
|disabled|disabled|不可用, 表单提交时也不提交数据|
|readonly|readonly|只读, 表单提交时数据提交|
|size|number|设置可见输入字符长度|
|maxlength|number|限制输入字符的最大长度|
|value|text|表单元素提交的数据值|
|type|||
placeholder|text|占位符|

常用type值:

|属性值|含义|
|:--|:--|
|checkbox|多选框|
|file|文件上传控件|
|hidden|不显示的输入框, 表单提交时数据提交|
|password|密码框|
|radio|单选框|
|text|单行输入文字框|

##### 表格

用来展示数据, 表格元素有:

`<table>` 定义一个表格  
`<caption>` 表格标题  
`<th>` 表头单元格  
`<tr>` 表格的一行  
`<td>` 表格单元格  
`<thead>` 表头  
`<tbody>` 表格内容主体  
`<tfoot>` 表脚  
`<col>` 在`<colgroup>`中定义, 用于设置每一列的属性  
`<colgroup>` 把<col>写在其中  

##### 框架

`<iframe>` 如无必须, 不推荐使用

##### 图片

`<img src="img.png" alt="图片" />`

`<canvas>` HTML5标签, 使用JavaScript在这个画板上绘图

##### 多媒体

`<audio>` 播放音频  
`<video>` 播放视频  
`<source>` 设置播放文件源  
`<track>` 设置播放条外观  

> 多媒体元素都是HTML5标签, 使用时注意兼容性

##### 链接

`<a>` 超链接  
`<link>` 常用于外链样式文件, 如  
`<link rel="stylesheet" href="style.css" >`

##### 列表

`<ul>` 无序列表  
`<ol>` 有序列表  
`<li>` 有序和无序列表内的每一项  
`<dl>` 含有描述的列表  
`<dt>` 定义列表的标题  
`<dd>` 定义列表的内容  

如:

```
<ol>
	<li>item1</li>
	<li>item2</li>
	<li>item3</li>
</ol>
<dl>
	<dt>title</dt>
	<dd>description</dd>
</dl>
```

##### 样式和语义化

`<style>` 在html文档中定义样式  
`<div>` 块级元素  
`<span>` 行内元素  

##### 元信息

`<head>` 有关HTML文档本身的信息，与用户所见内容无关的信息在此定义  
`<meta>` 定义HTML文档元信息  

##### 程序

`<script>` 定义客户端使用script语言, 默认为JavaScript  
`<noscript>` 当客户端不支持script语言的时候提示用户的文案  
`<embed>` 引入非HTML的扩展应用, 例如flash  

如:

```
<noscript>你的浏览器不支持脚本!</noscript>
<embed src="http://www.w3schools.com/tags/helloworld.swf" >
```

#### 常用全局属性

|属性|含义|
|:--|:--|
|class|给元素指定一个或多个类名, 一般用于css和js选择器使用|
|id|给元素指定唯一id, 一张页面id唯一|
|style|给元素制定行内样式|
|title|给元素指定扩展信息, 鼠标hover到元素上时才可见|
|data-*|用于存储元素的私有数据|

### CSS基础概述

#### 概述
CSS=Cascading Style Sheets，层叠样式表
文件扩展名.css，也可以直接写在网页内部
CSS是一门标记语言，需要靠记忆和多练习；
CSS还可以用于不同的媒介设备，如打印机、读屏器等。
CSS当前版本是3。

#### 如何引入
外部样式表：以独立文件存在，以link方式引入到html页面中的样式；
内部样式表：在html页面内部，通过`<style></style>`标签包围的样式；
行内样式：在html标签内部，通过标签的style属性定义的样式。
> 注意：`@import url(sample01.css);` 的方式不要使用。因为在一个css里用import导入另一个css的方式需要浏览器不能并行下载css文件，影响页面加载速度。

#### CSS语法

![_E5_B1_8F_E5_B9_95_E5_BF_AB_E7_85_A7_2016-04-09_14.09.57](http://024028.oss-cn-hangzhou-zmf.aliyuncs.com/uploads/antp/fullstack18/05b03f5cfd7192ed5bde9bb732e33ec6/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7_2016-04-09_14.09.57.png)

<b>选择器 {一组声明，以;分割}</b>

选择器：用于选中需要添加样式的目标样式，常用的有类选择器、id选择器、通用选择器、元素选择器。
参见[选择器模型约定](http://www.w3school.com.cn/cssref/css_selectors.asp)

#### 浏览器默认样式
* 浏览器默认给每个元素规定的样式  
如`body{margin:8px}`
* 不同的浏览器的默认样式不一样  
于是需要reset，所以有了：[http://necolas.github.io/normalize.css/](http://necolas.github.io/normalize.css/)
再如支付宝首页的reset

#### 前端：结构、表现、行为的分离
分离是为了更好的维护性，所以推荐使用外部样式表。
<font color=red>那么为什么支付宝首页还是用到了很多内部样式表呢？</font>

### CSS选择器
#### 选择器的种类
| 单一选择器        | 例子           | 描述  |
| :------------- |:-------------| :-----|
| 通用选择器      | * | 选择所有元素 |
| 标签选择器      | p      |   选择所有p元素 |
| 类选择器 | .header      |    选择所有class里包含header的元素 |
| ID选择器      | #logo | 选择id="logo"的元素|
| 属性选择器      | [target=_blank]      |选择所有包含target属性且属性值为_blank的元素|
| 伪类选择器 | a:hover      |    选中hover状态下的a元素 |
> 注意:属性选择器指的是html元素的属性,属性可以随便写. `:hover`表示选中hover状态的任意元素.

| 复合选择器        | 例子           | 描述  |
| :------------- |:-------------| :-----|
| 后代选择器      | div p | 选择所有在div元素内部的p元素|
| 子选择器      | div>p      | 选择所有父元素为div的p元素 |
| 选择器分组 | .header,.footer|选择所有class里包含header或者footer的元素|
| 兄弟选择器      |#logo+p|选择前一个相邻同级元素是id="logo"元素的p元素|
| 组合选择器      | div.nav      |选择所有class包含nav的div元素|
> 注意:注意复合选择器中间的符号,空格,>,逗号,加号,啥都没有

#### 选择器的优先级
单一选择器:id>类=伪类=属性>标签>*
复合选择器:  

| 范例        | style|id|类/伪类/属性 | 标签|*|
| :-- |:--| :--|:--|:--|:--|
| div.nav      |  | 0|1|1|0|
| #head .nav .logo | | 1|2|0|0|
| #a p .info li a:hover | |1|2|3|0|
> 注意:比较方式为从左往右,某一列值高的优先级高,当前列不能区分的继续按照右边的列进行比较. 当选择器的优先级相同时: 后面 > 前面 . `!important`不要用.   
> 纠错1: 优先级 内联式 > 嵌入式 > 外联式  是不对的,嵌入式和外联式的优先级并没有差别,还是要根据上面的公式计算.
> 纠错2:离得越近,优先级越高,也是不对的.

根据id比较,第一个优先级最高,根据类/伪类/属性比较后两个优先级相同,根据标签列比较第三个优先级最高.


#### 设计选择器的最佳实践
1. 最小影响原则  
利用"命名空间"防止影响别人,
别用单一的标签选择器
2. 最短组合原则
<=5
3. 最大重用原则
保证即使html成块移动了,也一样被覆盖到
4. 其他
不要出现两个id选择器的组合
命名语义化

### CSS属性
#### 属性简述
##### 分类
| 定位| 盒模型|字体/文本|其他|
| :-- |:--|:--|:--|
|position<br>left,top,bottom,right,z-index<br><br>float<br>clear<br><br>display<br>visibility<br><br>在哪儿显示|margin<br>border<br>padding<br>width,height<br><br>占多大空间|color<br>font<br>line-height<br>text-xxx<br><br>内容样式|background<br>list-style<br>cursor<br>overflow<br>outline<br><br>杂项|

更多内容: [http://w3school.com.cn/cssref/index.asp](http://w3school.com.cn/cssref/index.asp)


##### 最佳书写顺序

```
{
   /* 定位 */
	display: block;
	float:left;
	/* 盒模型 */
	margin: 10px auto;
	border: 1px solid #eee;
	width: 600px;
	/* 文本/字体 */
	color: #444;
	font-size: 12px;
	line-height: 1.5em;
	/* 其他 */
	background: #fafafa;
}
```

详情请看:[http://www.shejidaren.com/css-written-specifications.html](http://www.shejidaren.com/css-written-specifications.html)

##### 简写

`margin:10px`  
`margin:10px 20px 30px 40px`  
`margin:10px 20px` 表示10px 20px 10px 20px  
`margin:10px 20px 30px` 表示10px 20px 30px 20px  

`font:italic small-caps bold 12px/1.5em arial,verdana;`

font-style: italic;  
font-variant: small-caps;  
font-weight: bold;  
font-size: 12px;  
line-height: 1.5em;  
font-family: arial,verdana;  

详细请看: [http://www.qianduan.net/css-font-shorthand-attribute-handbook/](http://www.qianduan.net/css-font-shorthand-attribute-handbook/)

### CSS属性 - 布局

#### 文档流

块元素: 每个元素占一整行,自上而下  
行元素: 从左向右,排满换行  
注意: 元素的默认样式,行元素的边框效果(和父元素重叠了)  

#### 盒模型

每个元素都可以看成一个盒子.

margin: 外边距  
border: 边框  
padding: 内边距,与内部内容的边距  
content: width/height  

> 注意: 
> 1. 块元素在垂直方向上的margin重叠,重叠时间距不是叠加而是依大的为准. 父子同向margin重叠,父子元素如果都设置了margin,同方向上就会有重叠,以大的为准.
> 2. 行元素的垂直方向属性失效; width失效.

改变显示模式: 使用display
属性值:
<b>block(块元素)</b> 
特点1: 占满父容器的一整行,不会和任何相邻元素共享一行;
特点2: 宽度取决于父级容器,或width设置;
特点3: 具备完整的盒模型.
<b>inline(行元素)</b> 
特点1: 和其他相邻行级元素共享一行,一行排满就换行;
特点2: 宽度取决于内容,设置width无效;
特点3: 盒模型的垂直方向属性无效.
<b>inline-block(行级块元素)</b> 
特点1: 和其他相邻的行级元素共享一行,一行排满就换行;
特点2: 宽度取决于内容,或width设置;
特点3: 具备完整的盒模型.
<b>none(不可见)</b> 
...

> 注意:
> 1. 块元素和行元素属性可以通过设置来改变;
> 2. inline-block的意义在于横向布局;
> 3. 元素的嵌套规则(记住一点:行元素里不能有块元素);
> 4. display:none和visibility:hidden的区别:前者不保留位置,后者保留位置.

#### 定位

位置定位: position
> 配合left,right,top,bottom,z-index来定位

属性值:
<b>static(镜头定位,*默认值)</b>
	特点:设置left,right,top,bottom,z-index无效
<b>relative(相对定位)</b>
	特点1: 相对自己原本的位置偏移,偏移量通过top,left
	,right,bottom定位;
	特点2: 未脱离原先文档流,占据的空间保留,后面的元素不补位.
<b>absolute(绝对定位)</b>
	特点1: 相对外层第一个非static属性的祖先元素的边框内侧,偏移量同上;
	特点2: 脱离原先文档流,占据的空间释放,后面的元素补位.
<b>fixed(固定定位)</b>
	特点1: 相对浏览器窗口定位,偏移量同上;
	特点2: 脱离原先文档流,占据的空间释放,后面的元素会补位.
	
> 注意:
> 1. absolute + margin实现relative效果;
> 2. z-index的使用: 谁覆盖谁. 

浮动定位: float

属性值:
<b>none(默认值)</b>
	特点: 无
<b>left(向左浮动)</b>
	特点1: 浮动在父容器padding以内左上角,(区别于absolute);
	特点2: 自身宽度由内容决定,或width设置,(类似inline-block);
	特点3: 半脱离文档流(会影响其他相邻元素),会影响同一个父容器内其他的行元素的位置. 有完整的盒模型.
<b>right(向右浮动)</b>
	特点: 同上,只是向右浮动.
> 注意:
> 1. 配合使用伪元素`clear`,清除浮动;
> 2. float的意义: 通常也是用来做水平方向的布局,为行元素增加完整盒模型的能力.

### CSS属性 - 内容
#### 字体文本
##### 颜色color
 #ff0000 十六进制,#RRGGBB  
 #f00 十六进制简写  
 red 预定义颜色名  
 rgb(255, 0, 0) rgb值  
 还有rbga,hsl,hsla  
 rbga(255, 0, 0, 0.5) 最后一位是透明度  
 透明: transparent  
 
##### 字体font
`font:italic small-caps bold 12px/1.5em arial,verdana,"Times New Roman";`

font-style: italic;[normal, italic, oblique, inherit]  
font-variant: small-caps;  
font-weight: bold;[100~400(normal)~700~900,normal,bold,bolder,lighter]  
font-size: 12px;[单位: px,em,rem]  
line-height: 1.5em;[单位: px,%,em]  
font-family: arial,verdana;[字体系列]  

px: 像素  
%: 百分比  
em: 相对于当前容器  
rem: 相对于文档根(body)的字体大小  
cm: 厘米,很少用  

> 注意: line-height = 父容器高度可以使文本垂直居中

##### 文本text

text-align: left; [left,right,center]  
text-decoration: normal; [normal, underline, line-though, none] none可以去除链接的下划线  
text-indent: 2em;  

vertical-align: middle; [baseline,top,middle,bottom,...]  

white-space: nowrap; [normal,pre,nowrap,...] p标签里的文字,显示时,默认是没有空格的,`white-space:pre`则原样显示  
word-break: break-all; [normal,keep-all,break-all]  
work-wrap: break-word; [normal,break-word]  

#### 背景background

background: #f00 url(bg.png) no-repeat left top

background-color: #f00;  
background-image: url(bg.png);  
background-repeat: no-repeat; [repeat | repeat-x | repeat-y]  
background-position: left top; [x% y% | 0px 50px | -10px -10px] x轴y轴可取的有  left/right/center,top/bottom/center, 百分比指的是图片的这个百分比的位置与元素的百分比的位置的比较  

#### 列表 list-style

list-style: square inside url('/i/arrow.gif');  

list-style-type: none; [none,disc,circle,square,...]  
list-style-position: inside; [inside, outside]  
list-style-image: url('arrow.gif');  

#### 表格

```
table {
	border-collapse: collapse;
}
```

#### 其他

cursor: pointer; [move | ...]   
如: `button{cursor: pointer;}` 鼠标放上去会变成手  
overflow: hidden; [scroll | visible | ...]  
outline: 10px solid #ff0000; [与border的区别]  
如: `span{outlien:5px solid rgba(255,0,0,0.5)}`,注意并没有改变元素的大小,会覆盖边上的元素  

### CSS进阶
#### CSS兼容性
目标: 让web在不同的场景(设备,浏览器,分辨率)下有更好的体验  
理解: 一致性(感性) >> 渐进增强&优雅降级(理性)  
方法: doctype,hack,浏览器私有属性,响应式  

<!DOCTYPE>
告诉浏览器当前是什么类型的html文档,4.01的时候曾有多种类型: 过渡/严格/框架;  
一定要写,无doctype,IE下启动怪异模式;  
html5:`<!DOCTYPE html>`  

CSS hack: 通过在css生命中添加特殊字符,对不同浏览器做单独声明.  
> 慎用!除非是某个浏览器的可用性问题.

IE条件注释  

```
<!--[if lt IE 9]>
<link rel="stylesheet" href="css/ie9.css">
<![endif]-->
```

[参考](http://www.cnblogs.com/spider518/archive/2011/12/26/2302347.html)

浏览器私有属性  
-moz- firefox  
-webkit- chrome, safari  
-o- opera  
-ms- IE  
因为CSS标准没有定稿...  

响应式  
背景: 智能手机及平板电脑的爆发,屏幕分辨率的泛滥  
争论: 响应vs定制  
思路: 布局响应性 + 组件适应性  
实现: media query  


#### 性能

样式文件  
1. 位置尽量放在<head>里 -- <font color=red>什么情况下不能放在head里?</font>  
2. 至少放在要定义的结构前面 -- 避免内容显示无格式,后闪烁编程有格式  
3. 合并,压缩 -- 减少下载次数, 加快加载时间  

选择器  
查询解析顺序,从又向左,如`#head div`,    
所以少用标签选择器结尾,  
少用后代选择器,多用子选择器,  
减少层级,  
避免冗余, 如`.main p #title{}`  

属性  
多用简写,(减少代码,提高解析性能)  
多利用属性继承,  
背景图片合并(CSS Sprite图片精灵),(减少图片请求次数)  
少用CSS Expression.(CSS Expression在其它浏览器中不起作用，因此在跨浏览器的编码中单独针对IE设置时会比较有用，如果必须使用CSS Expression，一定要记住它们要计算成千上万次并且可能会对你页面的性能产生影响)  

#### 维护性
less, sass  

[http://lesscss.org/](http://lesscss.org/)
[http://sass-lang.com](http://sass-lang.com)

规划: reset, base, layout, mods, components, theme  
避免就一个main.css  
按页面分文件,公用的部分提出来  

库: bootstrap, BUI, xmixins  

#### CSS3

常用CSS3属性:  
圆角 border-radius:100px; (四个参数,顺时针顺序)  
投影 box-shadow:2px 10px 10px 0px #999   
变换 transform:rotate(90deg);  
过渡 transition:all 1s ease-out 0s;  
动画 animation: move 2s ease-out infinite alternate;  

```
@keyframes move{
		from{margin-top:0px;}
		to{margin-top:100px;}
}
```

透明度 opacity:0.4;

### CSS布局实战

实践知识点
	语义化html  
	盒模型  
	文档流  
	选择器  
	浮动  
	绝对定位  
	栅格化  
	
从零开始搭建一个静态网页
	搭建html结构  
	观察文档流  
	样式reset  
	两栏布局  
	栅格化  
	侧边菜单细化  
	练习  

执行完成这个实例:  
`http://site.alipay.net/xingmin.zhu/front-end-basic/demo`  
个人感觉: 反复多来几次, 敲多了会熟悉起来, 否则理解+记忆当时是可以了,过几天都是要忘掉的.

学习CSS布局  
[http://zh.learnlayout.com](http://zh.learnlayout.com)
	
## 前端工具

### 开发者调试工具

工作中, 经常使用chrome的开发者工具  
Mac下快捷键: option + command + i  

### http代理

http代理在用户和目标服务器中间做中转站,可以监听用户网络请求,修改和发送网络请求等.

#### Charles

是一款功能强大的http代理调试软件,跨平台,windows/osx/linux  
主要功能:  
	记录网络请求  
	带宽调节/带宽模拟  
	断点工具  
	SSL代理  
	反向代理   
	端口转发    

<b>常用功能</b>  
	手机代理  
	远程代理  
	本地代理  
> Response乱码时添加: -Dfile.encoding=UTF-8  
	
> Fiddler适合windows使用

#### 其他

Chrome的Network: 捕获,重发  
Firefox的网络: 捕获,修改,重发  
IE的网路: 捕获  

### 构建类工具

#### 概述

前端自动化构建  
打包  
压缩  
图片合并  

#### Gulp

一种前端自动化工具,高效,易用,插件易开发.  
安装node.js -> 安装`npm install -g gulp`  

#### 使用gulp

gulp.src(globs[.options]) 通过输入的字符串或数组查询文件并且返回对应文件流以便后续pipe方法调用插件.

gulp.dest(path[,options]) 会将通过pipe方法处理完成后的文件进行处理以后写入path制定的文件中,可以指定多个文件,当文件目录不存在时会自动创建.

gulp.task(name[, deps], fn) 定义一个task, deps会在task执行之前执行.

示例:
gulpfile.js

```
var gulp = require('gulp');
var spriter = require('gulp-css-spriter');
var minify = require('gulp-minify-css');
gulp.task('css', function() {
	return gulp.src('./src/styles.css')
		.pipe(spriter())
		.pipe(gulp.dest('./_dist/css'))
		.pipe(minify())
		.pipe(gulp.dest('./dist/css'));
});
gulp.task('sayhi', function() {
	console.log('hi');
});
gulp.task('default', ['sayhi'], function(){
	console.log('test');
});
var watcher = gulp.watch('./src/styles.css',['css']);
gulp.watch('./src/styles.css', function() {
	console.log(1);
});
watcher.on('change', function(){
	console.log('css changed');
});
```

<b>gulp常用插件</b>
gulp-uglify js混淆压缩
gulp-minify-css 压缩css
gulp-htmlmin 压缩html
imagemin 压缩图片
gulp-jslint 代码质量检查

#### 其他工具
Grunt
Spm
Fis -- 百度的,呵呵
等等

### PS及图片的合并压缩

#### PS简介

常用功能切图/取色

#### 常用的PS快捷键

command/control + +/- 放大/缩小  
tab工作区切换  
按住空格,拖动文件  
按F 标准屏幕模式/带有菜单栏的全屏模式/全屏模式切换  
按I 进入吸管模式,选取颜色  
按T 进入文字模式  
按C 进入切片模式  


#### 切图

这个很有用...

#### 图片格式

|格式|压缩模式|交错支持|透明支持|动画支持|缺点|
|:--|:--|:--|:--|:--|:--|
|PNG|无损压缩|支持|支持|不支持|压缩图片大|
|JPG|有损压缩|支持|不支持|不支持|图像质量损失|
|GIF|微损压缩|支持|支持|支持|色域有限,最多256色|

JPG: 图片中有人物,风景时使用  
PNG: 适合存储大块颜色相近区域以及亮度差异十分明显的图片  
PNG-8: 适合色彩颜色较少的图片,最多支持256色  
PNG-24: 适合色彩较多的图片,支持1600万色  
GIF: 和PNG类似, 最多支持256色  

#### iconfont

用字体文件取代图片文件  
好处:矢量图标, 便于修改, 兼容性好, 文件小, 支持CSS3效果.  
阿里自己的[矢量图标库](www.iconfont.cn)  

#### 合并图片

为什么做图片合并?  
	减少页面请求  
	降低图片占用  
我们的做法:自动化构建, 如compass,css-spriter等  

#### 图片压缩

ImageOptim [下载地址](https://imageoptim.com/)  
jpegtran windows平台工具,[下载地址](http://jpegclub.org/)  
gifsicle 命令行工具,[下载地址](http://www.lcdf.org/gifsicle/)  
PngOptimizer [下载地址](http://psydk.org/pngoptimizer)  
optipng windows平台工具,[下载地址](http://optipng.sourceforge.net/)  

### JavaScript基础

#### 背景知识

1994年在Netscape公司的Navigator浏览器上诞生;  
1997年提交ECMA制定标准,称为ECMAScript(...ES5,ES6...);  
借鉴了C语言的基本语法;  
借鉴了Java语言的数据类型和内存管理;  
借鉴scheme语言,将函数提升到"第一等公民"的地位;  
借鉴self语言,使用基于原型(prototype)的继承机制.  

#### JavaScript的引入方式

内嵌式

```
<script type="text/javascript">
	console.log('hi');
</script>
```

外链式 -- 推荐  

```
<script src="xxx.js"></script>
```

标签式 -- 禁用  

```
<input type="button" value="button" onclick="return console.log('clicked')" />
```

#### 语法基础

##### 数据类型

标识符  
	* 第一个字符必须是字母,下划线或美元符号$;其他字符可以是字母,下划线,美元符号或数字;不能用关键字/保留字作为变量;  
	* 标识符区分大小写;  
	* 弱类型变量  `var`;  
	* 使用var关键词定义,如果不使用var显示声明变量将会在顶层域上创建变量;  
	* 变量的初始值是undefined.  
	
参考:  
[关键字](http://www.w3school.com.cn/js/pro_js_keywords.asp)  
[保留字](http://www.w3school.com.cn/js/pro_js_reservedwords.asp)

基本数据类型

* undefined

任何没有被赋值的变量都有undefined值,5种情况下会出现undefined值:  
1. 使用var关键字声明的变量,但是没有赋值;  
2. 没有赋值的属性;  
3. 没有返回值的函数;  
4. 没有传值函数的参数;  
5. 主动赋值undefined.  

* null  

null类型只有一个值null,表示空对象指针.一般当声明一个变量准备在将来保存对象,那就初始化为null. 如 `var obj = null`.

* Boolean

1. 两个值: true,false.  
2. 类型转换方法: !!, Boolean().  

|数据类型|转换为true的值|转换为false的值|
|:--|:--|:--|
|Boolean|true|false|
|String|任何非空字符串|""(空字符串)|
|Number|任何非零数字值(包括无穷大)|0和NaN|
|Object|任何对象|null|
|undefined||undefined|

如:

```
var str='a';
!!str;//true
Boolean(str);//true
Boolean("");//false
```

* String

1. 使用0到多个16位的Unicode字符表示;  
2. 无固定大小;  
3. 字符串字面量是由双引号或单引号声明的,我们规范要求使用单引号. 如 `var str='hell js';`  
4. String对象内置多个常用方法,[参见](http://www.w3school.com.cn/jsref/jsref_obj_string.asp)  
5. 转换为字符串类型: toString()方法,除null和undefined之外,任何一个值都有这个方法; String(),如果值有toString()方法则调用该方法(不带参数),如果值是null则返回"null",如果值是undefined则返回"undefined".  

* Number

> 注意: IEEE754标准来表示(双精度64位)精度不高

1. 整数  

```
var intNum = 55;// 十进制
var octalNum = 079;// 八进制
var hexNum = 0xa;// 十六进制
```
 
2. 浮点数  

```
var floatNum1 = 1.1;
var floatNum2 = 3.2e2;// 科学计数法320
```

3. NaN(Not a Number)  

是一个特殊的值,表示非数值;NaN不等于任何值,包括自身;isNaN()可以用来判断当前参数是否是NaN非数值.
引用类型.

4. 转换为number, 推荐parseInt(), parseFloat(). 不推荐Number(). Number()的转换规则如下:

|被转换数据类型|规则|
|:--|:--|
|Boolean|true:1, false:0|
|Null|0|
|Undefined|NaN|
|String|1.只包含合法数值,转换为十进制数值,忽略前导0<br>2.空字符串变成0<br>3.除此之外的字符串都是NaN|
|Object|同上|

* Object

对象: 一组数据和功能的集合,key/value的无序集合. 所有对象都由Object继承而来, Object对象中的所有属性和方法都会出现在其他对象中.  

常用方法/属性:  

`constructor
prototype
hasOwnProperty()
toString()
valueOf()`

* Array

保持数据的有序列表. 数组上的每一项可以保存任何数据,数组是可以动态调整的.  
`new Array()`或字面量方式声明数组,推荐使用后者.  
常用方法: join()  
[参见](http://www.w3school.com.cn/jsref/jsref_obj_array.asp)

* Date

设置,获取时间的方法: `getDate(), getDay(), getMonth(), getFullYear(), setDate()`  
[参见](http://www.w3school.com.cn/jsref/jsref_obj_date.asp)

* Function
* RegExp

两种声明语法
1. `/pattern/flags    // 直接量语法`   
2. `new RegExp(pattern[, flags])     // 创建RegExp对象的语法`   

如:

```
var reg = /\d/g;
var reg2 = new RegExp("\\d", "g");  // 和/\d/g等价
var str = 'e';
reg.test(str); // false
```

常用支持正则表达式的String对象的方法有: 

|方法|描述|
|:--|:--|
|search|检索与正则表达式相匹配的值|
|match|找到一个或多个正则表达式的匹配|
|replace|替换与正则表达式匹配的子串|
|split|把字符串分割为字符串数组|

如:

```
var str='abc';
str.replace(/a/g, 'alipay');  // alipaybc
```

[参考](http://www.w3school.com.cn/jsref/jsref_obj_regexp.asp)

* String
* Number
* Boolean  

> 基本类型的变量存储的是简单的数据段,引用类型存储的是指向引用对象的引用.


##### 运算符

typeof operand

|Type|Result|
|:--|:--|
|undefined|"undefined"|
|null|"Object"|
|Boolean|"boolean"|
|Number|"number"|
|String|"string"|
|Symbol(new in ECMAScript 6)|"symbol"|
|Host object(provided by JS environment)|Implementation-dependent|
|Function object(impelments [[Call]] in ECMA-262 terms)|"function"|
|Any other object|"object"|

操作符
一元操作符 `++,--,-,+`  
位操作符 `~,&,|,^,<<,>>,>>>`  
布尔操作符 `!,&&,||`  
乘性操作符 `*,/,%`  
加性操作符 `+,-`  
关系操作符 `<,>,<=,>=`  
相等操作符 `==,!=,===,!==`  
> 注意: `==, !=`会执行类型转换,禁止使用. 推荐使用全等`===, !==`. 如 
> `var a = '5';
> var b = 5;
> a == b; // true
> a === b; // false`

条件操作符 ` ? : `  
赋值操作符 `=, *=, /=, %=, +=, -=, <<=, >>=`  
逗号操作符 `,`   

##### 控制语句
`if
while
for
for in
switch
break, continue
do-while // 不推荐
with // 禁止
label // 禁止`

##### 函数

声明式声明   
`function fn(arg0, arg1, ... argN) {
	statements
}`

函数表达式声明   
`var fn = function(arg0, arg1, ... argN) {
	statements
}`

推荐: 先声明后使用

函数的参数  
1. 没有参数类型;  
2. 按值传递;  
3. 函数不介意传递近来多少个参数, 也不在乎传进来是什么类型, 也就是说即便你定义的函数只接收两个参数, 在调用这个函数时也未必一定要传递两个参数, 可以传递一个, 三个, 甚至不传递参数, 而解析器不会报错.

在ES内部函数是使用数组表示的, 定义的形参只是这个数组对应项的一个别名. 如:

```
function say(){
	console.log('hello' + arguments[0] + arguments[1]);
}
```

4. 使用return语句返回返回值, return语句之后的代码不会执行, 不定义return语句默认返回undefined.

##### 其他内置对象

Math [参见](http://www.w3school.com.cn/jsref/jsref_obj_math.asp)
全局函数 [参见](http://www.w3school.com.cn/jsref/jsref_obj_global.asp)

学习资料:
[W3C](http://www.w3school.com.cn/js/index_pro.asp)
[Mozilla Developer](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

### JavaScript进阶

#### 对象

读取属性,调用方法,设置属性值  
"."操作符,"[]"操作符都可以, 后者的优势是支持表达式.

添加属性, 直接
`obj.attr = 'a';`即完成添加属性attr到对象obj

删除属性  
`delete obj.hello;
delete obj['hello'];`

#### this

<font color=red>this是函数的隐含参数, 在js中this指向函数执行时的当前对象.</font>

严格模式下,this的默认值是undefined. 因为不是对象方法就会属于全局对象,而严格模式下全局对象是取不到的,如:

```
function bankCard() {
	'use strict';
	return this;
}
bankCard() === undefined;// true
```

对象方法: this指向该方法所在的对象.

```
var obj = {
	method : bankCard;
};
obj.method() === obj; // true
```

<b>this改变</b>

```
var work = {
money : 9999,
goodJob: function() {
   return ++this.money;
}
};
var func = work.goodJob;
func(); // NaN, 因为此时this指向全局对象
work.goodJob(); // 10000
```
 
 有时, 我们会只用self暂存this, 如:
 
```
var nameObj = {
name:'tom',
showName: function() {
    console.log(this.name);
},
waitShowName: function() {
    var self = this;
    this.showName();
    setTime(function() {
        self.showName();
    }, 1000);
}
};
nameObj.waitShowName(); // 不暂存直接调用会报错
```
 
#### 原型

每个js函数都有prototype属性, 这个属性引用了一个对象, 这个对象就是原型对象.
原型对象初始化的时候是空的, 我们可以在里面自定义任何属性和方法, 这些方法和属性都将被该构建函数创建的对象继承.

1. 实例就是通过构造函数创建的. 实例一创造出来就具有constructor属性(指向构造函数)和_proto_属性(指向原型对象);  
2. 构造函数中有一个prototype属性,这个属性是一个指针,指向它的原型对象;  
3. 原型对象内部也有一个指针(constructor属性)指向构造函数;  
4. 实例可以访问原型对象上定义的属性和方法.  

例子参加下 构造函数.

#### 构造函数

```
function Company(name) {
	this.name = name;
}
Company.prototype.showCompany = function() {
	console.log(this.name);
}
var alibaba = new Company('alibaba');
alibaba.showCompany();
```

#### 原型链

![_E5_B1_8F_E5_B9_95_E5_BF_AB_E7_85_A7_2016-04-10_15.45.07](http://024028.oss-cn-hangzhou-zmf.aliyuncs.com/uploads/antp/fullstack18/4335fe68f1173f1e1431b52d025fe79f/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7_2016-04-10_15.45.07.png)

```
// 构造方法1
function Company(name) {
    this.name = name;
}
// 往原型对象里添加方法
Company.prototype.showCompany = function () {
    console.log(this.name);
}
// 构造方法2
function Alibaba(name) {
    this.name = name;
}
// 指定原型对象
Alibaba.prototype = new Company();
// 指向正确的构造方法
Alibaba.prototype.constructor = Alibaba;
// 重写原型里的某个方法
Alibaba.prototype.showCompany = function () {
    console.log('上市公司' + this.name);
};
var taobao = new Alibaba("淘宝");
taobao.showCompany();
var alipay = new Company("支付宝");
alipay.showCompany();
```

#### 作用域

JS的作用域链.  
函数体内部, 局部变量的优先级比同名的全局变量高.  
JS没有块级作用域.  
未使用var关键字定义的变量都是全局变量.  
全局变量都是全局对象的属性.  

#### 闭包

闭包(closure) 是指有权访问另一个函数作用域中的变量的函数.

创建闭包最常见的方式就是在一个函数内创建另一个函数, 通过另一个函数访问这个函数的局部变量.  
一般函数执行完毕后, 局部活动对象就被销毁, 内存中仅仅保存全局作用域. 使用闭包可以把全局变量驻留在内存中, 成为封装的局部私有变量.  

闭包实例

```
function getAntStaffNum() {
    var staffNum = 5000;
    return function () {
        staffNum++;
        console.log("ant staff Num is " + staffNum);
    }
}
var antStaffNum = getAntStaffNum();
antStaffNum(); // 5001
antStaffNum(); // 5002
```

### jQuery和DOM编程

#### jQuery

##### 使用jQuery库

通过`<script>`标签引入jQuery库

##### Document.ready

Running Code Unobtrusively When the DOM is Ready.

首先要了解"document ready" handler的概念, 代码初始化部分应该交由这部分处理, 它实现了两个功能: 代码在DOM没有完全生成前是不执行的; 确保js代码中访问的元素已生成.  

##### 链式调用


##### jQuery选择器

选择器兼容所有css选择器(包含CSS3), 方法是`$('')`

##### 控制CSS

使用jQuery可以添加/删除和切换class属性,如

```$('div').addClass('content');
$('div').removeClass('content');
$('div').toggleClass('content');
```

##### DOM操作

jQuery里面有大量的操作页面元素的方法,包括操作元素的内容,如  

`.html()
.text()
.heml('new content')`

附加内容到元素, 增加到元素闭合标签之前. `append('append html')`

在元素指定位置插入内容.  

`appendTo()
prepend()
prependTo()
before()
insertBefore()
after()
inserAfter`


##### 事件绑定

`$('selector').on(events, handler)`

常用的UI事件  

`blur focus click
keydown keyup keypress
mouseenter moseleave
chage
scroll`

##### 显示效果

动画:元素显示/隐藏  

`show
hide
toggle`

`fadeIn
fadeOut`

`slideUp
slideDown`

##### jQuery.ajax

Ajax: Asynchronous JavaScript And XML  
诞生于2005年的一篇论文`Ajax: A New Approach to Web Applications by Jesse James Garrett`

一个基本的ajax请求的例子:

```
$.ajax({
	url: 'https://ali.github.com/',
	methos: 'get'
}).done(function(data){
	console.log('data ==========>', data);
});
```

##### 完成一个简单的交互效果

很简单, 就不赘述了.

### JavaScript实战

#### Ajax

一个原生态的ajax请求示例

```
var api = 'https://api.github.com/users/xudafeng';
var xmlHttp = new XMLHttpRequest();
xmlHttp.open('GET', api, true);
xmlHttp.onreadystatechange = function(data) {
	if(xmlHttp.readyState == 4) {
	    console.log(xmlHttp.responseText);
	}
};
xmlHttp.send(null);
```

jQuery

```
var api = 'https://api.github.com/users/xudafeng';
$.ajax({
	method: 'GET',
	url: api,
	data: {
		foo: 'bar'
	}
}).done(function(msg) {
	console.log(msg);
});
```

#### JSON

JavaScript Object Notation
[JSON官网](www.json.org)

JSONP (JSON with Padding): script tag, javascript callback.
由于同源策略的限制, 跨域请求的时候将用到JSONP. JSONP的本质是从服务端返回了一段js代码.

#### event

基于事件驱动的编程. 这里的事件不是DOM事件, 指的是基于事件编程模式, 本质上类似publish/subscribe.

#### 模块化编程

无模块化时代  
ajax出现之前, js还只是一种"玩具语言", 代码简单的堆在一起, 能执行就可以了.  

模块萌芽  
ajax使得传统网页向"富客户端"发展, 前端的业务逻辑越来越多, 代码也越来越多, 于是一些问题就暴露了出来:  
1. 全局变量灾难  
2. 函数命名冲突  
3. 依赖关系不好管理,引入script需要按照顺序引入  

这个阶段的解决方案主要有:  
1. 用自执行函数来包装代码  

如: 

```
var = function() {
	var a,b; // 变量a,b外部不可见
	return {
		add : function(c) {
			a + b + c;
		},
		format : function() {
			// ....
		}
	}
}();
```

这种方法隐藏了局部变量, 达到了封装的目的, 可是随着模块的增多, 全局变量还是会越来越多.

2. java风格的命名空间, 如`app.util.modA = xxx;`  
Yahoo的YUI早期就是这么做的, 类似`app.tools.modA.format();`这么调用, 写写都让人心累.

3. jQuery风格的匿名自执行函数, 如

```
(function(window){
	window.jQuery = window.$ = jQuery;// 通过给window添加属性而暴露到全局
})(windows);
```

这种风格灵活了很多, 如果需要添加扩展, 这作为jQuery的插件把它挂到$上即可. 然后这并没有从跟不上解决问题, 所需依赖还是需要外部提前提供, 还是增加的全局变量.


随着nodejs的出现, 服务端js编程不能没有模块化, CommonJs社区制定了Modules/1.0规范([http://wiki.commonjs.org/wiki/Modules/1.0](http://wiki.commonjs.org/wiki/Modules/1.0)), 主要内容有:
>1. 模块的标识应遵循的规则（书写规范）
2. 定义全局函数require，通过传入模块标识来引入其他模块，执行的结果即为别的模块暴漏出来的API
3. 如果被require函数引入的模块中也包含依赖，那么依次加载这些依赖
4. 如果引入模块失败，那么require函数应该报一个异常
5. 模块通过变量exports来向往暴漏API，exports只能是一个对象，暴漏的API须作为此对象的属性。

遵循该规范的代码类似:

`//math.js`

```
exports.add = function() {
    var sum = 0, i = 0, args = arguments, l = args.length;
    while (i < l) {
        sum += args[i++];
    }
    return sum;
};
```

`//increment.js`

```
var add = require('math').add;
exports.increment = function(val) {
    return add(val, 1);
};
```

`//program.js`

```
var inc = require('increment').increment;
var a = 1;
inc(a); // 2
```

当然, 这个模块化规范并不适用于浏览器, 因为外层没有function包裹, 变量全暴露在全局; 资源加载方式不适合浏览器环境, 为此参数了以下规范:   

AMD(Asynchronous Module Definition)规范  
Modules/Transport  
Modules/Wrappings  
来自淘宝的CMD/seajs(Common Module Definition)规范  
以及还在制定中的ES6模块标准  

最后, 有了模块化, 自然需要一款模块依赖管理和打包的工具 -- webpack, 参见官网[webpack.github.io](http://webpack.github.io)


#### 代码风格

参考
[https://github.com/felixge/node-style-guide](https://github.com/felixge/node-style-guide)
[https://github.com/airbnb/javascript](https://github.com/airbnb/javascript)

### React入门

<b>包含</b>
是什么
为什么
怎么用
搭建示例应用

<b>不包含</b>
生态圈/公用组件
应用框架
编译/合并代码

#### 是什么
react是一个专注于做UI的底层库, 是个工具, 具体来说是做UI组件的库, 专注于做MVC中的v.

一个简单的react组件

```
var Hello = React.createClass({
	render: function() {
		return <div>Hello {this.props.name}</div>
	}
});
React.render(<Hello name="world" />, document.getElementById('container'));
```

用状态控制组件的变化, 可以把一个组件看做一个状态机, 每一次状态对应于组件的一个UI.

#### 为什么选择react?

api少, 类库易学;
组件内聚, 易于组合;
原生组件和自定义组件融合渲染;
状态/属性驱动全局更新, 不用关注细节更新;
commonjs生态圈/工具链完善.

#### 基础知识

##### jsx

类似xml的语法, 用来描述组件树

```
<div className="x">
	<a href="#">#</a>
	<Component x="y">1</Component>
</div>
```

```
React.createElement('div', {
className:'x'
},[
React.createElement('a', {href: '#'}, '#'),
React.createElement(Component, {x: 'y'}, 1);
]);
```

jsx嵌入变量: 可以通过{变量名}来将变量的值作为属性值

```
var x = 'http://www.alipay.com';
var y = <a href = {x} target="_target">alipay.com</a>;
React.render(y, document.getElementById('container'));
```

jsx spread: 可以用通过{...obj}来批量设置一个对象的键值对到组件的属性, 注意顺序

```
var x = 'http://www.alipay.com';
var obj = {
	href:"http://www.taobao.com",
	target:"_target"
}
var y = <a {...obj} href = {x}>alipay.com</a>;
React.render(y, document.getElementById('container'));
```

props: 通过this.props可以获取传递给该组件的属性值, 还可以通过定义getDefaultProps来指定默认属性值

```
var B = React.createClass({
	getDefaultProps(){
		return {
			title:'default'
		};
	},
	render(){
		return <b>{this.props.title}</b>
	}
});
React.render(<div>
<B title="指定  " /><B /></div>, document.getElementById('container'));`

prop validation: 通过指定propTypes可以校验属性值的类型
`var B = React.createClass({
    propTypes: {
        title: React.PropTypes.string,
    },
    getDefaultProps(){
        return {
            title: 'default'
        };
    },
    render(){
        return <b>{this.props.title}</b>
    }
});
React.render(<div>
<B title="指定..." /> <B title={2} />
</div>, document.getElementById('container'));
```

> 校验仅为提升开发者体验

state: 组件内部的状态,可以使用state

```
var Timer = React.createClass({
    getInitialState: function () {
        return {secondsElapsed: 0};
    },
    tick: function () {
        this.setState({secondsElapsed: this.state.secondsElapsed + 1});
    },
    componentDidMount: function () {
        this.interval = setInterval(this.tick, 1000);
    },
    componentWillUnmount: function () {
        clearInterval(this.interval);
    },
    render: function () {
        return (
            <div>Seconds Elapsed: {this.state.secondsElapsed}</div>
        );
    }
});
React.render(<Timer />, document.getElementById('container'));
```

##### event 事件

可以通过设置原生dom组件的onEventType属性来监听dom事件, 例如onClick,onMouseDown, 在加强组件内聚性的同时, 避免了传统html的全局变量污染

```
var likeButton = React.createClass({
    getInitialState: function () {
        return {liked: false};
    },
    handleClick: function (event) {
        this.setState({liked: !this.state.liked});
    },
    render: function () {
        var text = this.state.liked ? 'like' : 'haven\'t liked';
        return (
            <p onClick={this.handleClick}>
                You {text} this. Click to toggle.
            </p>
        );
    }
});
React.render(<LikeButton />, document.getElementById('container'));
```

##### composition 组合

可以像使用原生dom组件一样使用自定义的组件. 而且react也不能继承.

```
var A = React.createClass({
    render() {
        return <a href='#'>a</a>
    }
});
var B = React.createClass({
    render() {
        return <i><A /> !</i>
    }
});
React.render(<B />, document.getElementById('container'));
```

组合children: 自定义组件中可以通过this.props.children访问自定义组件的子节点

```
var B = React.createClass({
    render(){
        return <ul>
            {React.Children.map(this.props.children, function (c) {
                return <li>{c}</li>;
            })}
            </ul>;
    }
});
React.render(<B>
<a href='#'>1</a>
2
</B>, document.getElementById('container'));
```

##### props/state



##### mixin

mixin是一个普通对象, 通过mixin可以在不同组件间共享代码.

```
var mixin = {
    propTypes: {
        title: React.PropTypes.string,
    },
    getDefaultProps(){
        return {
            title: 'default'
        };
    }
};
var A = React.createClass({
    mixins: [mixin],
    render(){
        return <i>{this.props.title}</i>
    }
});
var B = React.createClass({
    mixins: [mixin],
    render(){
        return <b>{this.props.title}</b>
    }
});
React.render(<div>
<B /> <A title={2} />
<A />
</div>, document.getElementById('container'));
```

##### form

和html的不同点:

###### value/checked属性设置后, 用户输入无效;

controlled components受控组件: 如果用户设置了value属性, 那么该组件变为受控组件, 用户无法输入, 除非程序改变value的只, 此时可以通过监听onChange事件结合state来改变input的值.

```
var Test = React.createClass({
    getInitialState(){
        return {
            value: 'xadfasdaf'
        };
    },
    onChange(e){
        this.setState({
            value: e.target.value
        });
    },
    render(){
        return <input value={this.state.value} onChange={this.onChange} />
    }
});
React.render(<Test />, document.getElementById('container'));
```

设置defaultValue为设置input的初始值, 之后input的值由用户输入. 但是不推荐这样做, 因为后续输入值就不受控制了.

```
var Test = React.createClass({
	render(){
		return <input defaultValue="xyz" />
	}
});
React.render(<Test />, document.getElementById('container'));
```

###### textarea的值要设置在value属性;
###### select的value属性可以是数组, 不建议使用option的selected属性;
###### input/textarea的onChange用户每次输入都会触发(即使不丢失焦点);
###### radio/checkbox点击后触发onChange.

##### refs

该功能是为了结合现有非react类库, 通过ref/refs可以取得组件实例, 进而取得原生节点.

```
var Test = React.createClass({
	componentDidMount(){
		alert(React.findDOMNode(this.refs.content).innerHTML);
	},
	render(){
		return <div>
				<h3>header</h3>
				<div ref='content'>content</div>
			</div>;
	}
});
React.render(<Test />, document.getElementById('container'));
```

##### component api

React.createClass定义组件时允许传入的配置:  
getDefaultProps得到默认属性对象;  
propTypes属性检验规则;  
mixins组件间公用方法, 定义等.  

component lifecycle组件生命周期:  
React.createClass定义时允许传入的函数, 会在特定生命周期内调用.  

<b>初次创建组件时调用</b>  
getInitialState 得到初始状态对象;  
render 返回组件树, 必须设置;  
componentDidMount渲染到dom树中时调用, 只在客户端调用, 可用于获取原生节点.  

<b>组件的属性值改变时调用</b>  
componentWillReceiveProps 属性被改变前调用;  
shouldComponentUpdate 判断是否需要重新渲染;  
render 返回组件树, 必须设置;  
componentDidUpdate 渲染到dom树中时调用, 可用于获取原生节点.  

最后是componentWillUnmount 组件从dom销毁前调用.  

##### top api

顶层api有:  
React.createClass 创建组件类  
React.findDOMNode 从组件实例获取dom根节点   
React.render 渲染组件到dom  
React.Children.* 操作map/forEach children工具类  

#### 一步步搭建一个评论应用

组件分解   

```
顶层CommentBox
	评论列表CommentList
		单条评论Comment
	评论表单CommentForm
```

[参考](http://reactjs.cn/react/docs/tutorial.html)

	
#### 作业

实现一个checkbox

功能点:  
新生成组件/更新组件;  
checked/unchecked交互处理;  
键盘;  
label?  

作业完成:

```
// 创建一个checkbox
var Checkbox = React.createClass({
  getInitialState(){
    return {
      checked: ''
    };
  },
  onChange(e){
    this.setState({
      checked: this.state.checked == 'checked' ? '' : 'checked'
    });
  },
  render(){
    return <input type="checkbox" checked={this.state.checked} onChange={this.onChange} />
  }
});
React.render(<Checkbox />, document.getElementById('container'));
```

### React进阶

#### 生态圈

安装nodejs  
使用npm, tnpm

安装生态圈模块

`npm install xx
tnpm install yy
tnpm install @your-company/xx`

#### 开发工具

组件开发:  
`tnpm install yo generator-rc -g`

项目开发:  
`tnpm install antd-init -g`

#### 如何开发一个组件

> 课程暂不讲授

#### 如何开发项目

纯前端项目  
`antd-init`

所有界面都是js写了, 主要就是一个src文件夹.

`npm start` 启动   
`npm run build` 打包, 一般不用手动build   
`tnpm install jquery --save` 安装需要的插件并添加引用   
antd[文档](http://ant.design/)

开发者工具调试源码: sources>webpack>App.jsx

CHAIR   
`tnpm install chair-init -g
chair init --type react test`

ROUTER客户端路由   
demo:[learning-react/react-router](http://yiminghe.me/learning-react)
[https://github.com/yiminghe](https://github.com/yiminghe)   
`复杂的"多页面"实际上都是一个单页面的应用`

用到的文件里写Link, 如    

```
import { Link } from 'react-router';
<Link to="/about">关于</Link>
```

然后在入口文件配置路由, 如     

```
import '../common/lib';
import App from '../component/App';
import ReactDOM from 'react-dom';
import React from 'react';
import About from '../component/About';
import {Router, Route, browserHistory} from 'react-router';


var mountNode = document.getElementById('react-content');


React.render(<App />, mountNode);

const router = (

  <Router history={browserHistory}>

    <Route path="/" component={App} />
    <Route path="/about" component={About} />

  </Router>

);

React.render(
  router,
  mountNode
);

```
## 前端工程

### uisvr使用指南

#### 概述

uisvr是sofamvc中提供的一种前后端分离的解决方案. 
  
前后端分离:  
前端专注于页面的渲染和交互逻辑, 后端专注于业务以及数据的处理.  

为什么需要前后端分离:  
日积月累混杂的前后端代码难以维护  
不易于前后端开发人员的合作  

uisvr的解决方案:   
在物理层面上隔离前后端的代码, 通过约定及一些配置进行关联.   

|目录结构|sofa3|sofa4|
|:--|:--|:--|
|uisvr根目录|htdocs|webroot|

|uisvr的目录结构|sofa3|sofa4|
|:--|:--|:--|
|静态文件目录|htdocs|public|
|模板目录|templates|view|
|配置目录|uisvr|uisvr|

UISVR 是 sofamvc 的一个组件，提供一种方式可解耦静态文件和模板，同时能够更好的组织页面。

在做一个站点的时候势必会将公用的文件抽出来避免代码冗余，其中抽出头尾文件是惯例。但每个页面引用的 css 和 js 不一致怎么办？希望在头尾写一些自定义的代码怎么做？这就是 UISVR 主要解决的问题。

UISVR 提供了以下功能:  
单独管理头尾文件  
根据页面配置静态文件  
页面自定义 css 和 js  
可以配置一些固定的变量，如 menu  

#### 静态文件

提供直接访问静态文件的服务, 在htdocs/htdocs存放了demo.jpg, 则可以直接通过`http://localhost:7777/demo.jpg`访问.

#### 模板

采用velocity模板引擎, [官网](http://velocity.apache.org/)

语法概要:  
 #标识脚本语句  
 $用来标识一个变量  
 {}用来明确标识变量  
 !用啦强制把不存在的变量显示为空白  
 
#### uisvr配置

参考[文档](https://site.alipay.net/alipay-site/uisvr/index.html)


### 环境准备

#### 环境概况

![_E5_B1_8F_E5_B9_95_E5_BF_AB_E7_85_A7_2016-04-11_14.11.32](http://024028.oss-cn-hangzhou-zmf.aliyuncs.com/uploads/antp/fullstack18/25e67e2099928808a7a2dadb3e134e6e/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7_2016-04-11_14.11.32.png)

#### antd环境准备完成

![_E5_B1_8F_E5_B9_95_E5_BF_AB_E7_85_A7_2016-04-11_13.58.02](http://024028.oss-cn-hangzhou-zmf.aliyuncs.com/uploads/antp/fullstack18/2b75380556c9073a85c7e6104534f0bd/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7_2016-04-11_13.58.02.png)
![_E5_B1_8F_E5_B9_95_E5_BF_AB_E7_85_A7_2016-04-11_02.23.10](http://024028.oss-cn-hangzhou-zmf.aliyuncs.com/uploads/antp/fullstack18/7eb3ddff0371a3a5a91fa213be41b84f/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7_2016-04-11_02.23.10.png)

sofa环境准备完成


![_E5_B1_8F_E5_B9_95_E5_BF_AB_E7_85_A7_2016-04-11_10.06.31](http://024028.oss-cn-hangzhou-zmf.aliyuncs.com/uploads/antp/fullstack18/ceddab5ed5dbc49d7d671ccf43839bd2/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7_2016-04-11_10.06.31.png)
![_E5_B1_8F_E5_B9_95_E5_BF_AB_E7_85_A7_2016-04-11_20.26.29](http://024028.oss-cn-hangzhou-zmf.aliyuncs.com/uploads/antp/fullstack18/32aa4f2c3eb12c7b4f927d36e18d9835/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7_2016-04-11_20.26.29.png)
![_E5_B1_8F_E5_B9_95_E5_BF_AB_E7_85_A7_2016-04-11_13.51.14](http://024028.oss-cn-hangzhou-zmf.aliyuncs.com/uploads/antp/fullstack18/25907ece8d53dcd9bdef58dae4a67700/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7_2016-04-11_13.51.14.png)

## sofa-antd

#### 在应用根目录下创建static目录, 该目录存放静态资源源码

#### 安装 antd-init

```
tnpm install antd-init -g

```

#### 在static目录下执行 antd-init

```
cd static
antd-init

```

#### 启动antd server

```
cd static
tnpm run dev
```

#### 修改`sofa-test-config.properties`, 加入`assets_url`

```
assets_url=http://127.0.0.1:8001 
```

#### 在ui-brokers.xml中加入`content-uri`

注意sofa3中为`assets.url`, sofa4为`assets_url`

```
<content-uri name="assetsServer" expose="true">
  <serverURI>${assets_url}</serverURI>
</content-uri>
```

#### 如果使用uisvr

在config/js.vm config/css.vm中配置对应的js, 在uisvr/home/config.xml中配置js与vm的对应关系

#### 如果不使用uisvr

直接写个macro, 在layout中加载js, css即可


#### 最后在vm中挖个坑

```

<div id="react-content"></div>

```

#### 如果安装了sofa sdk, 在项目根目录下执行 s run --hotcode --compile


#### 打开 localhost:7777/sample

## nodejs npm常用命令

npm是一个node包管理和分发工具，已经成为了非官方的发布node模块（包）的标准。有了npm，可以很快的找到特定服务要使用的包，进行下载、安装以及管理已经安装的包。

1、npm install moduleNames：安装Node模块
安装完毕后会产生一个node_modules目录，其目录下就是安装的各个node模块。

node的安装分为全局模式和本地模式。
一般情况下会以本地模式运行，包会被安装到和你的应用程序代码的本地node_modules目录下。
在全局模式下，Node包会被安装到Node的安装目录下的node_modules下。

全局安装命令为$npm install -g moduleName。
获知使用$npm set global=true来设定安装模式，$npm get global可以查看当前使用的安装模式。

示例：
npm install express 
默认会安装express的最新版本，也可以通过在后面加版本号的方式安装指定版本，如npm install express@3.0.6

npm install <name> -g 
将包安装到全局环境中

但是代码中，直接通过require()的方式是没有办法调用全局安装的包的。全局的安装是供命令行使用的，就好像全局安装了vmarket后，就可以在命令行中直接运行vm命令

npm install <name> --save 
安装的同时，将信息写入package.json中项目路径中如果有package.json文件时，直接使用npm install方法就可以根据dependencies配置安装所有的依赖包，这样代码提交到github时，就不用提交node_modules这个文件夹了。

2、npm view moduleNames：查看node模块的package.json文件夹
注意事项：如果想要查看package.json文件夹下某个标签的内容，可以使用$npm view moduleName labelName

3、npm list：查看当前目录下已安装的node包
注意事项：Node模块搜索是从代码执行的当前目录开始的，搜索结果取决于当前使用的目录中的node_modules下的内容。$ npm list parseable=true可以目录的形式来展现当前安装的所有node包

4、npm help：查看帮助命令

5、npm view moudleName dependencies：查看包的依赖关系

6、npm view moduleName repository.url：查看包的源文件地址

7、npm view moduleName engines：查看包所依赖的Node的版本

8、npm help folders：查看npm使用的所有文件夹

9、npm rebuild moduleName：用于更改包内容后进行重建

10、npm outdated：检查包是否已经过时，此命令会列出所有已经过时的包，可以及时进行包的更新

11、npm update moduleName：更新node模块

12、npm uninstall moudleName：卸载node模块

13、一个npm包是包含了package.json的文件夹，package.json描述了这个文件夹的结构。访问npm的json文件夹的方法如下：
$ npm help json 
此命令会以默认的方式打开一个网页，如果更改了默认打开程序则可能不会以网页的形式打开。

14、发布一个npm包的时候，需要检验某个包名是否已存在
$ npm search packageName

15、npm init：会引导你创建一个package.json文件，包括名称、版本、作者这些信息等

16、npm root：查看当前包的安装路径
npm root -g：查看全局的包的安装路径

17、npm -v：查看npm安装的版本

更多命令请参看[npm官方文档](https://www.npmjs.org/doc/)




# Mac 环境配置

## Node.js

Node.js 是一个 javascript 的**执行环境**。

使用淘宝镜像安装 Node.js [http://npm.taobao.org/mirrors/node](http://npm.taobao.org/mirrors/node)。目前版本 4.2.3。记住，装偶数开头的最新版。

安装完之后执行以下代码查看版本:

```
node -v
```

## npm 和 tnpm

npm 是 Node.js 的包管理工具。因为源在国外不稳定，所以阿里做了个内网镜像源 tnpm。 

```
npm install -g tnpm --registry=http://registry.npm.alibaba-inc.com
```

之后看到任何 npm 的命令，替换成 tnpm 就好了。

## antd

参考 [http://ant.design/docs/getting-started](http://ant.design/docs/getting-started) 。




README
# 汇总

务必按照顺序使用本教程。课程和视频资料是重点，必看！

 - [Mac 环境配置](http://gitlab.alipay-inc.com/ant-design/learn-it-yourself/blob/master/mac_setup.md)
 - [Windows 环境配置](http://gitlab.alipay-inc.com/ant-design/learn-it-yourself/blob/master/windows_setup.md)
 - [前端名词汇总](http://gitlab.alipay-inc.com/ant-design/learn-it-yourself/blob/master/glossary.md)
 - [课程和视频资料](http://antp.alipay.net/training#/detail/566e41965bc411e428421610?_k=2p9jmn)
 - [组件使用的经典例子](http://gitlab.alipay-inc.com/ant-design/samples)
 
## 脚手架
 
- [antd init](http://github.com/ant-design/antd-init)
- [react-antd-roof-boilerplate](http://gitlab.alipay-inc.com/roof/react-antd-roof-boilerplate)
 
## 实际项目
 
- [成都服务宝-大型项目演示](http://gitlab.alipay-inc.com/alipay-cd/explat)

## 其他

- [gitlab 使用](http://gitlab.alipay-inc.com/ant-design/learn-it-yourself/blob/master/gitlab.md)


# npm常用命令


1、`npm install moduleNames`：安装Node模块
安装完毕后会产生一个node_modules目录，其目录下就是安装的各个node模块。

> node的安装分为全局模式和本地模式。
> 一般情况下会以本地模式运行，包会被安装到和你的应用程序代码的本地node_modules目录下。
> 在全局模式下，Node包会被安装到Node的安装目录下的node_modules下。

全局安装命令为`npm install -g moduleName`。
或者使用`npm set global=true`来设定安装模式，`npm get global`可以查看当前使用的安装模式。

示例：
`npm install express`
默认会安装express的最新版本，也可以通过在后面加版本号的方式安装指定版本，如`npm install express@3.0.6`

`npm install <name> -g`
将包安装到全局环境中

> 但是代码中，直接通过require()的方式是没有办法调用全局安装的包的。全局的安装是供命令行使用的，就好像全局安装了vmarket后，就可以在命令行中直接运行vm命令

`npm install <name> --save`
安装的同时，将信息写入package.json中. 项目路径中如果有package.json文件时，直接使用npm install方法就可以根据dependencies配置安装所有的依赖包，这样代码提交到github时，就不用提交node_modules这个文件夹了。

2、`npm view moduleNames`：查看node模块的package.json文件夹
> 注意事项：如果想要查看package.json文件夹下某个标签的内容，可以使用`npm view moduleName labelName`

3、`npm list`：查看当前目录下已安装的node包
注意事项：Node模块搜索是从代码执行的当前目录开始的，搜索结果取决于当前使用的目录中的node_modules下的内容。`npm list parseable=true`可以目录的形式来展现当前安装的所有node包

4、`npm help`：查看帮助命令

5、`npm view moudleName dependencies`：查看包的依赖关系

6、`npm view moduleName repository.url`：查看包的源文件地址

7、`npm view moduleName engines`：查看包所依赖的Node的版本
??
8、`npm help folders`：查看npm使用的所有文件夹
??
9、`npm rebuild moduleName`：用于更改包内容后进行重建

10、`npm outdated`：检查包是否已经过时，此命令会列出所有已经过时的包，可以及时进行包的更新

11、`npm update moduleName`：更新node模块

12、`npm uninstall moudleName`：卸载node模块

13、一个npm包是包含了package.json的文件夹，package.json描述了这个文件夹的结构。访问npm的json文件夹的方法如下：
`npm help json`
此命令会以默认的方式打开一个网页，如果更改了默认打开程序则可能不会以网页的形式打开。

14、发布一个npm包的时候，需要检验某个包名是否已存在
`npm search packageName`

15、`npm init`：会引导你创建一个package.json文件，包括名称、版本、作者这些信息等

16、`npm root`：查看当前包的安装路径
`npm root -g`：查看全局的包的安装路径

17、`npm -v`：查看npm安装的版本

更多命令请参看npm官方文档：https://www.npmjs.org/doc/





# Gitlab 相关

## Git

Git 是一种分布式的版本控制工具。[5分钟的简明教程](http://rogerdudler.github.io/git-guide/index.zh.html)。

## gitlab.alipay-inc.com

[gitlab.alipay-inc.com](gitlab.alipay-inc.com) 是支付宝内部自己搭建的基于 git 的版本控制服务。开始一个正式的项目只需要两步：

 - 创建一个[成员组(Group)](http://gitlab.alipay-inc.com/dashboard/groups)。把需要往项目里提交代码或者需要查看代码的同学都加到这个组里。
 - 创建一个[项目](http://gitlab.alipay-inc.com/projects/new)。在 Namespace 中选择刚才创建的组。除保密项目外，在 [Visibility Level] 一项中最好选 Internal。
 
 接下来就按照 git 的基本教程使用就好。



