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
