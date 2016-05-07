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

