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
