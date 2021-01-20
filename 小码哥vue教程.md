## Vue内容概述

### 认识Vuejs

- 为什么学习Vuejs
- 简单认识一下Vuejs

### Vuejs安装方式

- CDN引入
- 下载和引入
- NPM安装管理

### Vuejs初体验

- Hello Vuejs
- Vue列表展示
- 案例：计数器

### Vuejs的MVVM

- Vue中的MVVM
- 我相信每个人学习Vue的目的是各部相同的
  -  可能你的公司正要将原有的项目使用Vue进行重构。
  - 也可能是你的公司新项目决定使用Vue的技术栈
  - 当然，如果你现在正在换工作，你会发现招聘前端的需求中，10个有8个都对Vue有或多或少的要求。
  - 当然，作为学习者我们知道Vuejs目前非常火，可以说是前端必备的一个技能

## 简单认识一下Vuejs

- Vue（读音 /vju:/ ,类似于view），不要读错了。
- Vue是一个渐进式的框架，什么是渐进式的呢？就是有多个页面中有jQuery框架，慢慢引入Vue框架来替换jQuery。
  - 渐进式意味着你可以将Vue作为你应用的一部分嵌入其中，带来更丰富的交互体验。
  - 或者如果你希望将更多的业务逻辑使用Vue实现，那么Vue的核心库以及其生态系统。
  - 比如Core+Vue-router+Vuex，也可以满足你各种各样的需求。

- Vue有很多特点和Web开发中常见的高级功能
  -   解耦视图和数据
  - 可复用的组件
  - 前端路由技术
  - 状态管理
  - 虚拟DOM
- 这些特点，慢慢去体会，多敲多练多思考就能理解。

- 学习Vuejs的前提？
  - ​	从零学习Vue开发，并不需要你具备其他类似于Angular、React，甚至是JQuery的经验。
  - 但是你需要具备一定的HTML、CSS、JavaScript基础。

## Vue.js安装

- 使用一个框架，我们第一步要做什么呢？安装下载他

- 安装Vue的方式有很多

- 方式一：直接CDN引入

  - ​	你可以选择引入开发环境版本还是生成环境版本

  ```html
  <!--开发环境版本，包含了有帮助的命令行警告-->
  <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
  <!--生产环境版本，优化了尺寸和速度-->
  <script src="https://cdn.jsdelivr.net/npm/vue"></script>
  ```

- 方式二：下载和引入

```html
开发环境 <a href="https://vuejs.org/js/vue.js">开发环境</a>
生产环境 <a href="https://vuejs.org/js/vue.min.js">生产环境</a>
```

- 方式三：NPM安装
  - 后续通过webpack和CLI的使用，我们使用该方式。

- 方式四：vscode安装和HBuilder x内置环境

## Hello Vuejs

- 我们来做我们的第一个Vue程序，体验一下Vue的响应式

- 代码做了什么事情？

- 我们来阅读javaScript代码，会发现创建了一个Vue对象。

- 创建Vue对象的时候，传入了一些options：{}

  - {}中包含了el属性：该属性决定了这个Vue对象挂载到哪一个元素上，很明显，我们这里是挂载到了id为app的元素上
  - {}中包含了data属性：该属性中通常会存储一些数据
    - 这些数据可以是我们直接定义出来的，比如像上面这样。
    - 也可能是来自网络，从服务器加载的。

- 浏览器执行代码的流程：

  - 执行到10~13行代码显然出对应的HTML
  - 执行第16行代码创建Vue实例，并且对原HTML进行解析和修改。

  ```html
  <!DOCTYPE html>
  <html>
  	<head>
  		<meta charset="utf-8">
  		<title></title>
  	</head>
  	<body>
  		<div id="app">
  			<h1>{{message}}</h1>
  			<h2>{{name}}</h2>
  		</div>
  	<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
  	<script type="text/javascript">
  		//let(变量) const(常量)
  		//编程范式：声明式编程
  		const app=new Vue({
  			el:'#app',//用于挂载要管理的元素
  			data:{//定义数据
  				message:'你好呀',
  				name:'小明'
  			}
  		})
  		//原生js的做法（编程范式：命令式编程）
  		//1.创建div元素，设置id属性
  		//2.定义一个变量叫message
  		//3.将message变量放前面的div元素中显示
  		//4.修改message的数据：今天不是很好！
  		//5.将修改后的数据再次替换到div元素
  	</script>
  	</body>
  </html>
  ```

- 并且，目前我们的代码是可以做到响应式的。

- 注意写代码的时候，注意逗号，少了就乱码。

## Vue列表显示

- 现在，我们来展示一个更加复杂的数据：数据列表。
  - 比如我们现在从服务器请求过来一个列表
  - 希望展示到HTML中。

- HTML代码中，使用v-for指令
- 循环使用 v-for 指令。v-for 指令需要以 **site in sites** 形式的特殊语法， sites 是源数据数组并且 site 是数组元素迭代的别名。

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
	</head>
	<body>
		<div id="app">
			<ul>
				<li v-for="item in movies">{{item}}</li>
			</ul>
		</div>
		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
		<script type="text/javascript">
			const app=new Vue({
				el:'#app',
				data:{
					movies:['星际穿越','大话西游','少年派','盗梦空间']
				}
			})
		</script>
	</body>
</html>
```

- 使用v-for，我们再不需要在JavaScript代码中完成DOM的拼接相关操作了

- 而且，他是响应式的。
  - 也就是说，当我们数组中的数据发生改变时，界面会自动改变。
  - 依然让我们打开开发者模式的console，来试一下。用app.movies.push()

## 案例：计数器

- 现在，我们来实现一个小的计时器

  - 点击 + 计时器+1
  - 点击- 计时器 - 1

  ```html
  <!DOCTYPE html>
  <html>
  	<head>
  		<meta charset="utf-8">
  		<title></title>
  	</head>
  	<body>
  		<div id="app">
  			<h2>当前计数：{{counter}}</h2>
  			<!-- <button v-on:click="counter++">+</button>
  			<button v-on:click="counter--">-</button> -->
  			<button v-on:click="add">+</button>
  			<button v-on:click="sub">-</button>
  		</div>
  		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
  		<script type="text/javascript">
  			const app=new Vue({
  				el:'#app',
  				data:{
  					counter: 0
  				},
  				methods:{
  					add: function (){
  						console.log('add被执行');
  						this.counter++
  					},
  					sub:function(){
  						console.log('sub被执行');
  						this.counter--
  					}
  				}
  			})
  		</script>
  	</body>
  </html>
  ```

- 这里，我们又要失业新的指令和属性

  - 新的属性：methods，该属性用于在Vue对象中定义方法。
  - 新的指令：@click，该指令用于监听某个元素的点击事件，并且需要指定当发生点击时，执行的方法（方法通常是methods中定义的方法）

- 你可能会有疑惑？

  - 这些@click是什么东西？

    语法糖，@是v-on的缩写

  - Vue对象中又是定义el/data/methods,到底都有哪些对象可以定义，以及他们的作用是什么？

  el 是数据源的绑定 el:'#app'就是id的绑定元素，编译执行时会编译相应的代码

  data是定义数据，类似于定义变量名然后在html标签中输出，name: '你好' ，然后在el定义的div里面输出你好，但是必须是{{name}}才能输出。

  methods是定义方法，然后在html标签里面写指令，然后调用它，调用data里面变量，有时候需要this指向。

## Vue中的MVVM

- 什么是MVVM呢？

  - ​	MVVM分为三个部分：分别是M（Model，模型层 ），V（View，视图层），VM（ViewModel，V与M连接的桥梁，也可以看作为控制器）
     1、 M：模型层，主要负责业务数据相关；
     2、 V：视图层，顾名思义，负责视图相关，细分下来就是html+css层；
     3、 VM：V与M沟通的桥梁，负责监听M或者V的修改，是实现MVVM双向绑定的要点；

  - MVVM支持双向绑定，意思就是当M层数据进行修改时，VM层会监测到变化，并且通知V层进行相应的修改，反之修改V层则会通知M层数据进行修改，以此也实现了视图与模型层的相互解耦；

  - 关系图

    ![](C:\Users\86157\Desktop\百家号图片搜集\MVVM关系图.webp)

### 关于Object.defineProperty

- 介绍

  `Object.defineProperty`可以再一个对象中**定义**或者**修改**一个属性，然后返回这个对象，并且可对该属性的**可写行**，**可便利性**，**存取描述符(get、set)**等进行设定；

- 参数

  `Object.defineProperty(obj, prop, descriptor)`;

  - obj: 需要进行定义或修改属性的对象；
  - prop： 需要进行定义或者修改的属性；
  - descriptor： 该属性的描述符（包含存取描述符和数据描述符），该参数以一个对象的形式传入，该参数有六个选项：
  - value: 设定该属性的值；
  - writable: 布尔，该属性是否可写入（是否可改变其value）；
  - enumerable: 布尔，该属性是否可被遍历得到（for...in， Object.keys等）；
  - configurable: 布尔，设定该属性是否可被删除，且除writable外的其他描述符是否可被修改；
  - get: 函数，该属性的值被获取时执行的回调函数（例如console.log(prop)），默认为undefined；
  - set: 函数，该属性的值被设置时执行的回调函数，默认为undefined；

- 简单例子

  ```js
  // 没有get和set
          let obj = {
  
          }
          Object.defineProperty(obj, 'a', {
              value: 123, // 该属性值为123
              enumerable: false, // 不可被遍历得到
              writable: false, // 不可被重新写入
              configurable: false // 不可被删除，且enumerable和value不能通过Object.defineProperty重新定义
          })
          // 使用get和set
          let obj = {
              // 设定默认值
              _data: {
                  a: 123
              }
          }
          Object.defineProperty(obj, 'a', {
              get() {
                  // 当获取a时执行
                  console.log('a被获取了')
                  return obj._data.a
              },
              set(value) {
                  // 当修改a时执行
                  obj._data.a = value
                  console.log('a的值被修改了')
              }
          })
  ```

- 数据描述符和存取描述符

在`descriptor`的六个选项中，有数据描述符和属性描述符，**他们是不可共存的**，否则会报错（因为功能上有所重复和冲突）。

- 数据描述符：value，writable；
- 存取描述符：get，set；
- 两者皆可共存：configurable，enumerable；

报错例子

```js
  let obj = {

        }
        Object.defineProperty(obj, 'a', {
            value: 123,
            get() {
                // 当获取a时执行
                console.log('a被获取了')
                return obj._data.a
            },
            set(value) {
                // 当修改a时执行
                obj._data.a = value
                console.log('a的值被修改了')
            }
        })
```

- 兼容性
  至少IE8以上

### 使用Object.defineProperty实现MVVM的表单数据双向绑定

- 有这么一个表单和一个`person`对象

```html
<form class="form">
    <p>name<input type="text" name="name"></p>
    <p>age<input type="text" name="age"></p>
</form>
<script>
let person={
    
}
</script>
```

- 需要实现的功能（该表单与person对象的双向绑定）
  - 1.用户在表单中输入的数据实时绑定在person对象的同名属性中；
  - 2.在person对象中进行属性的修改会实时反映在表单中；
- 获取form的DOM节点，并且设置默认值，该默认值在Vue中就是data对象中的数据；

```html
<form class="form">
    <p>name<input type="text" name="name"></p>
    <p>age<input type="text" name="age"></p>
</form>
<script>
let form=document.querySelector('.form')
let person={
    _data:{
        name:'',
        age:''
    }
}
</script>
```

- 实现用户输入数据与person对象内同名属性的同步修改

一、用`Object.defineProperty`为person对象设定name和age两个属性，并且他们的get获取的是_data里的数据

```html
<form class="form">
    <p>name<input type="text" name="name"></p>
    <p>age<input type="text" name="age"></p>
</form>
<script>
let form=document.querySelector('.form')
let person={
    _data:{
        name:'',
        age:''
    }
}
  Object.defineProperty(person,'name',{
    get(){
        console.log('name被获取了')
        return person._data.name
    },
    set(value){
        console.log('name被修改了')
        person._data.name=value   
    }  
})
    Object.defineProperty(person,'age',{
    get(){
        console.log('age被获取了')
        return person._data.name
    },
    set(value){
        console.log('age被修改了')
        person._data.name=value
        
    }
    
})
</script>
```

二、监听form表单中的input事件，并且将获取的目标DOM节点的value值赋值给person对象中的响应属性即可完成用户输入与对象值间的绑定

```html
<!--V层-->
<form class="form">
    <p>name<input type="text" name="name"></p>
    <p>age<input type="text" name="age"></p>
</form>
<script>
    //M层
let person={
    _data:{
        name:'',
        age:''
    }
}
//VM层
let form=document.querySelector('.form')
  Object.defineProperty(person,'name',{
    get(){
        console.log('name被获取了')
        return person._data.name
    },
    set(value){
        console.log('name被修改了')
        person._data.name=value   
    }  
})
    Object.defineProperty(person,'age',{
    get(){
        console.log('age被获取了')
        return person._data.name
    },
    set(value){
        console.log('age被修改了')
        person._data.name=value
        
    }
    
})
    form.addEventListener('input',(e)=>{
        let value=e.target.value
        let name=e.target.getAtrribute('name')
        person[name]=value
    })
</script>
```

### 缺点

本身form节点中只有name和age两个输入框对应person中的属性，如果这时候我在form节点中新添加一个输入框进去，这个新添加的input输入的值是没有双向绑定效果的；
 PS：在Vue中，`created`函数后新添加的属性不会进行监听，因为这时候的数据已经初始化完毕，当然Vue本身也提供了一个`Vue.set(object, key, value)`api使其可以在`created`后对data对象进行属性的添加；

处。

- <a href="https://zh.wikipedia.org/wiki/MVMM">MVVM</a>

### 我们直接来看Vue的MVVM

![](C:\Users\86157\Desktop\百家号图片搜集\MVVM.png)

- View层：
  - 视图层
  - 通常介绍DOM层
  - 作用是给用户展示各种信息
- Model层：
  - 数据层
  - 数据可能是我们固定的死数据，更多的是来自我们服务器，从网络上请求下来的数据。
  - 在我们计数器的案例中，就是后面抽出来的obj，当然，里面的数据可能没有这么简单。
- VueModel层
  - 视图模型层
  - 视图模型层是View和Model沟通的桥梁
  - 一方面他实现了Data Binding，也就是数据绑定，将Model的改变实时的反应到View中
  - 另一方面他实现了DOM Listener，也就是DOM监听，当DOM发生一些事件（点击、滚动、touch等）时，可以监听到，并在需要的情况下改变对应的Data。

### 计数器的MVVM

![](C:\Users\86157\Desktop\百家号图片搜集\MVVM分析图.png)

## 创建Vue实例传入的options

- 你会发现，我们在创建Vue实例的时候，传入一个对象options
- 这个options中可以包含哪些选项呢？
  - 详细解析：<a href="https://vuejs.org/v2/guide/instance.html">options的解析</a>

- 目前掌握这些选项：
  - el：
    - 类型：string|HTMLElement
    - 作用：决定之后Vue实例会管理哪一个DOM
  - data：
    - 类型：Object| Function
    - 作用：Vue实例对应的数据对象
  - methods：
    - 类型：{[key:string] :Fuction}
    - 作用：定义属性Vue的一些方法，可以在其他地方调用，也可以在指令中使用。

开发中什么时候称之为方法，什么时候称之为函数？

- 方法：method

动作

- 函数：function

  function person（）{

  }

  一块可执行程序段方法就是函数

生命周期：事物从诞生到消亡的整个过程

init初始化到destroy销毁

debug：开发阶段

release：发布版本

vue生命周期：

![](C:\Users\86157\Desktop\百家号图片搜集\vue生命周期.png)

![](C:\Users\86157\Desktop\百家号图片搜集\vue生命周期1.webp)

## 模板语法

## 内容概述

- 插值操作
- 绑定属性
- 计算属性
- 事件监听
- 条件判断
- 循环遍历
- 阶段案例
- v-model

### 插值操作

#### Mustache

- 如何将data中的文本数据，插入到html中呢？
  - 我们已经学习过了，可以通过Mustache语法（也是双大括号）
- 我们可以像下面这样来使用，并且数据是响应式的

```html
<div id="#app">
    <h2>Hello {{name}} </h2>
    <h2>{{firstname}}{{lastname}}</h2>
    <h2>{{counter * 2 }}</h2>
</div>
<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
<script>
let app=new Vue({
    el:'#app',
    data:{
        name:'VueJS',
        firstname:'coder',
        lastname:'why',
        counter: 100
    }
})

</script>
```

#### v-once

- 但是，在某些情况下，我们可能不希望界面随意的跟随改变
  - 这个时候，我们就可以使用一个Vue的指令
- v-once：
  - 该指令后面不需要跟任何表达式（比如之前的v-for后面是由跟表达式的）
  - 该指令表示元素和组件（组件后面才会学习）只渲染一次，不会随着数据的改变而改变。
- 代码如下：

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
	</head>
	<body>
		<div id="app">
			<h2>{{message}}</h2>
			<h2 v-once>{{message}}</h2>
		</div>
		<script>
			const app = new Vue({
			 	el:'#app',
		data:{message:'VueJS'},
		})
		</script>
	</body>
</html>

```

#### v-html

- 某些情况下，我们从服务器请求到的数据本身就是一个HTML代码
  - 如果我们直接通过{{}}来输出，会将HTML代码也一起输出。
  - 但是我们可能像希望的是按照HTML格式进行解析，并且显示对应的内容。
- 如果我们希望解析出HTML展示
  - 该指令后面往往会跟上一个string类型
  - 会将string的html解析出来并且进行渲染
- 代码如下：

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
	</head>
	<body>
		<div id="app">
			<h2>{{url}}</h2>
			<h2 v-html="url">{{url}}</h2>
		</div>
		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
		<script>
			const app = new Vue({
				el: '#app',
				data: {
					message: 'VueJS',
					url:'<a href="//www.baidu.com">百度</a>'
				},
			})
		</script>
	</body>
</html>

```

#### v-test

- v-text作用和Mustache比较相似：都是用于将数据显示在界面中

- v-test通常情况下，接受一个string类型

- 代码如下：

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
	</head>
	<body>
		<div id="app">
		<h2 v-text="message"></h2>
		</div>
		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
		<script>
			const app = new Vue({
				el: '#app',
				data: {
					message: 'VueJS',
				},
			})
		</script>
	</body>
</html>
```

#### v-pre

- v-pre用于跳过这个元素和它子元素的编译过程，用于显示原本的Mustache语法。
- 比如下面的代码：
  - 第一个h2元素中的内容会被编译解析出来对应的内容
  - 第二个h2元素中会直接显示{{message}}

- 代码如下：

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
	</head>
	<body>
		<div id="app">
		<h2>{{message}}</h2>
		<h2 v-pre>{{message}}</h2>
		</div>
		<script src="../js/vue.js" type="text/javascript"charset="utf-8"></script>
		<script>
			const app = new Vue({
			 	el:'#app',
		data:{message:'VueJS'},
		})
		</script>
	</body>
</html>

```

#### v-cloak

- 在某些情况下，我们浏览器可能会直接显示出来编译的Mustache标签。
- cloak：斗篷

- 代码如下：

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<style type="text/css">
			[v-cloak]{
				display: none;
			}
		</style>
	</head>
	<body>
		<div id="app" v-cloak>
			{{message}}
		</div>
		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
		<script>
			//在vue解析之前，div中有一个属性v-cloak
			//在vue解析之后，div中没有一个属性v-cloak
			setTimeout(function(){
				const app = new Vue({
					el: '#app',
					data: {
						message: 'VueJS'
					},
				})
			},1000)
		</script>
	</body>
</html>

```

### 绑定属性

#### v-bind介绍

- 前面我们学习的指令主要作用是将插入到我们模板的内容当中。
- 但是，除了内容需要动态来决定外，某些属性我们也希望动态来绑定。
  - 比如动态绑定a元素的href属性
  - 比如动态绑定img元素的src属性
- 这个时候，我们可以使用v-bind指令：
  - 作用：动态绑定属性
  - 缩写：   ：
  - 预期：any（with argument）|Object(without argument)
  - 参数：attrOrProp(optional)
- 下面，我们就具体来学习v-bind的使用。

#### v-bind基础

- v-bind用于绑定一个或多个属性值，或者想另外一个组件传递props值（这个学到组件时再介绍）
- 在开发中，有哪些属性需要动态进行绑定呢？
  - 还有很多的，比如图片的链接src、网站的链接href、动态绑定一些类、样式等等
- 比如通过Vue实例中的data绑定元素的src和href，代码如下：

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
	</head>
	<body>
		<div id="app">
			<!-- 错误的做法：这里不可以使用mustache语法 -->
			<!-- <img src="{{imgURL}}" alt=""> -->
			<!-- 正确做法是用v-bind指令 -->
			<img v-bind:src="imgURL" alt="">
			<a v-bind:href="aHref">百度</a>
            <!--语法糖写法-->
            <img :src="imgURL" alt="">
			<a  :href="aHref">百度</a>
		</div>
		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
		<script>
			const app = new Vue({
				el: '#app',
				data: {
					message: 'VueJS',
					imgURL:'https://ss0.bdstatic.com/94oJfD_bAAcT8t7mm9GUKT-xh_/timg?image&quality=100&size=b4000_4000&sec=1594485258&di=688260cc109b75d48955cbabea4d9cee&src=http://a0.att.hudong.com/64/76/20300001349415131407760417677.jpg',
					aHref:'https://www.baidu.com'
				},
			})
		</script>
	</body>
</html>
```

#### v-bind语法糖

- v-bind有一个对应的语法糖，也就是简写方式
  - 在开发中，我们通常会使用语法糖的形式，因为这样更美观简洁
- 简写方式如下：

```html
<!--语法糖写法-->
<div id="app">
            <img :src="imgURL" alt="">
			<a  :href="aHref">百度</a>
</div>
```

#### v-bind绑定class

- 很多时候，我们希望动态的来切换class，比如：
  - 当数据为某个状态时，字体显示红色。
  - 当数据另一个状态时，字体显示黑色。
- 绑定class有两种方式：
  - 对象语法
  - 数组语法
- 绑定方式：对象语法
  - 对象语法的含义是:class后面跟的是一个对象。
- 对象语法有下面这些用法：

用法一：直接通过{}绑定一个类

```html
<h2 :class="{'active':isActive}">Hello World</h2><!--isActive是boolean-->
```

用法二：也可以通过判断，传入多个值

```html
<h2 :class="{'active': isActive,'line':isLine}">Hello World</h2>
```

用法三： 和普通的类同时存在，并不冲突

注：如果isActive和isLine都为true，那么会有title/acitve/line三个类

```html
<h2 class="title" :class="{'active':isActive,'line':isLine}">Hello World</h2>
```

用法四：如果过于复杂，可以放在一个methods或者computed中

注：classes是一个计算属性

```html
<h2 class="title" :class="classes"> Hello World</h2>
```

#### v-bind绑定style

- 我们可以利用v-bind:style来绑定一些CSS内联样式。
- 在写CSS属性名的时候，比如font-size
  - 我们可以使用驼峰式（camelCase）fontSize
  - 或短横线分隔（kebab-case，记得用单引号括起来）‘font-size’

- 绑定class有两种方式：
  - 对象语法
  - 数组语法

- 绑定方式一：对象语法

```html
<h2 :style="{color:currentColor,fontSize:fontSize+'px'}">{{message}}</h2>
```

- style后面跟着是一个对象类型
  - 对象的key是CSS属性名称
  - 对象的value是具体赋的值，值可以来自于data中的属性
- 绑定方式二：数组语法

```html
<div v-bind:style="[baseStyles,overridingStyles]"></div>
```

- style后面跟的是一个数组类型
  - 多个值以分隔即可

### 计算属性（重要）

#### 什么是计算属性？

- 我们知道，在模板中可以直接通过插值语法显示一些data中的数据。
- 但是在某些情况，我们可能需要对数据进行一些转化后再显示，或者需要将多个数据结合起来进行显示
  - 比如我们有firstName和lastName两个变量，我们需要显示完整的名称。
  - 但是如果多个地方都需要显示完整的名称，我们就需要写多个{{firstName}} {{lastName}}

- 我们可以将上面的代码换成计算属性：
  - OK，我们发现计算属性是写在实例的computed选项中的。

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
	</head>
	<body>
		<div id="app">
		<h2>{{firstName+" "+lastName}}</h2>
		<h2>{{firstName}} {{lastName}}</h2>
		<h2>{{fullName}}</h2>
		</div>
		<script src="js/vue.js" type="text/javascript" charset="utf-8"></script>
		<script>
			const app = new Vue({
				el: '#app',
				data: {
					firstName:'Tom',
					lastName:'Joe'
				},
				computed:{
					fullName:function(){
						return this.firstName+' '+this.lastName 
					}
				},
				methods:{
				getFullName(){
					return this.firstName,this.lastName
				}	
				}
			})
		</script>
	</body>
</html>
```

#### 计算属性的复杂操作

-  计算属性也可以进行一些更加复杂的操作，比如下面的例子：

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
	</head>
	<body>
		<div id="app">
			<h2>书籍总价值:{{totalPrice}}</h2>
		</div>
		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
		<script type="text/javascript">
			let vm=new Vue({
				el:'#app',
				data:{
					books:[
						{name:'JAVA编程思想',price:39,count:3},
						{name:'Unix编程艺术',price:39,count:2},
						{name:'Vue程序设计',price:39,count:1},
					]
				},
				computed:{
					totalPrice(){
						//这里使用一个高阶函数
						return this.books.reduce((total,b)=>{
							return total+b.price*b.count
						},0)
					}
				}
			})
		</script>
	</body>
</html>

```

#### 计算属性的setter和getter

- 每计算属性都包含一个getter和一个setter

  - 在上面的例子中，我们只要使用getter来读取。
  - 在某些情况下，你也可以提供一个setter方法（不常用）。
  - 在需要写setter的时候，代码如下：

  ```html
  <!DOCTYPE html>
  <html>
  	<head>
  		<meta charset="utf-8">
  		<title></title>
  	</head>
  	<body>
  		<div id="app">
  			<h2>{{fullName}}</h2>
  		</div>
  		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
  		<script>
  			const app = new Vue({
  				el: '#app',
  				data: {
  				firstName:'Kobe',
  				lastName:'Btyant'
  				},
  				computed:{
  					// fullName:function(){
  					// 	return this.firstName+''+this.lastName
  					// }
  					//计算属性一般是没有set方法，只读属性
  					fullName:{
  						set: function(newValue){
  							// console.log('-----',newValue);
  							const names=newValue.split(' ');
  							this.firstName = names[0];
  							this.lastName = names[1];
  						},
  						get: function(){
  							return this.firstName+' '+this.lastName
  						}
  					},
  				}
  			})
  		</script>
  	</body>
  </html>
  ```

#### 计算属性的缓存

- 我们可能会考虑这样的一个问题：

  - methods和computed看起来都可以实现我们的功能
  - 那么为什么还要多一个计算属性这个东西呢？
  - 原因：计算属性会进行缓存，如果多次使用时，计算属性只会调用一次。

- 我们来看下面的代码：

  ```html
  <!DOCTYPE html>
  <html>
	<head>
  		<meta charset="utf-8">
  		<title></title>
  	</head>
  	<body>
  		<div id="app">
  			<div>{{fullName}}</div>
  			<div>{{getfullName()}}</div>
  		</div>
  		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
  		<script>
  			let vm = new Vue({
  				el: '#app',
  				data: {
  					firstName: 'kobe',
  					lastName: 'bryant'
  				},
  				computed: {
  					fullName() {
  						console.log('执行了fullName的计算属性');
  						return this.firstName + ' ' + this.lastName
  					}
  					},
  					methods:{
  						getfullName() {
  							console.log('执行了getfullName的计算属性');
  							return this.firstName + ' ' + this.lastName
  						}
  				}
  			})
  		</script>
  	</body>
  </html>
  ```
  

### 事件监听

- 在前端开发中，我们需要经常和用于交互。
  - 这个时候，我们就必须监听用户发生的时间，比如点击、拖拽、键盘事件等等
  - 在Vue中如何监听事件呢？使用v-on指令
- v-on介绍
  - 作用:绑定事件监听器
  - 缩写：@
  - 预期：Function}|Inline Statement|Object
  - 参数：event
- 下面，我们就具体来学习v-on的使用

#### v-on基础

- 这里，我们用一个监听按钮的点击事件，来简单看看v-on的使用
  - 下面的代码中，我们使用了v-on:click= " counter++"
  - 另外，我们可以将事件指向一个在methods中定义的函数

```html
<div id="app">
    <h2>点击次数:{{counter}}</h2>
    <button v-on:click="counter++">按钮点击1</button>
    <button v-on:click="btnClick">按钮点击2</button>
</div>
<script>
let app=new Vue({
    el:'app',
    data:{
        counter:0
    }
    methods:{
    btnClick(){
    this.counter++
}
}
})
</script>

```

- 注意：v-on也有对应的语法糖

  - v-on:click可以写成@click

  ```html
  <div id="app">
      <h2>点击次数:{{counter}}</h2>
      <button @click="counter++">按钮点击1</button>
      <button @click="btnClick">按钮点击2</button>
  </div>
  ```

#### v-on参数

- 当通过methods中定义方法，以供@click调用时，需要注意参数问题：
- 情况一：如果该方法不需要额外参数，那么方法后的()可以不添加。
  - 但是注意：如果方法本身中有一个参数，那么会默认将原生事件event参数传递进去
- 情况二：如果需要同时传入某个参数，同时需要event时，可以通过$event传入事件。

```html
<div id="app">
    <h2>点击次数:{{counter}}</h2>
    <button @click="handleAdd">+1</button>
    <button @click="handleAddTen(10,$event)">+10</button>
</div>
<script>
let app=new Vue({
    el:'app',
    data:{
        counter:0
    }
    methods:{
   handleAdd(event){
    console.log(event);
    this.counter++
},
    handleAddTen(count,event){
        console.log(event);
        this.counter += 10;
    }
}
})
</script>
```

#### v-on修饰符

- 在某些情况下，我们拿到event的目的可能是进行一些事情处理。

- Vue提供了修饰符来帮助我们方便的处理一些事件：

  - .stop-调用event.stopPropagation()
  - .prevent- 调用event.preventDefault()
  - .{keyCode | keyAlias}-只当事件是从特定键触发时才触发回调
  - .native -监听组件根元素的原生事件
  - .once-只触发一次回调

  ```html
  <!DOCTYPE html>
  <html lang="zh">
  <head>
  	<meta charset="UTF-8">
  	<meta name="viewport" content="width=device-width, initial-scale=1.0">
  	<meta http-equiv="X-UA-Compatible" content="ie=edge">
  	<title></title>
  </head>
  <body>
  	<script src="./vue.js" type="text/javascript" charset="utf-8"></script>
  	<!-- 停止冒泡 -->
  	<button @click.stop="doThis"></button>
  	<!-- 阻止默认行为 -->
  	<button @click.prevent="doThis"></button>
  	<!-- 阻止默认行为，没有表达式 -->
  	<form @submit.prevent>	</form>
  	<!-- 串联修饰符 -->
  	<button @click.stop.prevent="doThis"></button>
  	<!-- 键修饰符，键别名 -->
  	<input @keyup.enter="onEnter">
  	<input @keyup.13="onEnter">
  	<!-- 点击回调只会触发一次 -->
  	<button @click.once="doThis"></button>
  </body>
  </html>
  ```

### 条件判断

#### v-if、v-else-if、v-else

- v-if、v-else-if、v-else
  - 这三个指令与JavaScript的条件语句if、else、else if类似。
  - Vue的条件指令可以根据表达式的值在DOM中渲染或销毁元素或组件
- 简单的案例演示：

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
	</head>
	<body>
		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
		<div id="app">
			<h2 v-if="score>=90">优秀</h2>
			<h2 v-else-if="score>=80">良好</h2>
			<h2 v-else-if="score>=60">及格</h2>
			<h2 v-else>不及格</h2>
			<h1>{{result}}</h1>
		</div>
		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
		<script>
            //简单判断用v-if和v-else-if，v-else 复杂判断用计算属性
			const app = new Vue({
				el: '#app',
				data: {
						score: 99
				}, 
				computed:{
					result(){
						let showMessage='';
						if(this.score>=90){
							showMessage="优秀"
						}
						else if(this.score>=80){
							showMessage="良好"
						}
						else if(this.score>=60){
							showMessage="及格"
						}else{
							showMessage="不及格"
						}
						return showMessage
					}
				}
			})
		</script>
	</body>
</html>
```

- v-if的原理：
  - v-if后面的条件为false时，对应的元素以及其子元素不会渲染。
  - 也就是根本没有不会有对应的标签出现在DOM中。

#### 条件渲染案例

- 我们来做一个简单的小案例：

  - 用户再登录时，可以切换使用用户账号登录还是邮箱地址登录。
  - 类似如下情景：

  ```html
  <div id="app">
      <span v-if="type==='username'">
          <label>用户账号:</label>
          <input placeholder="用户账号">
      </span>
      <span v-else>
       	<label>邮箱地址:</label>
          <input placeholder="邮箱地址">
      </span>
      <button @click="handleToggle">切换类型</button>
  </div>
  <script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
  <script>
  let app=new Vue({
      el:'#app';
      data:{
      type:'username'
  },
      methods:{
                  handleToggle(){
      this.type=this.type==='email'? 'username':'emailx'
  }
                  }
  })
  </script>
  ```

#### 案例小问题

- 小问题：
  - 如果我们在有输入内容的情况下，切换了类型，我们会发现文字依然显示之前的输入的内容。
  - 但是按道理讲，我们应该切换到另外一个input元素中了。
  - 在另一个input元素中，我们并没有输入内容。
  - 为什么会出现这个问题呢？
- 问题解答：
  - 这里因为Vue'在进行DOM渲染时，出于性能考虑，会尽可能的复用已经存在的元素，而不是重新创建新的元素。
  - 在上面的案例中，Vue内部会发现原来的input元素不再使用，直接作为else中的input来使用了。
- 解释方案：
  - 如果我们不希望Vue出现类似重复利用的问题，可以给对应的input添加key
  - 并且我们需要保证key的不同

#### v-show

- v-show的用法和v-if非常相似，也用于决定一个元素是否渲染
- v-if和v-show对比
- v-if和v-show都可以决定一个元素是否渲染，那么开发中我们如何选择呢？
  - v-if当条件为false时，压根不会有对应的元素在DOM中。
  - v-show当条件为false时，仅仅是将元素的display属性设置为none而已。
- 开发中如何选择呢？
  - 当需要在显示与隐藏之间切换很频繁时，使用v-show
  - 当只有一次切换时，通过使用v-if

```html
<div id="app">
    <button @click="toggle">切换显示</button>
    <h2 v-show="isShow">我要不要显示呢？</h2>
</div>
<script src="../js/vue.js"></script>
<script>
let app = new Vue({
    el:'#app',
    data:{
        isShow:true
    },
    methods:{
        toggle(){
            this.isShow = ! this.isShow
        }
    }
})
</script>
```

### 循环遍历

#### v-for遍历数组

- 当我们有一个数据需要进行渲染时，我们就可以使用v-for来完成。
  - v-for的语法类似于JavaScript中的for循环。
  - 格式如下：item in item 的形式。
- 我们来看一个简单的案例：
- 如果在遍历的过程中不需要使用索引值
  - v-for="moive in movies"
  - 依次从movies中取出movie，并且在元素的内容中，我们可以使用Mustache语法，来使用movie
- 如果在遍历的过程中，我们需要拿到元素在数组中的索引值呢？
  - 语法格式： v-for=(item,index) in items
  - 其中的index就代表了取出的item在原数组的索引值。

```html
<div id="app">
    <ul>
    <li v-for="item in movies">{{item}}</li>
    <li>-----------我是分割线------------</li>
    <li>{{index+1}}.{{item}}</li>
    </ul>
</div>
<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
		<script>
			const app = new Vue({
				el: '#app',
				data: {
					movies:{
                        '你好','O(∩_∩)O哈哈~','嘻嘻','哟哟'
                    }
				},
			})
		</script>
```

#### v-for遍历对象

- v-for可以遍历对象：
  - 比如某个对象中存储着你的个人信息，我们希望以列表的形式显示出来。

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
	</head>
	<body>
		<div id="app">
			<!-- 1.在遍历对象的过程中，如果只是获取一个值，那么获取到是value -->
		<ul>
			<li v-for="item in info">{{item}}</li>
		</ul>
		
		<!-- 2.获取key和value 格式：(value,key) -->
		<ul>
			<li v-for="(value,key) in info">{{value}}-{{key}}</li>
		</ul>
		
		<!-- 3.获取key,value和index 格式：(value,key,index) -->
		<ul>
			<li v-for="(value,key,index) in info">{{value}}-{{key}}-{{index}}</li>
		</ul>
		</div>
		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
		<script>
			const app = new Vue({
				el: '#app',
				data: {
				info:{
					name:'tom',
					age:19,
					height:1.99
				}
				},
			})
		</script>
	</body>
</html>
```

#### 组件的key属性

- 官方推荐我们在使用v-for时，给对应的元素或组件添加上一个:key属性。
- 为什么需要这个key属性呢（了解）？
  - 这个其实和Vue的虚拟DOM的Diff算法有关系。
  - 这里我们借用React's diff algorithm中的一张图来简单说明一下：
- 当某一层有很多相同的节点时，也就是列表节点时，我们希望插入一个新的节点
  - 我们希望可以在B和C之间加一个F，Diff算法默认执行起来是这样的。
  - 即使把C更新成F，D更新成C，E更新成D，最后再插入E，是不是很没有效率
- 所以我们需要使用key来给每个节点做一点唯一标识		
  - Diff算法就可以正确的识别此节点
  - 找到正确的位置区插入新的节点
- key的作用主要是为了高效的更新虚拟DOM。

#### 检测数组更新

- 因为Vue是响应式的，所以当数据发生变化时，Vue会自动检测数据变化，视图会发生对应的更新。
- Vue中包含了一组观察数组编译的方法，使用他们改变数组也会触发视图的更新。
  - push()
  - pop()
  - shift()
  - unshift()
  - splice()
  - sort()
  - reverse()

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
	</head>
	<body>
		<div id="app">
			<ul>
				<li v-for="item in letters">{{item}}</li>
			</ul>
			<button  @click="btnClick">按钮</button>
		</div>
		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
		<script>
			const app = new Vue({
				el: '#app',
				data: {
				letters:['a','b','c','d']
				},
				methods:{
					btnClick(){
						// 1.push()方法
						// this.letters.push('aaaa')
							// 2.pop()方法 :删除数组中的最后一个元素
							// this.letters.pop()
							// 3.shift()：删除数组中的第一个元素
							// this.letters.shift()
							// 4.unshift():在数组最前面添加元素
							// this.letters.unshift('aaa')
							// 5.splice作用:删除元素/插入元素/替换元素,
									// 删除元素:第二个参数传入你要删除几个元素（如果没有传，就是删除后面所有的元素）
									//替换元素: 第二个参数，表示我们要替换几个元素，后面是用于替换前面的元素
									//插入元素：第二参数，传入0，并且后面跟上要插入的元素
							// splice(start)
							// const start=2
							// this.letters.splice(1,3,'m','n','w')
							// this.letters.splice(1,0,'f','g','h')
							// 6.sort()
							// this.letters.sort()
							// 7.reverse():调换前后位置
							// this.letters.reverse()
						// 2.通过索引值修改数组中的元素
						// this.letters[0] = 'bbbbbb';
						// this.letters.splice(0,1,'aaaaaaaa')
						// set(要修改的对象,索引值,修改后的值)
						Vue.set(this.letters,0,'aaaaaaa')
						
						
					}
				}
			})
			// function sum(num1,num2){
			// 	return num1+num2
			// }
			// function sum(num1,num2,num3){
			// 	return num1+num2+num3
			// }
			// function sum(...num){
			// 	console.log(num);
			// }
			// sum(20,122,2323,23,23,23,234)
		</script>
	</body>
</html>

```

### 阶段案例

#### 书籍购物车

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<link rel="stylesheet" href="style.css">
        <style>
        table{
	border:1px solid #e9e9e9;
	border-collapse: collapse;
	border-spacing: 0;
}
th,td{
	padding:8px 16px;
	border: 1pxx solid #E9E9E9;
	text-align: left;
}
th{
	background-color: #f7f7f7;
	color: #5c6b77;
	font-weight: 600;
}
        </style>
	</head>
	<body>
		<div id="app">
			<div v-if="books.length">
				<table>
				 <thead>
					 <tr>
						 <th></th>
						 <th>书籍</th>
						 <th>出版日期</th>
						 <th>价格</th>
						 <th>购买数量</th>
						 <th>操作</th>
					 </tr>
				 </thead>
				 <tbody>
					 <tr v-for="(item,index) in books">
					 	<td>{{item.id}}</td>
					 	<td>{{item.name}}</td>
					 	<td>{{item.date}}</td>
					 	<td>{{item.price|showPrice}}</td>
					 	<td>
							<button @click="decrement(index)" v-bind:disabled="item.count<=	1">-</button>
						{{item.count}}
						<button @click="increment(index)">+</button>
						</td>
						<td><button @click="removeHandle">移除</button></td>
					 </tr>
				 </tbody>
				</table>
				<h2>总价格:{{totalPrice|showPrice}}</h2>
			</div>
			<h2 v-else>购物车为空</h2>
		</div>
		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
		<script src="./main.js" type="text/javascript" charset="utf-8"></script>
        <script>
        const app=new Vue({
	el:'#app',
	data:{
		books:[
			{
				id:1,
				name:'《算法导论》',
				date:'2012-8',
				price:86.55,
				count:1
			},
			{
				id:2,
				name:'《UNIX编程艺术》',
				date:'2013-5',
				price:89.55,
				count:1
			},
			{
				id:3,
				name:'《编程高手》',
				date:'2015-8',
				price:96.55,
				count:1
			},
			{
				id:4,
				name:'《机器学习》',
				date:'2019-8',
				price:56.55,
				count:1
			}
		]
	},
	methods:{
		// getFinalPrice(price){
		// 	return '¥'+price.toFixed(2)
		increment(index) {
			this.books[index].count++
		},
		decrement(index) {
			this.books[index].count--
		},
		removeHandle(index){
			this.books.splice(index,1)
		}
		},
		computed:{
			totalPrice(){
				let totalPrice=0;
				for(let i=0;i<this.books.length;i++){
					totalPrice +=this.books[i].price*this.books[i].count
				}
				return totalPrice
			}
		},
		filters:{
			showPrice(price){
				return  '¥' +price.toFixed(2)
			}
		}
})
        </script>
	</body>
</html>

```

#### 表单绑定v-model

- 表单控件在实际开发中是非常常见的。特别是对于用户信息的提交，需要大量的表单。
- Vue中使用v-model指令实现表单元素和数据的双向绑定。
- 案例的解析：
  - 当我们在输入框输入内容时
  - 因为input中的v-model绑定了message，所以会时将输入的内容传递给message，message发生改变。
  - 当message发生改变时，因为上面我们使用Mustache语法，将message的值插入到DOM中，所以DOM会发生响应的改变。
  - 所以，通过v-model实现了双向的绑定。
- 当然，我们也可以将v-model用于textarea元素

```html
<textarea v-model="message"></textarea>
<p>输入的内容是:{{message}}</p>


<div id="#app">
<input type="text" v-model="message" 
       <h2>
    {{message}}
    </h2>
</div>
<script src="../js/vue.js"></script>
<script>
let app=new Vue({
    el:'#app',
    data:{
        message:''
    }
})
</script>
```

#### v-model原理

- v-model其实是一个语法糖，它的背后本质上是包含两个操作:
  - 1.v-bind绑定一个value属性
  - 2.v-on指令给当前元素绑定input事件
- 也就是说下面的代码：等同于下面的代码：

```html
<input type="text" v-model="message"/>
等同于
<input type="text" v-bind:value="message" v-on:input ="message = $event.target.value"/>
```

#### v-model:radio

- 当存在多个单选框时

```html
<div id="app">
    <label for="male">
    <ibput type="radio" :value="abc" v-model="gender" id="male">男
    </label>
    <label for="female">
    <input type="radio" value="female" v-model="gender" id="female">女    
    </label>
        <p>您的选择:{{gender}}</p>
</div>
<script src="../js/vue.js"></script>
<script>
let  app= new Vue({
    el:'#app',
    data:{
        gender:'',
        abc:'male'
    }
})
    </script>
```

#### v-model:checkbox

- 复选框分为两种情况：单个勾选框和多个勾选框

- 单个勾选框：
  - v-model即为布尔值。
  - 此时input的value并不影响v-model的值。

#### v-model:select

- 和checkbox一样，select也分单选和多选两种情况。
- 单选：只能选中一个值。
  - v-model绑定的是一个值。
  - 当我们选中option中的一个时，会将它对应的value赋值到mySelect中

```html
<!--选择一个值-->
<select v-model="mySelect">
    <option value="apple">苹果</option>
    <option value="orange">橘子</option>
    <option value="banana">香蕉</option>
</select>
<p> 您最喜欢的水果:{{mySelect}}</p>

<!--选择多个值-->
<select v-model="mySelects" multiple>
    <option value="apple">苹果</option>
    <option value="orange">橘子</option>
    <option value="banana">香蕉</option>
</select>
<p> 您最喜欢的水果:{{mySelects}}</p>
<script>
let app=new Vue({
    el:'#app',
    data:{
        mySelect:'apple',
        mySelects:[]
    }
})
</script>
```

#### v-model值绑定

- 初看Vue官方值绑定的时候，我很疑惑：what the hell is that？
- 但是仔细阅读之后，发现很简单，就是动态的给value赋值而已：
  - 我们前面的value中的值，可以回头去看一下，都是在定义input的时候直接给定的。
  - 但是真实开发中，这些input的值可能是从网络获取或定义在data中的。
  - 所以我们可以通过v-bind:value动态的给value绑定值。
  - 这不就是v-bind吗？
- 这不就是v-bind在input中的应用吗？搞得我看了很久，搞不清楚他想讲什么。
- 这里不再给出对应的代码，因为会用v-bind，就会值绑定的应用了。

#### v-model修饰符

- lazy修饰符：
  - 默认情况下，v-model默认是在input事件中同步输入框的数据的。
  - 也就是说，一旦有数据发生改变对应的data中的数据就会自动发生改变。
  - lazy修饰可以让数据在失去焦点或者回车时才会更新。
- number修饰符：
  - 默认情况下，在输入框中无论我们输入的是字母还是数字，都会被当做字符串类型进行处理。
  - 但是如果我们希望处理的是数字类型，那么最好直接将内容当做数字处理。
  - number修饰符可以让在输入框输入的内容自动转成数字类型。
- trim修饰符：
  - 如果输入的内容首尾有很多空格，通常我们希望将其去除。
  - trim修饰符可以过滤内容左右两边的空格。

### 什么是组件化？

- 人面对复杂问题的处理方式：

  - 任何一个处理信息的逻辑能力都是有限的
  - 所以，当面对一个非常复杂的问题时，我们不太可能一次性搞定一大堆的内容。
  - 但是，我们人有一种天生的能力，就是将问题进行拆解。
  - 如果将一个复杂的问题，拆分成很多个可以处理的小问题，再将其放在整体当中，你会发现大的问题也会迎刃而解。

- 组件化也是类似的思想：

  - 如果我们将一个页面中所有的处理逻辑全部放在一起，处理起来就会变得非常复杂，而且不利于后续的管理以及扩展。
  - 但是如果，我们讲一个页面拆分成一个一个小的功能块，每个功能块完成属于自己这部分独立的功能，那么之后整个页面的管理和维护就变得非常容易了。

  ![](C:\Users\86157\Desktop\百家号图片搜集\组件.png)

- 我们将一个完整的页面分成很多个组件。
- 每个组件都用于实现页面的一个功能块。
- 而每一个组件又可以进行细分。

#### Vue组件化思想

- 组件化是Vue.js中的重要思想
  - 它提供了一种抽象，让我们可以开发出一个一个独立可复用的小组件来构造我们的应用。
  - 任何的应用都会被抽象成一颗组件树。

![](C:\Users\86157\Desktop\百家号图片搜集\vue组件化思想.jpg)





- 组件化思想的应用：
  - 有了组件化的思想，我们在之后的开发中就要充分的利用它。
  - 尽可能的将页面拆分成一个一个小的、可复用的组件。
  - 这样让我们的代码更加方便组织和管理，并且扩展性也更强。
- 所以，组件是Vue开发中，非常重要的一个篇章，要认真学习。

#### 注册组件的基本步骤

- 组件的使用分成三个步骤：

  - 创建组件构造器
  - 注册组件
  - 使用组件

- 我们来看看通过代码如何注册组件
- 查看运行结果：
  - 和直接使用一个div看起来并没有什么区别。
  - 但是我们可以设想，如果很多地方都要显示这样的信息，我们是不是就可以直接使用&lt;my-cpn&gt;&lt;/my-cpn&gt;来完成呢？

![](C:\Users\86157\Desktop\百家号图片搜集\注册.png)

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
	</head>
	<body>
		<div id="app">
			<!-- 3.使用组件 -->
			<my-cpn></my-cpn>
		</div>
		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
		<script>
			//ES6
			
			//1.创建组件构造器对象
		 const cpnC =	Vue.extend({
			 template:`
			 <div>
			 <h2>我是标题</h2>
			 <p>我是raper</p>
			 <p>我是beatboxer</p>
			 </div>
			 `
		 })
			//2.注册组件
			Vue.component('my-cpn',cpnC)
            	
            const app = new Vue({
				 	el:'#app',
			data:{message:'VueJS'},
			})
		</script>
	</body>
</html>

```

#### 注册组件步骤解析

- 这里的步骤都代表什么含义呢？
- Vue.extend():
  - 调用Vue.extend()创建的是一个组件构造器。
  - 通常在创建组件构造器时，传入template代表我们自定义组件的模板。
  - 该模板就是在使用到组件的地方，要显示的HTML代码。
  - 事实上，这种写法在Vue2.x的文档中几乎已经看不到了，它会直接使用下面我们会讲到的语法糖，但是在很多资料还是会提到这种方式，而是这种方式是学习后面方式的基础。

- Vue.component():
  - 调用Vue.component()是将刚才的组件构造器注册为一个组件，并且给它起一个组件的标签名称。
  - 所以需要传递两个参数：1、注册组件的标签名 2.组件构造器

- 组件必须挂载在某个Vue实例下，否则它不会生效。
  - 我们来看下面我使用了三次&lt;my-cpn&gt;&lt;my-cpn&gt;
  - 而第三次其实并没有生效：
- 第三步的解析：

![](C:\Users\86157\Desktop\百家号图片搜集\解析.png)

#### 全局组件和局部组件

- 当我们通过调用Vue.component()注册组件时，组件的注册是全局的
  - 这意味着该组件可以在任意Vue示例下使用
- 如果我们注册的组件是挂载在某个实例中，那么就是一个局部组件

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
	</head>
	<body>
		<div id="app">
		<cpn></cpn>
		</div>
		<div id="app2">
		<cpn></cpn>
		</div>
		<cpn></cpn>
		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
		<script>
			
			//1.创建组件构造器
			const cpnC = Vue.extend({
				template:`
				<div>
				 <h2>我是标题</h2>
				 <p>我是rap，我是beatbox</p>
				</div>
				`
			})
			//2.注册组件(全局组件，意味着可以在多个Vue的实例下面使用)
			// Vue.component('my-cpn',cpnC)
			
			//怎么注册的组件才是局部组件了？
			const app = new Vue({
				el: '#app',
				data: {
					message: 'VueJS'
				},
				components:{
					//cpn使用组件时的标签名
					cpn: cpnC
				}
			})
			const app2 = new Vue({
				el:'#app2'
			})
			
		</script>
	</body>
</html>

```

#### 父组件和子组件

- 在前面我们看到了组件树：
  - 组件和组之间存在层级关系
  - 而其中一种非常重要的关系就是父子组件的关系
- 我们来看通过代码如何组成的这种层级关系：
- 父子组件错误用法：以子标签的形式在Vue实例中使用
  - 因为当子组件注册到父组件的components时，Vue会编译好父组件的模块
  - 该模块的内容已经决定了父组件将要渲染的HTML（相当于父组件中已经有了子组件中的内容了）
  - &lt;child-cpn&gt;&lt;/child-cpn&gt;是只能在父组件中被识别的
  - 类似这种用法，&lt;child-cpn&gt;&lt;/child-cpn&gt;是会呢浏览器忽略的

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
	</head>
	<body>
		<div id="app">
			<cpn1></cpn1>
		<cpn2></cpn2>
		</div>
		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
		<script>
			
			//1.创建第一个组件(子组件)
			const cpnC1= Vue.extend({
				template:`
				<div>
				<h2>我是raper001</h2>
				<p>我是beatboxer001</p>
				</div>
				`
			})
			
			//2.创建第二个组件构造器(父组件)
			const cpnC2 = Vue.extend({
				template:`
				<div>
				<h2>我是raper002</h2>
				<p>我是beatboxer002</p>
				<cpn1></cpn1>
				</div>
				`,
				components:{
					cpn1:cpnC1
				}
			})
			//root组件
			const app = new Vue({
				el: '#app',
				data: {
					message: 'VueJS'
				},
				components:{
					cpn2:cpnC2,
					cpn1:cpnC1
				}
			})
		</script>
	</body>
</html>
```

#### 注册组件语法糖

- 在上面注册组件的方式，可能会有些繁琐
  - Vue为了简化这个过程，提供了注册的语法糖
  - 主要是省去了调用Vue.extend()的步骤，而是可以直接使用一个对象来代替
- 语法糖注册全局组件和局部组件：

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
	</head>
	<body>
		<div id="app">
		<cpn1></cpn1>
		<cpn2></cpn2>
		</div>
		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
		<script>
			
			//1.全局组件注册的语法糖
			//1.创建组件构造器
			// const cpn1= Vue.extend({
			// 	template:`
			// 	<div>
			// 	<h2>我是raper001</h2>
			// 	<p>我是beatboxer001</p>
			// 	</div>
			// 	`
			// })
			
			//2.注册组件
			Vue.component('cpn1',{
				template:`
				<div>
				<h2>我是raper001</h2>
				<p>我是beatboxer001</p>
				</div>
				`
			})
			const app = new Vue({
				el: '#app',
				data: {
					message: 'VueJS'
				},
				components:{
					'cpn2' :{
						template:`
				<div>
				<h2>我是raper002</h2>
				<p>我是beatboxer002</p>
				<cpn1></cpn1>
				</div>
				`
					}
				}
			})
		</script>
	</body>
</html>
```

#### 模板的分离写法

- 我们通过语法糖简化了Vue组件的注册过程，另外还有一个地方的写法比较麻烦，就是template模块写法。
- 如果我们能将其中的HTML分离出来写,然后挂载到对应的组件上，必须结构会变得非常清晰。
- Vue提供了两种方案来定义HTML模块内容：
  - 使用&lt;script&gt;&lt;/script&gt;标签
  - 使用&lt;template&gt;&lt;/template&gt;标签

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
	</head>
	<body>
		<div id="app">
		<cpn></cpn>
		</div>
		<!-- 1.script标签，注意：类型必须是text/x-handlebars-template -->
		<!-- <script type="text/x-handlebars-template" id="cpn">
		<div>
		<h2>我是raper002</h2>
		<p>我是beatboxer002</p>
		</div>
		</script> -->
		
		<!-- 2.template标签	 -->
		<template id="cpn">
			<div>
			<h2>我是raper002</h2>
			<p>我是beatboxer003</p>
			</div>
		</template>
		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
		<script>
			//1.注册一个全局组件
			Vue.component('cpn',{
				template:'#cpn'
			})
			const app = new Vue({
				el: '#app',
				data: {
					message: 'VueJS'
				}
			})
		</script>
	</body>
</html>
```

#### 组件可以访问Vue实例数据吗？

- 组件是一个单独功能模块的封装：

  - 这个模块有属于自己的HTML模板，也应该有属性自己的数据data

- 组件中的数据是保存在哪里呢？顶层的Vue实例中吗？

  - 我们先下测试一下，组件中能不能直接访问Vue实例中的data
  - 我们发不能访问，而且即使可以访问，如果将所有的数据都放在Vue实例中，Vue实例就会变的非常臃肿
  - 结论：Vue组件应该有自己保存数据的地方

  ![](C:\Users\86157\Desktop\百家号图片搜集\数据1.png)

#### 组件数据的存放

- 组件自己的数据存放在哪里呢？
  
  - 组件对象也有一个data属性（也可以有methods等属性，下面我们有用到）
  - 只是这个data属性必须是一个函数
  - 而且这个函数返回一个对象，对象内部保存着数据
  
  ![](C:\Users\86157\Desktop\百家号图片搜集\数据2.png)

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
	</head>
	<body>
		<div id="app">
		<cpn></cpn>
		</div>
		<template id="cpn">
			<div>
				<h2>{{title}}</h2>
				<p>beatboxer</p>
			</div>
		</template>
		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
		<script>
			Vue.component('cpn', {
				template: '#cpn',
				data() {
					return {
						title: 'RAPER'
					}
				}
			})
			const app = new Vue({
				el: '#app',
				data: {
					message: 'VueJS'
				}
			})
		</script>
	</body>
</html>
```

#### 父子组件的通信

- 在上一个小节中，我们提到了子组件是不能引用父组件或者Vue实例的数据
- 但是，在开发中，往往一些数据确实需要从上层传递到下层：
  - 比如在一个页面中，我们从服务器请求到了很多的数据。
  - 其中一部分数据，并非是我们整个页面的大组件来展示的，而是需要下面的子组件进行展示。
  - 这个时候，并不会让子组件再次发送一个网络请求，而是直接让**大组件**(**父组件**)将数据传递给**小组件**（**子组件**）
- 如何进行父子组件间的通信呢？Vue官方提到
  - 通过props向子组件传递数据
  - 通过事件向父组件发送消息

![](C:\Users\86157\Desktop\百家号图片搜集\子父传递.png)



- 在下面的代码中，我直接将Vue实例当做父组件，并且其中包含子组件来简化代码
- 真实的开发中，Vue实例和子组件的通信，和父组件，还有子组件的通信过程是一样的

#### props基本用法

- 在组件中，使用选项props来声明需要从父级接收到的数据
- props的值有两种方式:
  - 方式一：字符串数组，数组中的字符串就是传递时的名称
    - 方式二：对象，对象可以设置传递时的类型，也可以设置默认值等

- 我们先来看一个最简单的props传递：

![](C:\Users\86157\Desktop\百家号图片搜集\props.png)

#### props数据验证

- 在前面，我们的props选项是使用一个数组

- 我们说过，除数组之外，我们也可以使用对象，当需要对props进行类型等验证时，就需要对象写法了

- 验证都支持哪些数据类型呢？

  - String
  - Number
  - Boolean
  - Array
  - Object
  - Date
  - Function
  - Symbol

  ```js
  function Person(firstname,lastname){
      this.firstname = firstName
      this.lastname = lastname
  }
  Vue.component('blog-post',{
      props:{
          author:Person
      }
  })
  
  Vue.component('my-component',{
      props:{
          //基础的类型检查（'null'匹配任何类型）
          propA:Number,
          //多个可能的类型
          propB:[String,Number],
          //必填的字符串
          propC:{
              type:String,
              required:true
          },
          //带有默认值的数字
          propD:{
              type: Number,
              default:100
          },
          //带有默认值的对象
          propE:{
              type:Object,
              //对象或数组默认值必须从一个工厂函数获取
              default: function(){
                  return {
                      message:'你好'
                  }
              },
              //自定义验证函数
              propF:{
                  validator:function(value){
                      //这个值必须匹配下列字符串中的一个
                      return['bad','good','best'].indexOf(value)!==-1
                  }
              }
          }     
  })
  ```


#### 子级向父级传递

- props用于父组件向子组件传递数据，还有一种比较常见的是子组件传递数据或事件到父组件中
- 我们应该如何处理呢？这个时候，我们需要使用自定义事件来完成
- 什么时候需要自定义事件呢?
  - 当子组件需要向父组件传递数据时，就要用到自定义事件了
  - 我们之前学习的v-on不仅仅可以用于监听DOM事件，也可以用于组件间的自定义事件。
- 自定义事件的流程：
  - 在子组件中，通过$emit()来触发事件
  - 在父组件中，通过v-on来监听子组件事件
- 我们来看一个简单的例子：
  - 我们之前做过一两个按钮+1和-1，点击后修改counter
  - 我们整个操作的过程还是子组件中完成，但是之后的展示交给父组件
  - 这样，我们就需要将子组件中的counter，传递给父组件的某个属性，比如total

#### 自定义事件代码

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
	</head>
	<body>
		<div id="app">
			<!-- 发生两个事件时，调用一个函数changeTotal -->
		<child-cpn @increment="changeTotal" @decrement='changeTotal'></child-cpn>
		<h2>点击次数：{{total}}</h2>
		</div>
		<template id="childCpn">
			<div>
				<button @click="increment">+1</button>
				<button @click="decrement">-1</button>
			</div>
		</template>
		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
		<script>
			let app = new Vue({
				el: '#app',
				data: {
				total: 0
				},
				methods:{
					changeTotal(counter){
						this.total=counter
					}
				},
				components:{
					'child-cpn':{
						template:'#childCpn',
						data(){
							return{
								counter:0
							}
						},
						methods:{
							increment(){
								//1.子组件发生事件
								//2.在使用child-cpn使用
								//通过@increment和@decrement监听事件
								this.counter++;
								this.$emit('increment',this.counter)
							},
							decrement(){
								this.counter--;
								this.$emit('decrement',this.counter)
							}
							
						}
					}
				}
			})
		</script>
	</body>
</html>
```

#### 父子组件的访问方式:$children

- 有时候我们需要父组件直接访问子组件，子组件直接访问父组件，或者是子组件访问跟组件。
  - 父组件访问子组件:使用$children或$refs
  - 子组件访问父组件:使用$parent
- 我们先看下$children的访问
  - this.$children是一个数组类型,它包含所有子组件对象。
  - 我们这里通过一个遍历,取出所有子组件的message状态。

### 插槽slot

#### 为什么使用slot

- slot翻译为插槽：
  - 在生活中很多地方都有插槽，电脑的USB插槽，插板当中的电源插槽。
  - 插槽的目的是人我们原来的设备具备更多的扩展性。
  - 比如电脑的USB我们可以插入U盘、硬盘、手机、音响、键盘、鼠标等等。
- 组件的插槽：
  - 组件的插槽也是为了让我们封装的组件更加具有扩展性。
  - 让使用者可以决定组件内部的一些内容到底展示什么。

- 例子：移动网站中的导航栏
  - 移动开发中，几乎每个页面都有导航栏。
  - 导航栏我们必然会封装成一个插件，比如nav-bar组件。
  - 一旦有了这个组件，我们就可以在多个页面中复用。

#### 如何封装这类组件呢？slot

- 如何去封装这类的组件呢？
  - 它们也很多区别，但是也有很多共性。
  - 如果，我们每一个单独去封装一个组件，显然不合适:比如每个页面都返回，这部分内容我们就要重复去封装。
  - 但是，如果我们封装成一个，好像也不合理：有些左侧是菜单，有些是返回，有些中间是搜索，有些是文字,等等
- 如何封装合适呢?抽取共性，保留不同。
  - 最好的封装方式就是将共性抽取到组件中，将不同暴露为插槽。
  - 一旦我们预留了插槽，就可以让使用者根据自己的需求，决定插槽中插入什么内容。
  - 是搜索框，还是文字，还是菜单。由调用者自己来决定。
- 这就是为什么我们要学习组件中的插槽slot的原因。

#### slot基本使用

- 了解了为什么用slot，我们再来谈谈如何使用slot？

  - 在子组件中，使用特殊的元素&lt;slot&gt;就可以为子组件开启一个插槽。
  - 该插槽插入什么内容取决于父组件如何使用。

- 我们通过一个简单的例子，来给子组件定义一个插槽：

  - &lt;slot&gt;中的内容表示，如果没有在该组件中插入任何其他内容，就默认显示该内容

  - 有了这个插槽后，父组件如何使用呢？

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
	</head>
	<body>
		
		<!-- 1.插槽的基本使用 <slot></slot>
		 2.插槽的默认值，<slot>button</slot>
		 3.如果有多个值，同时放入到组件进行替换时，一起作为替换元素
		 -->
		<div id="app">
			<cpn></cpn>
			<cpn><span>你好</span></cpn>
			<cpn>
				<i>万物</i>
				<div>我是div元素</div>
				<p>我是p标签</p>
			</cpn>
			<cpn></cpn>
		</div>
		
		<template id="cpn">
			<div>
				<h2>我是rapper</h2>
				<p>我是beatboxer</p>
				<slot><button type="button">按钮</button></slot>
			</div>
		</template>
		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
		<script>
			const app = new Vue({
				el: '#app',
				data: {
					message: 'VueJS'
				},
				components:{
					cpn:{
						template:'#cpn'
					}
				}
			})
		</script>
	</body>
</html>
```

#### 具名插槽slot

- 当子组件的功能复杂时，子组件的插槽可能并非是一个。

  - 比如我们封装一个导航栏的子组件，可能就需要三个插槽，分别代表左边、中间、右边。
  - 那么，外面在给插槽插入内容时，如何区分插入的是哪一个呢？
  - 这个时候，我们就需要给插槽起一个名字

- 如何使用具名插槽呢？

  - 非常简单，只要给slot元素一个name属性即可
  - &lt;slot name='myslot'&gt;&lt;/slot&gt;

- 我们给出一个案例：

  - 这里我先不对导航组件做非常复杂的封装，先了解具名插槽的用法。

  ```html
  <!DOCTYPE html>
  <html>
  	<head>
  		<meta charset="utf-8">
  		<title></title>
  	</head>
  	<body>
  		<div id="app">
  			<cpn><span slot="center">标题</span></cpn>
  			<cpn><button slot="left">返回</button></cpn>
  		</div>
  		<template id="cpn">
  			<div>
  				<slot name="left"><span>左边</span></slot>
  				<slot name="center"><span>中间</span></slot>
  				<slot name="right"><span>右边</span></slot>
  				<slot></slot>
  			</div>
  		</template>
  		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
  		<script>
  			const app = new Vue({
  				el: '#app',
  				data: {
  					message: 'VueJS'
  				},
  				components:{
  					cpn:{
  						template:'#cpn'
  					}
  				}
  			})
  		</script>
  	</body>
  </html>
  ```

#### 编译作用域

- 在真正学习插槽之前，我们需要先理解一个概念：编译作用域。
- 官方对于编译的作用域解析比较简单，我们自己来通过一个例子来理解这个概念：
- 我们来考虑下面的代码是否最终是可以渲染出来的：
  - &lt;my-cpn v-show="isShow"&gt;&lt;/my-cpn&gt;中，我们使用了isShow属性。
  - isShow属性包含在组件中，也包含在Vue实例中。

```html
<div id="app">
    <my-cpn v-show="isShow"></my-cpn>
</div>

<template id="myCpn">
    <h2>我能不能显示出来</h2>
</template>
<script src="../js/vue.js"></script>
<script>
Vue.component('my-cpn',{
    template:'#myCpn',
    data(){
        teturn{
            isShow:false
        }
    }
})
    let app = new Vue({
        el:'#app',
        data:{
            isShow:true
        }
    })
</script>
```

- 答案：最终可以渲染出来，也就是使用的是Vue实例的属性。
- 为什么呢？
  - 官方给出了一条准则：父组件模板的所有东西都会在父级作用域内编译；子组件模板的所有东西都会在子级作用域内编译。
  - 而我们在使用&lt;my-cpn  v-show="isShow"&gt;&lt;/my-cpn&gt;的时候，整个组件的使用过程是相当于在父组件中出现的。
  - 那么他的作用域就是父组件，使用的属性也是属于父组件的属性。
  - 因此，isShow使用的是Vue实例中的属性，而不是子组件的属性。

#### 作用域插槽：准备

- 作用域插槽是slot一个比较难理解的点，而且官方文档说的又有点不清晰。
- 这里，我们用一句话对其做一个总结，然后我们在后续的案例中来体会：
  - 父组件替换插槽的标签，但是内容由子组件来提供。
- 我们先提一个需求：
  - 子组件中包括一组数据，比如：pLanguages:['JavaScript','Python','Swift','Go','C++']
  - 需求在多个界面进行展示：
    - 某些界面是以水平方向——展示的
    - 某些界面是以列表形式展示的
    - 某些界面直接展示一个数组
  - 内容在子组件，希望父组件告诉我们如何展示，怎么办呢？
    - 利用slot作用域插槽就可以了

- 我们来看看子组件的定义：

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
	</head>
	<body>
		<div id="app">
			<cpn></cpn>
			<cpn>
			<!-- 目的是获取子组件中的PLanguages -->
			<template slot-scope="slot">
				<!-- <span v-for="item in slot.data">{{item}}--</span> -->
				<span>{{slot.data.join(' - ')}}</span>
			</template>
			</cpn>
		</div>
		<template id="cpn">
			<div>
				<slot :data="pLanguges">
					<ul>
						<li v-for="item in pLanguges">{{item}}</li>
					</ul>
				</slot>
			</div>
		</template>
		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
		<script>
			const app = new Vue({
				el: '#app',
				data: {
					message: 'VueJS'
				},
				components:{
					cpn:{
						template:'#cpn',
						data(){
							return {
								pLanguges:['JavaScript','c++','c#','Python','Go','Swift']
							}
						}
					}
				}
			})
		</script>
	</body>
</html>
```

#### 作用域插槽：使用

- 在父组件使用我们的子组件时，从子组件中拿到数据：

  - 我们通过&lt;template slot-scope="slotProps"&gt;获取到slotProps属性
  - 在通过slotProps.data就可以获取到刚才我们传入的data

  ```html
  <div id="app">
      <!--列表形式展示-->
      <my-cpn>
          <template slot-scope="slotProps">
              <ul><li v-for="info in slotProps.data">{{info}}</li></ul>
          </template>
      </my-cpn>
      <!--水平展示-->
      <my-cpn>
          <template slot-scope="slotProps">
              <span v-for="info in slotProps.data">{{info}}</span>
          </template>
      </my-cpn>
  </div>
  ```


### 模块化开发

#### JavaScript原始功能

- 在网页开发的早期，js制作作为一种脚本语言，做一些简单的表单验证或动画实现等，那个时候代码还是很少的。
  - 那个时候的代码是怎么写的呢？直接将代码写在&lt;script&gt;标签中即可
- 随着ajax异步请求的出现，慢慢形成了前后端的分离
  - 客户端需求完成的事情越来越多，代码量也是与日俱增。
  - 为了应对代码量的剧增，我们通常会将代码组织在多个js文件中，进行维护。
  - 但是这种维护方式，依然不能避免一些灾难性的问题。

- 比如全局变量同名问题：看右边的例子

```html
<script>
	document.getElementById('button').onclick=function(){
        console.log('按钮发生了点击');
    }
</script>
```

```js
//aaa.js文件中，小明定义一个变量，名称是flag，并且为true
flag = true
//bbb.js文件中，小明也喜欢用flag这个变量名称，只是为false
flag = false
//main.js文件中，小明想通过flag进行一些判断，完成后续的事情
if(flag){
    console.log("努力学习");
}

```

- 小明发现代码不能正常运行，去检查自己的变量，发现确实true
- 最后悲剧发生了，小明加班到2点还是没有找到问题出在哪了（所以加班无意义，yes）
- 另外，这种代码的编写方式对js文件的依赖顺序几乎是强制性的
  - 但是当js文件过多，比如有几十个的时候，弄清楚他们的顺序是一件比较同时的事情。
  - 而且即使你弄清楚顺序了，也不能避免上面出现的这种尴尬问题的发生

#### 匿名函数的解决方案

- 我们可以使用匿名函数来解决方面的重名问题

  - 在aaa.js文件中，我们使用匿名函数

  ```js
  (function(){
      var flag = true
  })()
  ```

- 但是如果我们希望在main.js文件中，用到flag，应该如何处理呢？

  - 显然，另外一个文件中不容易使用，因为flag是一个局部变量。

#### 使用模块作为出口

- 我们可以使用将需要暴露到外面的变量，使用一个模块作为出口，什么意思呢？
- 来看下对应的代码：
- 我们做了什么事情呢？
  - 非常简单，在匿名函数内部，定义一个对象。
  - 给对象添加各种需要暴露到外面的属性和方法（不需要暴露的直接定义即可）。
  - 最后将这个对象返回，并且在外面使用了一个MoudleA接受。
- 接下来，我们在main.js中怎么使用呢？
  - 我们只需要使用属于自己模块的属性和方法即可
- 这就是模块最基础的封装，事实上模块的封装还有很多高级的话题：
  - 但是我们这里就是要认识一下为什么需要模块，以及模块的原始雏形。
  - 幸运的是，前端模块化开发已经有了很多既有的规范，以及对应的实现方案。

```js
var MoudleA = (function(){
    //1.定义一个对象
    var obj = {}
    //2.在对象内部添加变量和方法
    obj.flag = true
    obj.myFunc = function (info) {
        console.log(info);
        //3.将对象返回
        return obj
    }
})()

if(MoudleA.flag){
    console.log('我是rapper');
}
ModuleA.myFunc('我是beatboxer')

console.log(ModuleA);
```

- 常见的模块化规范:
  - CommonJS、AMD、CMD，也有ES6的Moudles

#### CommonJS（了解）

- 模块化有两个核心：导入和导出


- CommonJS的导出：

```js
module.exports = {
    flag: true,
    test(a,b){
        return a+b
    },
    demo(a,b){
        return a*b
    }
}
```

- CommonJS的导入

```js
//CommonJS模块
let {test,demo,flag} = require('MoudleA');

//等同于
let _mA = require('moduleA');
let test = _mA.test;
let demo= _mA.demo;
let flag= _mA.flag;
```

#### export基本使用

- export指令用于导出变量，比如下面的代码：

```js
//info.js
export let name = 'Bob'
export let age = 11
export let height = 1.99
```

- 上面的代码还有另外一种写法：

```js
//info.js
let name = 'Joe'
let age = 22
let height= 1.98

export {name,age,height}
```

#### 导出函数或类

- 上面我们主要是输出变量，也可以输出函数或者输出类

  - 上面的代码也可以写成这种形式：

  ```js
  export function test(content){
      console.log(content);
  }
  
  export class Person(){
      constructor(name,age){
          this.name = name;
          this.age = age;
      }
      run(){
          console.log(this.name + '在运行中');
      }
  }
  ```

  ```js
  function test(content){
      console.log(content);
  }
  
   class Person(){
      constructor(name,age){
          this.name = name;
          this.age = age;
      }
      run(){
          console.log(this.name + '在运行中');
      }
  }
  
  export {test,Person}
  ```

#### export default

- 某些情况下，一个模块中包含某个的功能，我们并不希望给这个功能命名，而且让导入者可以自己来命名

  - 这个时候就可以使用export default

  ```js
  //info.js
  export default function(){
      console.log('default function	');
  }
  
  ```

- 我们来到main.js中，这样使用就可以了

  - 这里的myFunc是我自己命名的，你可以根据需要命名它对应的名字

  ```js
  import myFunc from './info.js'
  
  myFunc()
  ```

- 另外，需要注意：

  - export default在同一个模块，不允许同时存在多个。

#### import使用

- 我们使用export指令导出了模块对外提供的接口，下面我们就可以通过import命令来加载对应的这个模块了
- 首先，我们需要在HTML代码中引入两个js文件，并且类型需要设置为module

```html
<script src="info.js" type="module"></script>
<script src="main.js" type="module"></script>
```

- import指令用于导入模块中的内容，比如main.js的代码

```js
import {name,age,height} from"./info.js"

console.log(name,age,height);
```

- 如果我们希望某个模块中所有的信息都导入，一个个导入显然有些麻烦：

  - 通过*可以导入模块中所有的export变量
  - 但是通常情况下我们需要给*起一个别名，方便后续的使用

  ```js
  import *as info "./info.js"
  
  console.log(info.name,info.height,info.friends);
  ```


### Webpack内容

- 认识webpack
- webpack的安装
- webpack的起步
- webpack的配置
- loader的使用
- webpack中配置Vue
- plugin的使用
- 搭建本地服务器

#### 什么是Webpack？

- 什么是webpack？

  - 这个webpack还真不是一两句话可以说清楚的。

- 我们先看看官方的解释：

  - At its core，webpack is a static  bundler for modern JavaScript applications
  - 从本质上来讲，webpack是一个现代的JavaScript应用的静态模块打包工具

- 但是它是什么呢？用概念解释概念，还是不清晰

  - 我们从两个点来解释上面这句话：模块 和  打包

  ![](C:\Users\86157\Desktop\百家号图片搜集\link.png)

#### 前端模块化

- 前端模块化：
  - 在前面学习中，我已经用了大量的篇幅解释了为什么前端需要模块化
  - 而且我也是提到了目前使用前端模块化的一些方案：AMD、CMD、CommonJS、ES6.
  - 在ES6之前，我们要想进行模块化开发，就必须借助于其他的工具，让我们可以进行模块化开发
  - 并且在通过模块化开发完成了项目后，还需要处理模块间的各种依赖，并且将其进行整合打包
  - 而webpack其中一个核心就是让我们可能进行模块化开发，并且会帮助我们处理模块间的依赖关系
  - 而且不仅仅JavaScript文件，我们的CSS、图片、json文件等等在webpack中都可以被当做模块来使用
  - 这就是webpack中模块化的概念

- 打包如何理解呢？

  理解了webpack可以帮助我们进行模块化，并且处理模块化间的各种复杂关系后，打包的概念就非常好理解了

  就是将webpack中的各种资源模块进行打包合成一个或多个包（Bundle）

  并且在打包的过程中，还可以对资源进行处理，比如压缩图片，将scss转成css，将ES6语法转成ES5语法，将TypeScript转成JavaScript等等操作

  但是打包的操作似乎grunt/gulp也可以帮助我们完成，他们有什么不同呢？


#### 和grunt/gulp的对比

- grunt/gulp的核心是Task

  - 我们可以配置一系列的task，并且定义task要处理的事务（例如ES6、ts转化、图片压缩、scss转成css）
  - 之后让grunt/gulp来依次执行这些task，而且让整个流程自动化。
  - 所以grunt/gulp也被称为前端自动化任务管理工具。

- 我们来看一个gulp的task

  - 下面的task就是将src下面的所有js文件转成ES5的语法。
  - 并且最终输出到dist文件夹中。

- 什么时候用grunt/gulp呢？

  - 如果你的工程模块化依赖非常简单，甚至是没有用到模块化的概念。
  - 只需要进行简单的合并、压缩，就使用grunt/gulp即可。
  - 但是如果整个项目使用了模块化管理，而且相互依赖非常强，我们就可以使用更加强大的webpack了

  ```js
  const gulp = require('gulp');
  const babel = require('gulp-babel');
  
  gulp.task('js',()=>
           gulp.src('src/*.js')
            .pipe(babel({
      presets: ['es2015']
  }))
      .pipe(gulp.dest('dist'))
           );
  ```

- 所以,grunt/gulp和webpack有什么不同呢？

  - grunt/gulp更加强调的是前端流程的自动化，模块化不是它的核心。
  - webpack更加强调模块化开发管理，而文件压缩合并、预处理等功能，是他附带的功能。

#### 准备工作

- 我们创建如下文件和文件夹：

![](C:\Users\86157\Desktop\百家号图片搜集\准备工作.png)

- 文件和文件夹解析：
  - dist文件夹：用于存放之后打包的文件
  - src文件夹：用于存放我们写的源文件
    - main.js:项目的入口文件，具体内容查看下面详情
    - mathUtils.js:定义了一些数学工具函数，可以在其他地方引用，并且使用。具体内容查看下面的详情
  - index.html:浏览器打开展示的首页html
  - package.json:通过npm init生成的，npm包管理的文件
- mathUtils.js文件中的代码:

```js
function add(num1, num2) {
    return num1 + num2
}

function mul(num1, num2) {
    return num1 * num2
}

module.exports = {
	add,mul
}
```

- main.js文件中的代码：

```js
const {add,mul} = require('./mathUtils.js')
console.log(add(20,30));
console.log(mul(20,30));
```

#### webpack安装

- 安装webpack首先需要安装Node.js,Node.js自带了软件包管理工具npm
- 查看自己的node版本：

```node
node -v
```

- 全局安装webpack（这里我先指定版本号3.6.0 ，因为最新的vue cli2依赖该版本）

```
npm install webpack@12.18.1 -g
```

- 局部安装webpack
  - save -dev 是开发时依赖，项目打包后不需要继续使用的。

```
cd 对应目录
npm install webpack@3.6.0 --save-dev
```

- 为什么全局安装后，还需要局部安装呢？
  - 在终端直接执行webpack命令，使用的全局安装的webpack
  - 当在package.json中定义了script时，其中包含了webpack命令，那么使用的是局部webpack

#### js文件的打包

- 现在的js文件使用了模块化的方式进行开发，他们可以直接使用吗？不可以。

  - 因为如果直接在index.html引入这两个js文件，浏览器并不识别其中的模块化代码
  - 另外，在真实项目中当许多这样的js文件时，我们一个个引用非常麻烦，并且后期非常不方便对它们进行管理

- 我们应该怎么做呢？使用webpack工具，对多个js文件进行打包。

  - 我们知道，webpack就是一个模块化的打包工具，所以它支持我们代码中写模块化，可以对模块化的代码进行处理
  - 另外，如果在处理完所有模块之间的关系后，将多个js打包到一个js文件中，引入时就变得非常方便了

- OK，如何打包呢？使用webpack的指令即可

  ```
  webpack src/main.js -o dist/bundle.js
  ```

#### 使用打包后的文件

- 打包后会在dist文件下，生成一个bundle.js文件

  - 文件内容有些复杂，后面在分析
  - bundle.js文件，是webpack处理了项目直接文件依赖后生成的一个js文件，我们只需要将这个js文件在index.html中引入即可

  ```html
  <!DOCTYPE html>
  <html>
  	<head>
  		<meta charset="utf-8">
  		<title></title>
  	</head>
  	<body>
  	</body>
  	<script src="dist/bundle.js" type="text/javascript" charset="utf-8"></script>
  </html>
  ```

#### 入口和出口

- 我们考虑一下，如果每次使用webpack的命令都需要写上入口和出口作为参数，就非常麻烦，有没有一种方法可以将这两个参数写到配置中，在运行时，直接读取呢？
- 当然可以，就是创建一个webpack.config.js文件

```js
const path = require('path')
module.exports = {
    //入口：可以是字符串/数组/对象，这里我们入口只有一个，所以写一个字符串即可
    entry:'./src/main.js',
    //出口:通常是一个对象，里面至少包含两个垂直属性，path 和 filename
    output:{
        path:path.resolve(__dirname,'dist'),//注意：path通常是一个绝对路径
        filename:'bundle.js'
    }
}
```

#### package.json中定义启动

- 但是，每次执行都敲这么一长串有没有觉得不方便呢？
  
  - 我们可以在package.json的script中定义自己的执行脚本。
  
- package.json中的script的脚本在执行时，会按照一定的顺序寻找命令对应的位置。

  - 首先，会寻找本地的node_modules/.bin路径中对应的命令。
  - 如果没有找到，会去全局的环境变量中寻找。
  - 如何执行我们的build指令呢？

  ```
  npm  run build
  ```

  ```js
  {
      "name":"meetwebpack",
         "version":"1.0.0",
             "description":"",
                 "main":"index.js",
                     "script":{
                         "build":"webpack"
                     },
                         "author":"",
                             "license":"ISC",
                                 "devDependencies":{
                                     "webpack":"^3.6.0"
                                 }
  }
  ```

#### 什么是loader？

- loader是webpack中一个非常核心的概念。
- webpack用来做什么呢？
  - 在我们之前的实例中，我们主要是用webpack来处理我们写的js代码，并且webpack会自动处理js之间相关的依赖。
  - 但是，在开发中我们不仅仅有基本的js代码处理，我们也需要加载css、图片,也包括一些高级的将ES6转成ES5代码，将Typescript转成ES5代码，将scss、less转成less，将.jsx、.vue文件转成js文件等等。
  - 对于webpack本身的能力来说，对于这些转化是不支持的。
  - 那怎么办呢？给webpack扩展对应的loader就可以了
- loader使用过程：
  - 步骤一：通过npm安装需要使用的loader
  - 步骤二：在webpack.config.js中的module关键字下进行配置
- 大部分loader我们都可以在webpack的官网中找到，并且学习对应的用法。

#### css文件处理-准备工作

- 项目开发过程中，我们必然需要添加很多的样式，而样式我们往往写到一个单独的文件中。
  - 在src目录中，创建一个css文件，其中创建一个normal.css文件。
  - 我们也可以重新组织文件的目录结构，将零散的js文件放在一个js文件夹中。
- normal.css中的代码非常简单，就是将body设置为red
- 但是，这个时候normal.css中的样式会生效吗？
  - 当然不会，因为我们压根就没有引用它。
  - webpack也不可能找到它，因为我们只有一个入口，webpack会从入口开始查找其他依赖的文件。
- 在入口文件中引用：

```js
const math = require('./js/mathUtils')
console.log("hello");
console.log(math.add(20,30));
console.log(math.mul(40,20));

//必须在这里引用一次css文件
require('./css/normal.css')
```

### less文件处理

#### less文件处理-准备工作

- 如果我们希望在项目中使用less、scss、stylus来写样式，webpack是否可以帮助我们处理呢？
  - 我们这里以less为例，其他也是一样的。
- 我们还是先创建一个less文件，依然放在css文件夹中

```js
const math = require('./js/mathUtils')
 
console.log('HELLO');
console.log(math.add(20,59));
console.log(math.mul(20,30));

//必须在这里引用一次css文件
require('./css/normal.css')

//引入less
require('./css/special.css')

//为了查看less生效的代码，添加一个div
document.writeln("<div>Hello World</div>")

```

```html
<style>
@fontSize: 50px;
    @fontColor: red;
    body{
        color:@fontColor;
        font-size:@fontSize;
    }
</style>
```

#### less文件处理--less-loader

- 继续在官方中查找，我们会找到less-loader相关的使用说明

- 首先，还是需要安装对应的loader

  - 注意：我们这里还安装了less，因为webpack会使用less对less文件进行编译

  ```
  npm install --save-dev  less-loader less
  ```

- 其次，修改对应的配置文件

  - 添加一个rules选项，用于处理.less文件

```js
const path = require('path')
module.exports = {
	entry: './src/main.js',
	output: {
		path: path.resolve(__dirname, 'dist'),
		filename: 'bundle.js'
	},
module:{
	rules:[
		{
			test:/\.css$/,
			//css-loader只负责将css文件进行加载
			//style-loader负责将样式添加到DOM中
			//使用多个loader时，是从右向左
			use:['style-loader','css-loader']
			
		},
		{
			test:/\.less$/,
			use:[{
				loader:"style-loader"
			},
			{
				loader:"css-loader"
			},
			{
				loader:"less-loader"
			}
			]
		}
	]
}
}
```

### 图片处理

#### 图片文件处理—资源准备阶段

- 首先，我们在项目中加入两张图片：
  - 一张较小的图片test.jpg(小于61.1kb)，一张较大的图片test.jpeg(大于61.1kb)
  - 针对两张图片进行不同的处理
- 我们先考虑在css样式中引用图片的情况，所以我更改了normal.css中的样式：

```css
body{
background-color:red;
background:url(../../img/2.jpeg);
}
```

- 如果直接打包，会出现问题

#### 图片文件处理— url-loader

- 图片处理，我们使用url-loader来处理，依然先安装url-loader

```
npm install --save-dev url-loader
```

- 修改webpack.config.js配置文件：

```js
const path = require('path')
module.exports = {
	entry: './src/main.js',
	output: {
		path: path.resolve(__dirname, 'dist'),
		filename: 'bundle.js',
		publicPath:'dist/'
	},
module:{
	rules:[
		{
			test:/\.css$/,
			//css-loader只负责将css文件进行加载
			//style-loader负责将样式添加到DOM中
			//使用多个loader时，是从右向左
			use:['style-loader','css-loader']
		},
		{
			test:/\.less$/,
			use:[{
				loader:"style-loader"
			},
			{
				loader:"css-loader"
			},
			{
				loader:"less-loader"
			}
			]
		},
		{
			test:/\.(png|jpg|gif|jpeg)$/,
			use:[{
				loader:'url-loader',
				options:{
					//当加载的图片，小于limit时，会将图片编译成base64字符串形式
					//当加载的图片，大于limit时，需要使用file-loader模块进行加载
					limit:63000
				}
			}]
		}
	]
}
}
```

- 再次打包，运行index.html,就会发现我们的背景图片选出了出来。
  - 而仔细观察，你会发现背景图是通过base64显示出来的
  - OK，这也是limit属性的作用，当图片小于61.1kb时，对图片进行base64编码

#### 图片文件处理—file-loader

- 如果大于61.1kb，我们将background的图片改成timg.jpg
  - 因为大于61.1kb的图片，会通过file-loader进行处理，但是我们的项目中并没有file-loader
- 所以，我们需要安装file-loader

```
npm install --save-dev file-loader
```

- 再次打包，就会发现dist文件夹下多了一个图片文件

![](C:\Users\86157\Desktop\百家号图片搜集\dist图片.png)

#### 图片文件处理—修改文件名称

- 我们发现webpack自动帮助我们生成一个非常长的名字

  - 这是一个32位hash值，目的是防止名字重复
  - 但是，真实开发中，我们可能对打包的图片名字有一定的要求
  - 比如，将所有的图片放在一个文件夹中，跟上图片原来的名称，同时也要防止重复

  ```js
  options:{
      limit:8192,
          name:'img/[name].[hash:8].[ext]'
  }
  ```

- 所以，我们可以在options中添加上如下选项：

  - img：文件要打包到的文件夹
  - name：获取图片原来的名字，放在该位置
  - hash:8  : 为了防止图片名称冲突，依然使用hash，但是我们只保留8位
  - ext：使用图片原来的扩展名

- 但是，我们发现图片并没有显示出来，这是因为图片使用的路径不正确

  - 默认情况下，webpack会将生成的路径直接返回给使用者
  - 但是，我们整个程序是打包在dist文件夹下的，所以这里我们需要在路径下再添加一个dist/

  ```js
  //出口：通常是一个对象，里面至少包含两个重要属性，path 和filename
  output: {
      path: path.resolve(__dirname,'dist'),//注意：path通常是一绝对路径
      filename:'bundle.js',
          publicPath:'dist/'      
  },
  ```


### babel的使用

#### 	ES6语法处理

- 如果你仔细阅读webpack打包的js文件，发现写的ES6语法并没有转成ES5，那么就意味着可能一些对ES6还不支持的浏览器没有办法很好的运行我们的代码。

- 在前面我们说过，如果希望将ES6的语法转成ES5，那么就需要使用babel。

  - 而在webpack中，我们直接使用babel对应的loader就可以了。

  ```
  npm install --save-dev babel-loader@7 babel-core babel-preset-es2015
  ```

- 配置webpack.config.js文件

```js
{
    test:/\.m?js$/,
        exclude:/(node_modules|bower_components)/,
            use:{
                loader:'babel-loader',
                    options:{
                        presets:['es2015']
                    }
            }

}
```

- 重新打包，查看bundle.js文件，发现其中的内容变成了ES5的语法

```js
! function(e) {
	var t = {};

	function n(r) {
		if (t[r]) return t[r].exports;
		var o = t[r] = {
			i: r,
			l: !1,
			exports: {}
		};
		return e[r].call(o.exports, o, o.exports, n), o.l = !0, o.exports
	}
	n.m = e, n.c = t, n.d = function(e, t, r) {
		n.o(e, t) || Object.defineProperty(e, t, {
			enumerable: !0,
			get: r
		})
	}, n.r = function(e) {
		"undefined" != typeof Symbol && Symbol.toStringTag && Object.defineProperty(e, Symbol.toStringTag, {
			value: "Module"
		}), Object.defineProperty(e, "__esModule", {
			value: !0
		})
	}, n.t = function(e, t) {
		if (1 & t && (e = n(e)), 8 & t) return e;
		if (4 & t && "object" == typeof e && e && e.__esModule) return e;
		var r = Object.create(null);
		if (n.r(r), Object.defineProperty(r, "default", {
				enumerable: !0,
				value: e
			}), 2 & t && "string" != typeof e)
			for (var o in e) n.d(r, o, function(t) {
				return e[t]
			}.bind(null, o));
		return r
	}, n.n = function(e) {
		var t = e && e.__esModule ? function() {
			return e.default
		} : function() {
			return e
		};
		return n.d(t, "a", t), t
	}, n.o = function(e, t) {
		return Object.prototype.hasOwnProperty.call(e, t)
	}, n.p = "dist/", n(n.s = 4)
}([function(e, t, n) {
	"use strict";
	e.exports = function(e) {
		var t = [];
		return t.toString = function() {
			return this.map((function(t) {
				var n = function(e, t) {
					var n = e[1] || "",
						r = e[3];
					if (!r) return n;
					if (t && "function" == typeof btoa) {
						var o = (a = r, c = btoa(unescape(encodeURIComponent(JSON.stringify(a)))), u =
								"sourceMappingURL=data:application/json;charset=utf-8;base64,".concat(c), "/*# ".concat(u, " */")),
							i = r.sources.map((function(e) {
								return "/*# sourceURL=".concat(r.sourceRoot || "").concat(e, " */")
							}));
						return [n].concat(i).concat([o]).join("\n")
					}
					var a, c, u;
					return [n].join("\n")
				}(t, e);
				return t[2] ? "@media ".concat(t[2], " {").concat(n, "}") : n
			})).join("")
		}, t.i = function(e, n, r) {
			"string" == typeof e && (e = [
				[null, e, ""]
			]);
			var o = {};
			if (r)
				for (var i = 0; i < this.length; i++) {
					var a = this[i][0];
					null != a && (o[a] = !0)
				}
			for (var c = 0; c < e.length; c++) {
				var u = [].concat(e[c]);
				r && o[u[0]] || (n && (u[2] ? u[2] = "".concat(n, " and ").concat(u[2]) : u[2] = n), t.push(u))
			}
		}, t
	}
}, function(e, t, n) {
	"use strict";
	var r, o = function() {
			return void 0 === r && (r = Boolean(window && document && document.all && !window.atob)), r
		},
		i = function() {
			var e = {};
			return function(t) {
				if (void 0 === e[t]) {
					var n = document.querySelector(t);
					if (window.HTMLIFrameElement && n instanceof window.HTMLIFrameElement) try {
						n = n.contentDocument.head
					} catch (e) {
						n = null
					}
					e[t] = n
				}
				return e[t]
			}
		}(),
		a = [];

	function c(e) {
		for (var t = -1, n = 0; n < a.length; n++)
			if (a[n].identifier === e) {
				t = n;
				break
			} return t
	}

	function u(e, t) {
		for (var n = {}, r = [], o = 0; o < e.length; o++) {
			var i = e[o],
				u = t.base ? i[0] + t.base : i[0],
				s = n[u] || 0,
				f = "".concat(u, " ").concat(s);
			n[u] = s + 1;
			var l = c(f),
				d = {
					css: i[1],
					media: i[2],
					sourceMap: i[3]
				}; - 1 !== l ? (a[l].references++, a[l].updater(d)) : a.push({
				identifier: f,
				updater: m(d, t),
				references: 1
			}), r.push(f)
		}
		return r
	}

	function s(e) {
		var t = document.createElement("style"),
			r = e.attributes || {};
		if (void 0 === r.nonce) {
			var o = n.nc;
			o && (r.nonce = o)
		}
		if (Object.keys(r).forEach((function(e) {
				t.setAttribute(e, r[e])
			})), "function" == typeof e.insert) e.insert(t);
		else {
			var a = i(e.insert || "head");
			if (!a) throw new Error(
				"Couldn't find a style target. This probably means that the value for the 'insert' parameter is invalid.");
			a.appendChild(t)
		}
		return t
	}
	var f, l = (f = [], function(e, t) {
		return f[e] = t, f.filter(Boolean).join("\n")
	});

	function d(e, t, n, r) {
		var o = n ? "" : r.media ? "@media ".concat(r.media, " {").concat(r.css, "}") : r.css;
		if (e.styleSheet) e.styleSheet.cssText = l(t, o);
		else {
			var i = document.createTextNode(o),
				a = e.childNodes;
			a[t] && e.removeChild(a[t]), a.length ? e.insertBefore(i, a[t]) : e.appendChild(i)
		}
	}

	function p(e, t, n) {
		var r = n.css,
			o = n.media,
			i = n.sourceMap;
		if (o ? e.setAttribute("media", o) : e.removeAttribute("media"), i && btoa && (r +=
				"\n/*# sourceMappingURL=data:application/json;base64,".concat(btoa(unescape(encodeURIComponent(JSON.stringify(i)))),
					" */")), e.styleSheet) e.styleSheet.cssText = r;
		else {
			for (; e.firstChild;) e.removeChild(e.firstChild);
			e.appendChild(document.createTextNode(r))
		}
	}
	var v = null,
		h = 0;

	function m(e, t) {
		var n, r, o;
		if (t.singleton) {
			var i = h++;
			n = v || (v = s(t)), r = d.bind(null, n, i, !1), o = d.bind(null, n, i, !0)
		} else n = s(t), r = p.bind(null, n, t), o = function() {
			! function(e) {
				if (null === e.parentNode) return !1;
				e.parentNode.removeChild(e)
			}(n)
		};
		return r(e),
			function(t) {
				if (t) {
					if (t.css === e.css && t.media === e.media && t.sourceMap === e.sourceMap) return;
					r(e = t)
				} else o()
			}
	}
	e.exports = function(e, t) {
		(t = t || {}).singleton || "boolean" == typeof t.singleton || (t.singleton = o());
		var n = u(e = e || [], t);
		return function(e) {
			if (e = e || [], "[object Array]" === Object.prototype.toString.call(e)) {
				for (var r = 0; r < n.length; r++) {
					var o = c(n[r]);
					a[o].references--
				}
				for (var i = u(e, t), s = 0; s < n.length; s++) {
					var f = c(n[s]);
					0 === a[f].references && (a[f].updater(), a.splice(f, 1))
				}
				n = i
			}
		}
	}
}, function(e, t, n) {
	"use strict";
	e.exports = function(e, t) {
		return t || (t = {}), "string" != typeof(e = e && e.__esModule ? e.default : e) ? e : (/^['"].*['"]$/.test(e) && (
			e = e.slice(1, -1)), t.hash && (e += t.hash), /["'() \t\n]/.test(e) || t.needQuotes ? '"'.concat(e.replace(/"/g,
			'\\"').replace(/\n/g, "\\n"), '"') : e)
	}
}, function(e, t, n) {
	"use strict";
	t.a = n.p + "img/2.3469442a.jpeg"
}, function(e, t, n) {
	n(5), n(7), document.writeln("<h2>你好</h2>")
}, function(e, t, n) {
	var r = n(1),
		o = n(6);
	"string" == typeof(o = o.__esModule ? o.default : o) && (o = [
		[e.i, o, ""]
	]);
	var i = {
		insert: "head",
		singleton: !1
	};
	r(o, i);
	e.exports = o.locals || {}
}, function(e, t, n) {
	"use strict";
	n.r(t);
	var r = n(0),
		o = n.n(r),
		i = n(2),
		a = n.n(i),
		c = n(3),
		u = o()(!1),
		s = a()(c.a);
	u.push([e.i, "body{\r\n/* \tbackground-color:red; */\r\n\t\tbackground:url(" + s + ");\r\n}", ""]), t.default = u
}, function(e, t, n) {
	var r = n(1),
		o = n(8);
	"string" == typeof(o = o.__esModule ? o.default : o) && (o = [
		[e.i, o, ""]
	]);
	var i = {
		insert: "head",
		singleton: !1
	};
	r(o, i);
	e.exports = o.locals || {}
}, function(e, t, n) {
	"use strict";
	n.r(t);
	var r = n(0),
		o = n.n(r)()(!1);
	o.push([e.i, "", ""]), t.default = o
}]);
```

### webpack配置vue

#### 引用vue.js

- 后续项目中，我们会使用Vuejs进行开发，而且会以特殊的文件夹来组件vue的组件。
  - 所以，下面我们来学习一下如何在我们的webpack环境中集成Vuejs
- 现在，我们希望在项目中使用Vuejs，那么必然需要对其依赖，所以需要先进行安装
  - 注意：因为我们后续是在实际项目中也会使用vue，所以并不是开发时依赖

```
npm install vue --save
```

- 那么，接下来就可以按照我们之前学习的方式来使用Vue了

```js
import Vue from 'vue'
new Vue({
    el:'#app',
    data:{
        name:'coderwhy'
    }
})
```

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
	</head>
	<body>
        <div id="app">
        {{message}}
        </div>
	</body>
	<script src="./dist/bundle.js"></script>
</html>

```

#### 打包项目-错误信息

- 修改完成后，重新打包，运行程序：
  - 打包过程没有任何错误
  - 但是运行程序，没有出现想要的效果，而且浏览器中有报错
- 这个错误说的是我们使用的是runtime-only版本的Vue，什么意思呢？
  - 这里我只说解决方案：Vue不同版本构建，后续我具体讲解runtime-only和runtime-compiler的区别。
- 所以我们修改webpack的配置，添加如下内容即可

```js
resolce:{
alias:{
'vue$':'vue/dist/vue.esm.js'
}
}
```

#### el和template区别(一)

- 正常运行之后，我们来考虑另外一个问题：

  - 如果我们希望将data中的数据显示在界面中，就必须是修改index.html
  - 如果我们后面自定义了组件,也必须修改index.html来使用组件
  - 但是html模板在之后的开发中，我并不希望手动的来频繁修改，是否可以做到呢？

- 定义template属性：

  - 在前面的Vue实例中，我们定义了el属性，用于和index.html中的#app进行绑定，让Vue实例之后可以管理它其中的内容
  - 这里，我们可以将div元素中的{{message}}内容删掉，只保留一个基本的id为div的元素
  - 但是如果我依然希望在其中显示{{message}}的内容，应该怎么处理呢？
  - 我们可以再定义一个template属性，代码如下：

  ```js
  new  Vue({
      el:'#app',
      template:'<div id="app">{{message}}</div>',
      data:{
          message:'coderwhy'
      }
  })
  ```


#### .vue文件封装处理

- 但是一个组件以一个js对象的形式组织和使用的时候是非常不方便的
  - 一方面编写template模块非常的麻烦
  - 另外一方面如果有样式的话，我们写在哪里比较合适呢？
- 现在，我们以一种全新的方式来组织一个vue的组件
- 但是，这个时候这个文件可以被正确的加载吗？
  - 必然不可以，这种特殊的文件以及特殊的格式，必须有人帮助我们处理。
  - 谁来处理呢？vue-loader以及vue-template-compiler。
- 安装vue-loader和vue-template-compiler

```
npm install vue-loader vue-template-compiler --save-dev
```

- 修改webpack.config.js的配置文件：

```vue
<template>
<h2 class="title">{{name}}</h2>
</template>
<script>
export default{
    name:"App",
    data(){
        return{
            name:'我是.vue的App组件'
        }
    }
}
</script>
<style>
    .title{
        color:red;
    }
</style>
```

```js
{
test:/\.vue$/,
    use:['vue-loader']
}
```

#### 认识plugin

- plugin是什么？
  - plugin是插件的意思，通常是用于对某个现有的架构进行扩展。
  - webpack中的插件，就是对webpack现有功能的各种扩展，比如打包优化，文件压缩等等。
- loader和plugin区别
  - loader主要用于转换某些类型的模块，它是一个转换器。
  - plugin是插件，它是对webpack本身的扩展，是一个扩展器。
- plugin的使用过程：
  - 步骤一：通过npm安装需要使用的plugins（某些webpack已经内置的插件不需要安装）
  - 步骤二：在webpack.config.js中的plugins中配置插件。
- 下面，我们就来看看可以通过那些插件对现在的webpack打包过程进行扩容，让我们的webpack变得更加好用。

添加版权的Plugin

- 我们先来使用一个最简单的插件，为打包的文件添加版权声明
  - ​	该插件名叫BannerPlugin，属于webpack自带的插件。
- 按照下面的方式来修改webpack.config.js文件：

```js
const path = require('path')
const webpack = require('webpack')

module.exports = {
    plugins:{
        new webpack.BannerPlugin('最终版权归aa所有')
    }
}
```

- 重新打包程序：查看bundle.js文件的头部，看到如下信息

```js
/*！最终版权归aa所有*/
/*********/ (function(modules){
    //webpackBootstrap
})
```

#### 打包html的plugin

- 目前，我们的index.html文件是存放在项目的根目录下的。
  - 我们知道，在真实发布项目时，发布的是dist文件夹中的内容，但是dist文件夹中如果没有index.html文件，那么打包的js等文件也就没有意义。
  - 所有，我们需要将index.html文件打包到dist文件夹中，这个时候就可以使用HtmlWebpackPlugin插件
- HtmlWebpackPlugin插件可以为我们做这些事情：
  - 自动生成一个index.html文件（可以指定模板来生成）
  - 将打包的js文件，自动通过script标签插入到body中
- 安装HtmlWebpackPlugin插件

```
npm install html-webpack-plugin --save-dev
```

- 使用插件，修改webpack.config.js文件中plugins部分的内容如下：

  - 这里的template表示根据什么模板来生成index.html
  - 另外，我们需要删除之前在output中添加的publicPath属性
  - 否则插入的script标签中的src可以会出问题

  ```js
  plugins:[
      new webpack.BannerPlugin('最终版权归福吉所有'),
      new HtmlWebpackPlugin({
          template:'index.html'
      }),
  ]
  ```


#### js压缩的Plugin

- 在项目发布之前，我们必然需要对js等文件进行压缩处理
- 我们使用一个第三方的插件uglifyjs-webpack-plugin，并且版本号指定1.1.1，和CLI2保持一致

```
npm install uglifyjs-webpack-plugin@1.1.1 --save-dev
```

- 修改webpack.config.js文件，使用插件：

```js
const path = require('path')
const webpack = require('webpack')
const uglifyJsPlugin = require('uglifyjs-webpack-plugin')

module.exports = {
    plugins: [
    new webpack.BannerPlugin('最终版权归福吉所有')
    new uglifyJsPlugin()
    ]
}
```

- 查看打包后的bunlde.js文件，是已经被压缩过的。

#### 搭建本地服务器

- webpack提供了一个可选的本地开发服务器，这个本地服务器基于node.js搭建，内部使用express框架，可以实现我们想要的让浏览器自动刷新显示我们修改后的结果。
- 不过它是一个单独的模块，在webpack中使用之前需要先安装它

```
npm install --save-dev webpack-dev-sever@2.9.1
```

- devserver也是作为webpack中的一个选项，选项本身可以设置如下属性：

  - contentBase: 为哪一个文件夹提供本地服务，默认是根文件夹，我们这里要填写./dist
  - port:端口号
  - inline：页面实时刷新
  - historyApiFallback：在SPA页面中，依赖HTML5的history模式

- webpack.config.js文件配置修改如下:

- 我们可以再配置另外一个scripts：

  - --open参数表示直接打开浏览器

  ```js
  devServer:{
      contentBase:'./dist',
          inline: true
  }
  ```

  ```js
  "dev":"webpack-dev-server --open"
  ```


## 什么是Vue CLI

- 如果你只是简单写几个Vue的Demo程序，那么你不需要Vue CLI
- 如果你在开发大型项目，那么你需要，并且必然需要使用Vue CLI
  - 使用Vue.js开发大型应用时，我们需要考虑代码目录结构、项目结构和部署、热加载、代码单元测试等事情。
  - 如果每个项目都要手动完成这些工作，那无疑效率比较低效，所以通常我们使用一些脚手架工具来帮助完成这些事情。
- CLI是什么意思？
  - CLI是Command-Line Interface ，翻译为命令行界面，但是俗称脚手架。
  - Vue CLI是一个官方发布 vue.js 项目脚手架
  - 使用 vue-cli 可以快速搭建Vue开发环境以及对应的webpack配置
- 脚手架长什么样子？

脚手架跟工地的工程差不多，类似于工程学。

### Vue CLI使用前提 -Node

- 安装NodeJS

  - 可以直接官方网站下载安装
  - 网址：http://nodejs.cn/download/

- 检测安装的版本

  - 默认情况下自动安装Node和NPM
  - Node环境要求8.9以上或者更高版本

  ![](C:\Users\86157\Desktop\百家号图片搜集\node版本.png)

- 什么是NPM呢？
  - NPM的全称是Node Package Manager
  - 是一个NodeJs包管理和分发工具，已经成为了非官方的发布Node模块(包)的标准。
  - 后续我们会经常使用NPM来安装一些开发过程中依赖包。

- cnpm安装

  由于国内直接使用npm的官方镜像是非常慢的，这里推荐使用淘宝NPM镜像。

  你可以使用淘宝定制的cnpm（gzip压缩支持）命令行工具代替默认的npm：

  npm install -g cnpm -registry=https://registry.npm.taobao.org

  这样就可以使用cnpm命令来安装模块了：

  cnpm install [name]

### Vue CLI使用前提 -webpack

- Vue.js官方脚手架工具就使用了webpack模板

  - 对所有的资源会压缩等优化操作
  - 它在开发过程中提供了一套完整的功能，能够使得我们开发过程中变得高效。

- Webpack的全局安装

  - npm install webpack  -g

  ![](C:\Users\86157\Desktop\百家号图片搜集\link.png)

### Vue CLI的使用

- 安装Vue脚手架

  - npm install -g @vue/cli

    ![](C:\Users\86157\Desktop\百家号图片搜集\vue脚手架.png)

- 注意：上面安装的是Vue CLI2的版本， Vue CLI3是不可以使用Vue CLI2的方式初始化项目。

  - 拉取2.x模板（旧版本）

  Vue CLI3 和旧版使用了相同的vue命令，所以Vue CLI 2（vue-cli）被覆盖了，如果你任然要使用旧版本的 vue init功能，你可以全局安装一个桥接工具：

  ```js
  npm install -g @vue/cli-init
  // vue init 的运行效果将跟 vue-cli2.x 相同
  vue init webpack my-project
  ```

- Vue CLI2初始化项目

  - vue init webpack my-project

- Vue CLI3初始化项目

  - vue create my-project

### Vue CLI2详解

### ![](C:\Users\86157\Desktop\百家号图片搜集\Vue CLI2图片.png)	vuecli-CLI2的目录结构解析

![](C:\Users\86157\Desktop\百家号图片搜集\vuecli2解析.png)

### render函数的使用

```js
new Vue({
    el:'#app',
        render:(createElement)=>{
            //1.使用方式一：
            return createElement('标签','相关数据对象(可以不传)',['内容数组'])
            //2.render函数基本使用
            return createElement('div',{class:'test'},['Hello'])
            //3.嵌套render函数
            return createElement('div',{class:'best'},['Yes',createElement('h3',['标题'])])
        }
})

const cpn = Vue。component('cpn',{
    template:'<div>我是cpn组件</div>',
    data(){
        return{
            
        }
    }
})

new Vue({
    el:'#app',
    render:(createElement)=>{
        //使用方式二：传入一个组件对象
        return createElement(cpn)
    }
})
```



### Runtime-Compiler和Runtime-only的区别

- 简单总结
  - 如果在之后的开发中，你依然使用template，就需要选择Runtime-Compiler
  - 如果在之后的开发中，使用的是.vue文件夹开发，那么可以选择Runtime-only

### render和template

- Runtime-Compiler和Runtime-only

```js
new Vue({
    el:'#app',
    components:{App},
    template:'<App/>'
})
new Vue({
    el:'#app',
    render: h =>h(App)
})
```

- 为什么存在这样的差异呢？
- 我们需要先理解Vue应用程序是如何运行起来的
- Vue中的模板如何最终渲染成真实DOM
- 我们来看下面的一幅图

### Vue程序运行过程

![](C:\Users\86157\Desktop\百家号图片搜集\render函数.png)

### npm run build

![](C:\Users\86157\Desktop\百家号图片搜集\npm run build.png)

### 修改配置：webpack.base.config.js起别名

```js
resolve:{
    extensions:['.js','.vue','.json'],
        alias:{
            '@':resolve('src'),
                'pages': resolve('src/pages'),
                'common':resolve('src/common'),
                'components':resolve('src/components'),
                'network':resolve('src/network')
        }
},
```

## 认识Vue CLI3

- vue-cli 3 与 2版本有很大区别
  - vue-cli 3 是基于webpack 4打造， vue-cli 2 还是webpack 3
  - vue-cli 3 的设计原则 是 ”0配置“ ，移除的配置文件根目录下的，build和config等目录
  - vue-cli 3 提供了 vue UI 命令 ，提供了可视化配置，更加人性化
  -  移除了static文件夹，新增了public文件夹，并且index.html移动到public中

## 认识路由

### 什么是路由？

- 说起路由你想起了什么？
  - 路由是一个网络工程里面的术语
  - 路由（routing）就是通过互联网的网络把信息从源地址传输到目的地址的活动

- 到底什么是路由器
  - 路由器是提供了两种机制：路由和传送
    - 路由是决定数据包从来源到目的地的路径
    - 传送将输出端的数据转移到合适的输出端
  - 路由中有一个非常重要的概念叫路由表
    - 路由表本质上是一个眏射表，决定了数据包的指向

### 后端路由阶段

- 早期的网站开发整个HTML页面但是由服务器来渲染的
  - 服务器直接生产渲染好对应的HTML页面，返回给客户端进行展示
- 但是，一个网站，这么多网页服务器如何处理呢？
  - 一个页面有自己对应的网址，也就是URL
  - URL会发送到服务器，服务器会通过正则对该URL进行匹配，并且最后交给一个Controller进行处理
  - Controller进行各种处理，最终生成HTML或者数据，返回给前端
  - 这就是完成了一个IO操作
- 上面的这种操作，就是后端路由
  - 当我们页面中需要请求不同的路径内容时，交给服务器来进行处理，服务器渲染好整个页面，并且将页面返回给客户端
  - 这种情况下渲染好的页面，不需要单独加载任何的js和css，可以直接交给浏览器展示，这样也有利于SEO优化
- 后端路由的缺点
  - 一种情况是整个页面的模块由后端人员来编写和维护的
  - 另一种情况是前端开发人员如果要开发页面，需要通过PHP和JAVA等语言来编写页面代码
  - 而且通常情况下HTML代码和数据以及对应的逻辑会混在一起，编写和维护都是非常糟糕的事情

#### 后端渲染

![](C:\Users\86157\Desktop\百家号图片搜集\后端渲染.png)

#### 前端渲染

![](C:\Users\86157\Desktop\百家号图片搜集\前端渲染.png)

- 前后端分离阶段：
  - 随着Ajax的出现，有了前后端分离的开发模式
  - 后端只提供API来返回数据，前端通过Ajax获取数据，并且通过JavaScript将数据渲染到页面中
  - 这样做最大的优点就是前后端责任清晰，后端专注于数据上，前端专注于交互和可视化上
  - 并且当移动端（IOS、Android）出现后，后端不需要进行任何处理，依然使用之前的一套API即可
  - 目前很多的网站依然采用这种模式开发
- 单页面富应用阶段
  - 其实SPA最主要的特点就是在前后端分离的基础上加了一层前端路由
  - 也就是前端来维护一套路由规则
- 前端路由的核心是什么呢？
  - 改变URL，但是页面不进行整体的刷新
  - 如何实现？

#### URL的hash

- URL的hash
  - URL的hash也就是锚点（#），本质上是改变window.location的href属性
  - 我们可以通过直接赋值location.hash来改变href，但是页面不发生刷新

![](C:\Users\86157\Desktop\百家号图片搜集\url的hash.png)

#### HTML5的history模式：pushState

![](C:\Users\86157\Desktop\百家号图片搜集\出入栈结构.png)

![](C:\Users\86157\Desktop\百家号图片搜集\replace.png)

![](C:\Users\86157\Desktop\百家号图片搜集\go.png)

#### 认识vue-router

- 目前前端流行的三大框架，都有自己的路由实现
  - Angular的ngRouter
  - React的ReactRouter
  - Vue的vue-router
- 重点是vue-router
  - vue-router是Vue.js官方的路由插件，他和vuejs是深度集成的，适合用于构建单页面应用
  - 我们可以去官网进行学习：https://router.vuejs.org/zh/
- vue-router是基于路由和组件的
  - 路由用于设定访问路径，将路径和组件眏射起来
  - 在vue-router的单页面应用中，页面的路径的改变就是组件的切换

#### 安装和使用vue-router

- 我已经学习了webpack，后续的开发中我们主要是通过工程化的方式开发的

  - 直接使用npm来安装路由即可
  - 安装vue-router

  ```
  npm install vue-router --save
  ```

  - 在模块化工程中使用它（因为是一个插件，使用可以通过Vue.use()来安装路由功能）
    
    - 导入路由对象，并且调用Vue.use(VueRouter)
    
    - 创建路由实例，并且传入路由眏射配置
    
    - 在vue实例中挂载创建的路由实例
  
- 使用vue-router的步骤：

  - 第一步：创建路由组件
  - 第二步：配置路由映射：组件和路径映射关系
  - 第三步：使用路由：通过&lt;router-link&gt;和&lt;router-view&gt;

```js
import Vue from 'vue'
import VueRouter from 'vue-router'
Vue.use(VueRouter)
```

#### 创建router实例

![](C:\Users\86157\Desktop\百家号图片搜集\router实例.png)

#### 挂载到Vue实例中

![](C:\Users\86157\Desktop\百家号图片搜集\挂载Vue.png)

#### 步骤一：创建路由组件

![](C:\Users\86157\Desktop\百家号图片搜集\创建组件.png)

#### 步骤二：配置组件和路径的映射关系

![](C:\Users\86157\Desktop\百家号图片搜集\配置映射关系.png)

#### 步骤三：使用路由

![](C:\Users\86157\Desktop\百家号图片搜集\使用路由.png)

- &lt;router-link&gt;:该标签是一个vue-router中已经内置的组件，它会被渲染成一个&lt;a&gt;标签
- &lt;router-view&gt;:该标签会根据当前的路径，动态渲染出不同的组件
- 网页的其他内容，比如顶部的标题/导航或者底部的一些标签信息等会和&lt;router-view&gt;处于同一个等级
- 在路由切换时，切换的是&lt;router-view&gt;挂载的组件，其他内容不会发生改变

#### 路由的默认路径

- 我们这里还有一个吧太好的实现：

  - 默认情况下，进入网站的首页，我们希望&lt;router-view&gt;渲染首页的内容
  - 但是我们的实现中，默认没有显示首页组件，必须让用户点击才可以

- 如何可以让路径默认跳到首页，并且&lt;router-view&gt;渲染首页组件呢？

  - 非常简单，我们只需要在配置中多配置一个映射就可以了

    ```js
    const routes = [
        {
            path:'/',
            redirect:'/home'
        }
    ]
    ```

- 配置分析：

  - 我们在routes中又配置了一个映射
  - path配置的是根路径：/
  - redirect是重定向，也就是我们将根据路径重定向到/home的路径下，这样就可以得到我们想要的结果了

#### HTML5的History模式

- 我们前面说过改变路径的方式有两种：
  - URL的hash
  - HTML5的history
  - 默认情况下，路径的改变使用的URL的hash
- 如果希望使用HTML5的history模式，进行如下配置即可

```js

export default new Router({
  routes: [
    {
      path:'/',
      //redirect重定向
      redirect:'/home'
    },
  {
    path:'/home',
    component:Home
  },
  {
    path:'/about',
    component:About
  },
  ],
    mode:'history',
})

```

#### router-link的补充

- 在前面的&lt;router-link&gt;中，我们只是使用了一个属性：to,用于指定跳转的路径
- &lt;router-link&gt;还有一些其他属性
  - tag：tag可以指定&lt;router-link&gt;之后渲染成什么组件，比如上面的代码会被渲染成一个&lt;li&gt;元素，而你是&lt;a&gt;
  - replace:replace不会留下history记录，所以指定replace的情况下，后退键返回不能返回到上一个页面中
  - active-class:当&lt;router-link&gt;对应的路由匹配成功时，会自动给当前元素设置一个router-link-active的class，设置active-class可以修改默认的名称
    - 在进行行高亮显示的导航菜单或者底部tabbar时，会使用到该类
    - 但是通常不会修改类的属性，会直接使用默认的router-link-active即可

#### 修改linkActiveClass

- 该class具体的名称也可以通过router实例的属性进行修改

![](C:\Users\86157\Desktop\百家号图片搜集\linkActiveClass.png)

- exact-active-class
  - 类似于active-class，只是在精准匹配下才会出现的class
  - 后面看到嵌套路由时，我们再看下这个属性

#### 路由代码跳转

- 有时候，页面的跳转可能需要执行对应的JavaScript代码，这个时候，就可以使用第二种跳转方式
- 比如，我们将代码修改如下：

![](C:\Users\86157\Desktop\百家号图片搜集\代码跳转.png)

#### 动态路由

- 在某些情况下，一个页面的path路径可能是不确定的，比如我们进入用户界面时，希望是如下的路径：
  - /user/c/path
  - 除了有前面的/user之外，后面还跟上了用户的ID
  - 这种path和Component的匹配关系，我们称之为动态路由（也是路由传递数据的一种方式）

#### 认识路由的懒加载

- 官方给了解释：
  - 当打包构建应用时，JavaScript包会变得非常之大，影响页面加载
  - 如果我们能把不同路由对应的组件割成不同的代码块，然后当路由被访问的时候才加载对应组件，这样就更加高效了

![](C:\Users\86157\Desktop\百家号图片搜集\懒加载.png)

- 官方在说什么呢？
  - 首先，我们知道路由中通常会定义很多不同的页面
  - 这个页面最后被打包在哪里呢？一般情况下，是放在一个js文件中
  - 但是，页面这么多放在一个js文件中，必然会造成这个页面非常的大
  - 如果我们一次性从服务器请求下来这个页面，可能需要花费一定的时间，甚至用户的电脑上还出现了短暂空白的情况
  - 如何避免这种情况呢？使用路由懒加载就可以了
- 路由懒加载做了什么呢？
  - 路由懒加载的主要作用就是将路由对应的组件打包成一个个的js代码块
  - 只有在这个路由被访问到的时候，才加载对应的组件

#### 懒加载的方式

- 方式一：结合Vue的异步组件和Webpack的代码分析

```js
const Home = resolve => {
    require.ensure(['../components/Home.vue'],() =>{
        resolve(require('../components/Home.vue'))
    })
};
```

- 方式二：AMD写法

```js
const About = resolve =>require(['../components/About.vue'],resolve);
```

- 方式三：在ES6中，我们可以有更加简单的写法来组织Vue异步组件和Webpack的代码分割

```js
const Home = () => import('../components/Home.vue')
```

#### 路由懒加载的效果

![](C:\Users\86157\Desktop\百家号图片搜集\懒加载效果.png)

#### 认识嵌套路由

- 嵌套路由是一个很常见的功能
  - 比如在home页面中，我们希望通过/home/news和/home/message访问一些内容
  - 一个路径映射一个组件，访问这两个路径也会分别渲染两个组件
- 路径和组件的关系如下：

![](C:\Users\86157\Desktop\百家号图片搜集\路径与组件的关系.png)

- 实现嵌套路由有两个步骤：
  - 创建对应的子组件，并且在路由映射中配置对应的子路由
  - 在组件内部使用&lt;router-view&gt;标签

#### 嵌套默认路径

- 嵌套路由也可以配置默认的路径，配置方式如下:

![](C:\Users\86157\Desktop\百家号图片搜集\嵌套默认路径.png)

### 传递参数

#### 准备工作

- 为了演示传递参数，我们这里再创建一个组件，并且将其配置好
  - 第一步：创建新的组件Profile.vue
  - 第二步：配置路由映射
  - 第三步：添加跳转的&lt;router-link&gt;

![](C:\Users\86157\Desktop\百家号图片搜集\准备1.png)

![](C:\Users\86157\Desktop\百家号图片搜集\准备2.png)

![](C:\Users\86157\Desktop\百家号图片搜集\准备3.png)

#### 传递参数的方式

- 传递参数主要有两种类型：params和query
- params的类型：
  - 配置路由格式:/router/:id
  - 传递的方式：在path后面跟上对应的值
  - 传递后形成的路径：/router/123/router/abc

- query的类型：
  - 配置路由格式:/router,也就是普通配置
  - 传递的方式：对象中使用query的key作为传递方式
  - 传递后形成的路径：/router?id=123,/router?id=abc

- 如何使用他们呢？有两种方式：&lt;router-link&gt;的方式和JavaScript代码方式

##### 传递参数方式一：&lt;router-link&gt;

![](C:\Users\86157\Desktop\百家号图片搜集\传递方式一.png)

##### 传递参数方式二：JavaScript代码

![](C:\Users\86157\Desktop\百家号图片搜集\传递方式二.png)

#### 获取参数

- 获取参数通过$router对象获取的
  - 在使用vue-router的应用中，路由对象会注入每个组件中，赋值为this.$route,并且当路由切换时，路由对象会被更新
- 通过$route获取传递的信息如下：

![](C:\Users\86157\Desktop\百家号图片搜集\获取参数.png)

#### $route和$router是有区别的

- $route和$router是有区别的
  - $router为VueRouter实例，想要导航到不同URL，则使用$router.push方法
  - $route为当前router跳转对象里面可以获取name、path、query、params等

![](C:\Users\86157\Desktop\百家号图片搜集\route和router区别.png)

#### 为什么使用导航守卫？

- 我们来考虑一个需求：在一个SPA应用中，如何改变网页的标题呢？
  - 网页标题是通过&lt;title&gt;来显示的，但是SPA只有一个固定的HTML，切换不同的页面时，标题并不会改变
  - 但是我们可以通过JavaScript来修改&lt;title&gt;的内容，window.document.title = '新的标题'
  - 那么在Vue项目中，在哪里修改？什么时候修改比较合适呢？

- 普通的修改方式：
  - 我们比较容易想到的修改标题的位置是每一个路由对应的组件.vue文件中
  - 通过mounted声明周期函数，执行对应的代码进行修改即可
  - 但是当页面比较多时，这种方式不容易维护（因为需要在多个页面执行类似的代码）

- 有没有更好的办法呢？使用导航守卫即可

- 什么是导航守卫？
  - vue-loader提供的导航守卫主要用来监听路由的进入和离开的
  - vue-router提供了beforeEach和afterEach的钩子函数，他们会在路由即将改变前和改变后触发

#### 导航守卫使用

- 我们可以利用beforeEach来完成标题的修改

  - 首先，我们在钩子当中定义一些标题，可以利用meta来定义

  - 其次，利用导航守卫，修改我们的标题

  - 导航钩子的三个参数解析：

    - to：即将要进入的目标的路由对象
    - from：当前导航即将要离开的路由对象
    - next：调用该方法后，才能进入下一个构子

    ![](C:\Users\86157\Desktop\百家号图片搜集\导航守卫1.png)

![](C:\Users\86157\Desktop\百家号图片搜集\导航守卫2.png)

#### 导航守卫补充

- 补充一：如果是后置钩子，也就是afterEach，不需要主动调用next()函数
- 补充二：上面我们使用的导航守卫，被称之为全局守卫
  - 路由独享的守卫
  - 组件内的守卫
- 百度学习vue-router的守卫

### keep-alive遇见vue-loader

- keep-alive是Vue内置的一个组件，可以使被包含的组件保留状态，或避免重新渲染
  - 他们有两个非常重要的属性
  - include - 字符串或正则表达 ，只要匹配的组件会被缓存
  - exclude -字符串或正则表达式，任何匹配的组件都不会被缓存
  
- router-view也是一个组件，如果直接被包在keep-alive里面，所有路径匹配到的视图组件都会被缓存

  ```html
  <keep-alive>
      <router-view>
          <!--所有路径匹配到的视图组件都会被缓存-->
          <router-view>
      </keep-alive>
  ```

- 通过create声明周期函数来验证

### TabBar实现思路

- 1.如果在下方有一个单独的TabBar组件，你如何封装
  - 自定义TabBar组件，在APP中使用
  - 让TabBar出于底部，并且设置相关的样式
- 2.TabBar中显示的内容由外界决定
  - 定义插槽
  - flex布局平分TabBar
- 3.自定义TabBarItem，可以传入图片和文字
  - 定义TabBarItem，并且定义两个插槽：图片、文字
  - 给两个插槽外层包装div，用于设置样式
  - 填充插槽，实现底部TabBar的效果