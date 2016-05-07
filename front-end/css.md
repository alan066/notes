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

学习CSS布局  
[http://zh.learnlayout.com](http://zh.learnlayout.com)
