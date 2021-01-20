### 基本Javascript实例

- 用Javascript输出文本

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>用Javascript输出文本</title>
  </head>
      <body>
          <h1>这是一个web页面</h1>
          <p>这是我的第一个段落</p>
          <script type="text/javascript">
          document.write(Date());//当前时间的输出
          </script>
      </body>
  </html>
  ```

- 用Javascript改变HTML元素

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>用Javascript改变HTML元素</title>
  </head>
      <body>
          <h1>这是一个web页面</h1>
          <p id="demo">这是我的第一个段落</p>
          <script type="text/javascript">
          //通过绑定id的方式来改变p标签的内容
          document.getElementById("demo").innerHTML="段落已经修改。";
          </script>
      </body>
  </html>
  ```

- 一个外部Javascript

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>用Javascript改变HTML元素</title>
  </head>
      <body>
          <h1>这是一个web页面</h1>
          <p id="demo">这是我的第一个段落</p>
          <!--通过onclick事件调用myFunction函数，点击按钮就会触发事件，执行相应的函数-->
          <button type="button" onclick="myFunction()">按钮</button>
          <p><b>注释:</b>myFunction 保存在名为"index.js"的外部文件中。</p>
          <script type="text/javascript" src="index.js"></script>
          <!--引用外部的index.js内容为：-->
          <script type="text/javascript">//在js书写中可以省略script标签
          function myFunction(){
              document.getElementById('demo').innerHTML="我的第一个Javascript函数";
          }
          </script>
     </body>
  </html>
  ```

- 实例解析

  #### Javascript用法

  HTML中的脚本必须位于&lt;script&gt;与&lt;/script&gt;标签之间。

  脚本可被放置在HTML页面的&lt;body&gt;和&lt;/body&gt;部分中。

  #### &lt;script&gt;标签

  如需在HTML页面中插入Javascript，请使用&lt;script&gt;标签。

  &lt;script&gt;和&lt;/script&gt;会告诉Javascript在何处开始和结束。

&lt;script&gt;和&lt;/script&gt;之间的代码行包含了Javascript：

  ```html
<script type="text/javascript">
    //window对象的弹窗
  alert("我的第一个Javascript");
  </script>
  ```

  你无需理解上面的代码。只需明白，浏览器会解释并执行位于&lt;script&gt;&lt;/script&gt;之间的Javascript代码

  ```
那些老旧的实例可能会在<script>标签中使用type="text/javascript"。现在已经不必这样做了。
  javaScript是所有现代浏览器以及HTML5中的默认脚本语言。
  ```

  #### &lt;body&gt;中的Javascript

  在本例中，Javascript会在页面加载时向HTML的&lt;body&gt;写文本：

  ```html
<!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>用Javascript输出文本</title>
  </head>
      <body>
          <p>
          javascript能够直接写入HTML输出流中：
          </p>
          <script type="text/javascript">
          document.write("<h1>这是一个标题</h1>");
          document.write("<p>这是一个段落</p>");    
          </script>
          <p>你只能在HTML输出流中使用<strong>document.write。</strong>如果你咋文档已加载后使用它（比如在函数中），会覆盖整个文档。</p>
      </body>
  </html>
  ```

  #### Javascript函数和事件

  上面的例子中的Javascript语句，会在页面加载时执行。

  通常，我需要在某个事件发生是执行代码，比如当用户点击按钮时。

  如果我们把Javascript代码放入函数中，就可以在事件发生时调用该函数。

  #### 在&lt;head&gt;或者&lt;body&gt;的Javascript

  你可以在HTML文档中放入不限数量的脚本。

  脚本可位于HTML的&lt;body&gt;或&lt;head&gt;部分中，或者同时存在于两部中。

  通常的做法是把函数放入&lt;head&gt;部分中，或者放在页面底部。这样就可以把他们安置到同一处位置，不会干扰页面的内容。

  #### &lt;head&gt;中的Javascript函数

  在本例中，我们把一个Javascript函数放置到HTML页面的&lt;head&gt;部分。

  该函数会在点击按钮时被调用：

  ```html
<!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>该函数会在点击按钮时被调用</title>
       <script type="text/javascript">
          function myFunction(){
              document.getElementById('demo').innerHTML="我的第一个Javascript函数";
          }
       </script>
  </head>
      <body>
          <h1>这是一个web页面</h1>
          <p id="demo">这是我的第一个段落</p>
          <button type="button" onclick="myFunction()">按钮</button>
     </body>
  </html>
  ```

  #### &lt;body&gt;中的Javascript函数

  在本例中，我们把一个Javascript函数放置到HTML页面的&lt;body&gt;部分。

  该函数会在点击按钮时被调用：

  ```html
<!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>该函数会在点击按钮时被调用</title>
  </head>
      <body>
          <h1>这是一个web页面</h1>
          <p id="demo">这是我的第一个段落</p>
          <button type="button" onclick="myFunction()">按钮</button>
          <script type="text/javascript">
          function myFunction(){
              document.getElementById('demo').innerHTML="我的第一个Javascript函数";
          }
         </script>
     </body>
  </html>
  ```

  #### 外部的Javascript

  也可以把脚本保存到外部文件中。外部文件通常包含被多个网页使用的代码。

  外部Javascript文件的文件扩展名是.js。

  如需使用外部文件，请在&lt;script&gt;标签的"src"属性中设置该.js文件：

  ```html
<!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>用Javascript改变HTML元素</title>
  </head>
      <body>
          <h1>这是一个web页面</h1>
          <p id="demo">这是我的第一个段落</p>
          <button type="button" onclick="myFunction()">按钮</button>
          <p><b>注释:</b>myFunction 保存在名为"index.js"的外部文件中。</p>
          <script type="text/javascript" src="index.js"></script>
     </body>
  </html>
  ```

  你可以将脚本放置于&lt;head&gt;或者&lt;body&gt;中，放在<script>标签中的脚本与外部引用的脚本运行效果完全一致。

  index.js文件代码如下：

  ```js
		function myFunction(){
              document.getElementById('demo').innerHTML="我的第一个Javascript函数";
          }
  ```

  注意：外部脚本不能包含&lt;script&gt;标签。

  ### JavaScript语句、注释和代码块

- JavaScript语句

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>JavaScript语句</title>
  </head>
      <body>
          <h1>这是一个web页面</h1>
          <p id="demo">这是我的第一个段落</p>
          <div id="myDiv">一个div</div>
          <script type="text/javascript">
          //书写两个document,绑定id，div和p标签的内容将会直接改变
          document.getElementById("demo").innerHTML="你好 Bob";
          document.getElementById("div").innerHTML="你最近怎么样？";    
          </script>
    	</body>
  </html>
  ```

- JavaScript代码块

  ```html
  <!DOCTYPE html>
  <html>
  <head> 
  <meta charset="utf-8"> 
  <title>JavaScript代码块</title> 
  </head>
  <body>
  <h1>我的 Web 页面</h1>
  <p id="myPar">我是一个段落。</p>
  <div id="myDiv">我是一个div。</div>
  <p>
   <!--点击按钮就会触发onclick事件，然后绑定id的内容就会被替换-->  
  <button type="button" onclick="myFunction()">按钮</button>
  </p>
  <script>
  function myFunction(){
  	document.getElementById("myPar").innerHTML="你好世界！";
  	document.getElementById("myDiv").innerHTML="你最近怎么样?";
  }
  </script>
  <p>当您点击上面的按钮时，两个元素会改变。</p>
  
  </body>
  </html>
  ```

- JavaScript单行注释

  ```html
  <!DOCTYPE html>
  <html>
  <head> 
  <meta charset="utf-8"> 
  <title>JavaScript单行注释</title> 
  </head>
  <body>
  <h1 id="myH1"></h1>
  <p id="myP"></p>
  <script>
  // 输出标题：
  document.getElementById("myH1").innerHTML="Welcome to my Homepage";
  // 输出段落：
  document.getElementById("myP").innerHTML="This is my first paragraph.";
  </script>
  <p><b>注释：</b>注释不会被执行。</p>
  
  </body>
  </html>
  ```

- JavaScript多行注释

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <title>JavaScript多行注释</title>
  <meta charset="utf-8">
  </head>
  <body>
  <h1 id="myH1"></h1>
  <p id="myP"></p>
  <script>
  /*
  下面的这些代码会输出
  一个标题和一个段落
  并将代表主页的开始
  */
  document.getElementById("myH1").innerHTML="欢迎来到这里;
  document.getElementById("myP").innerHTML="这是一个段落。";
  </script>
  <p><b>注释：</b>注释块不会被执行。</p>
  </body>
  </html>
  ```

- 使用单行注释来防止执行

  ```html
  <!DOCTYPE html>
  <html>
  <head> 
  <meta charset="utf-8"> 
  <title>使用单行注释来防止执行</title> 
  </head>
  <body>
  <h1 id="myH1"></h1>
  <p id="myP"></p>
  <script>
  //document.getElementById("myH1").innerHTML="欢迎来到我的主页";
  document.getElementById("myP").innerHTML="这是我的第一个段落。";
  </script>
  <p><strong>注意:</strong> 注释块不会被执行</p>
  </body>
  </html>
  ```

- 使用多行注释来防止执行

```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>使用多行注释来防止执行</title> 
</head>
<body>
<h1 id="myH1"></h1>
<p id="myP"></p>
<script>
/*
document.getElementById("myH1").innerHTML="欢迎来到我的主页";
document.getElementById("myP").innerHTML="这是我的第一个段落。";
*/
</script>
<p><strong>注意:</strong>注释块不会被执行。</p>
</body>
</html>
```

### JavaScript语句

JavaScript 语句向浏览器发出的命令。语句的作用是告诉浏览器该做什么。

#### JavaScript语句

JavaScript 语句是发给浏览器的命令。

这些命令的作用是告诉浏览器要做的事情。

下面的 JavaScript 语句向 id="demo" 的 HTML 元素输出文本 "你好 Bob" ：

```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>Javascript语句</title> 
</head>
<body>
<h1>我的网页</h1>
<p id="demo">我的第一个段落。</p>
<script>
document.getElementById("demo").innerHTML = "你好 Bob";
</script>
</body>
</html>
```

### 分号

分号用于分隔 JavaScript 语句。

通常我们在每条可执行的语句结尾添加分号。

使用分号的另一用处是在一行中编写多条语句。

```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>分号</title> 
</head>
<body>
<h1>我的网页</h1>
<p id="demo1"></p>
<p id="demo2"></p>
<script>
a = 2;
b = 4;
c = a + b;
document.getElementById("demo1").innerHTML = c;
x = 4; y = 5; z = x + y;
document.getElementById("demo2").innerHTML = z;
</script>
</body>
</html>
```

注意：您也可能看到不带有分号的案例。  在 JavaScript 中，用分号来结束语句是可选的。

### JavaScript代码

JavaScript 代码是 JavaScript 语句的序列。

浏览器按照编写顺序依次执行每条语句。

本例向网页输出一个标题和两个段落：

```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>网页输出一个标题和两个段落</title> 
</head>
<body>
<h1>我的 Web 页面</h1>
<p id="demo">一个段落。</p>
<div id="myDIV">一个 DIV。</div>
<script>
document.getElementById("demo").innerHTML="你好 Tom";
document.getElementById("myDIV").innerHTML="你最近怎么样?";
</script>
</body>
</html>
```

#### JavaScript代码块

JavaScript 可以分批地组合起来。

代码块以左花括号开始，以右花括号结束。

代码块的作用是一并地执行语句序列。

本例向网页输出一个标题和两个段落：

```html
!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>网页输出一个标题和两个段落</title> 
</head>
<body>
<h1>我的 Web 页面</h1>
<p id="myPar">我是一个段落。</p>
<div id="myDiv">我是一个div。</div>
<p>
<button type="button" onclick="myFunction()">按钮</button>
</p>
<script>
function myFunction(){
	document.getElementById("myPar").innerHTML="你好大自然！";
	document.getElementById("myDiv").innerHTML="你最近怎么样?";
}
</script>
<p>当您点击上面的按钮时，两个元素会改变。</p>
</body>
</html>
```

#### JavaScript语句标识符

JavaScript 语句通常以一个 **语句标识符** 为开始，并执行该语句。

语句标识符是保留关键字不能作为变量名使用。

下表列出了 JavaScript 语句标识符 (关键字) ：

|    语句    |                             描述                             |
| :--------: | :----------------------------------------------------------: |
|   break    |                        用于跳出循环。                        |
|   catch    |        语句块，在try语句块执行出错时执行catch语句块。        |
|  continue  |                    跳过循环中的一个迭代。                    |
| do...while |     执行一个语句块，在条件语句为true时继续执行该语句块。     |
|    for     |     执行一个语句块，在条件语句为true时继续执行该语句块。     |
|  for...in  | 用于遍历数组或者对象的属性（对数组或者对象的属性进行循环操作）。 |
|  function  |                         定义一个函数                         |
| if....else |              用于基于不同的条件来执行不同的动作              |
|   return   |                           退出函数                           |
|   switch   |             用于基于不同的条件来执行不同的动作。             |
|   throw    |                      抛出（生成）错误。                      |
|    try     |               现实错误处理，与catch一同使用。                |
|    var     |                         声明一个变量                         |
|   while    |               当条件语句为true时，执行语句块。               |

#### 空格

JavaScript 会忽略多余的空格。您可以向脚本添加空格，来提高其可读性。下面的两行代码是等效的：

```js
var person="Hege";
var person = "Hege";
```

#### 对代码行进行折行

您可以在文本字符串中使用反斜杠对代码行进行换行。下面的例子会正确地显示：

```js
document.write("你好 \
世界!");
```

不过，您不能像这样折行，上面的折行才是正确的做法，下面是错误的做法：

```js
document.write \ 
("你好世界!");
```

你知道脚本语言和传统编程语言的区别吗？

提示：JavaScript 是脚本语言。浏览器会在读取代码时，逐行地执行脚本代码。而对于传统编程来说，会在执行前对所有代码进行编译。

### JavaScript变量

- 声明一个变量，为他赋值，然后显示出来

  ```html
  <!DOCTYPE html>
  <html>
  <head> 
  <meta charset="utf-8"> 
  <title>声明一个变量，为他赋值，然后显示出来</title> 
  </head>
  <body>
  <script>
  var firstnames;
  firstnames="Hege";
  document.write(firstnames);
  document.write("<br>");
  firstnames="Tove";
  document.write(firstnames);
  </script>
  <p>上面的脚本定义了一个变量，给变量分配一个值并显示，再次修改变量的值后，再次显示。
  </p>
  </body>
  </html>
  ```

- 实例解析

  #### JavaScript变量

  变量是用于存储信息的“容器”。

  ```html
  <!DOCTYPE html>
  <html>
  <head> 
  <meta charset="utf-8"> 
  <title>容器</title> 
  </head>
  <body>
  <script>
  var x=2;
  var y=3;
  var z=x+y;
  document.write(x + "<br>");
  document.write(y + "<br>");
  document.write(z + "<br>");
  </script>
  </body>
  </html>
  ```

  #### 就像代数那样

  x=2
  y=3
  z=x+y

  在代数中，我们使用字母（比如 x）来保存值（比如 2）。

  通过上面的表达式 z=x+y，我们能够计算出 z 的值为 5。

  在 JavaScript 中，这些字母被称为变量。

  注意：您可以把变量看做存储数据的容器。

#### JavaScript变量

与代数一样，JavaScript 变量可用于存放值（比如 x=2）和表达式（比如 z=x+y）。

变量可以使用短名称（比如 x 和 y），也可以使用描述性更好的名称（比如 age, sum, name）。

- 变量必须以字母开头
- 变量也能以 $ 和 _ 符号开头（不过我们不推荐这么做）
- 变量名称对大小写敏感（a和 A 是不同的变量）

注意：JavaScript 语句和 JavaScript 变量都对大小写敏感。

#### JavaScript数据类型

JavaScript 变量还能保存其他数据类型，比如文本值 (name="Bob Toms")。

在 JavaScript 中，类似 "Bob Toms" 这样一条文本被称为字符串。

JavaScript 变量有很多种类型，但是现在，我们只关注数字和字符串。

当您向变量分配文本值时，应该用双引号或单引号包围这个值。

当您向变量赋的值是数值时，不要使用引号。如果您用引号包围数值，该值会被作为文本来处理。

```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>Javascript数据类型</title> 
</head>
<body>
<script>
var pi=3.1415926;
var name="Bob Toms";
var answer='Goodbye!';
document.write(pi + "<br>");
document.write(name + "<br>");
document.write(answer + "<br>");
</script>
</body>
</html>
```

#### 声明（创建）JavaScript变量

在 JavaScript 中创建变量通常称为"声明"变量。

我们使用 var 关键词来声明变量：

```js
var colorname;
```

变量声明之后，该变量是空的（它没有值）。

如需向变量赋值，请使用等号：

```js
colorname="blue";
```

不过，您也可以在声明变量时对其赋值：

```js
var	colorname="blue";
```

在下面的例子中，我们创建了名为 colorname 的变量，并向其赋值 "blue"，然后把它放入 id="demo" 的 HTML 段落中：

```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>声明JavaScript变量</title> 
</head>
<body>
<p>点击这里来创建变量，并显示结果。</p>
<button onclick="myFunction()">按钮</button>
<p id="demo"></p>
<script>
function myFunction(){
    var colorname="blue";
    document.getElementById("demo").innerHTML=colorname;
}
</script>
</body>
</html>
```

注意：一个好的编程习惯是，在代码开始处，统一对需要的变量进行声明。

#### 一条语句，多个变量

您可以在一条语句中声明很多变量。该语句以 var 开头，并使用逗号分隔变量即可：

```js
var lastname="Bob", age=10, job="it",love="play caixukun";
```

声明也可横跨多行：

```js
var lastname="Bob", 
    age=10, 
    job="it",
    love="play caixukun";
```

一条语句中声明的多个不可以赋同一个值:

```js
var a,b,c=5;
```

a,b 为 undefined， c 为 5。

#### Value = undefined

在计算机程序中，经常会声明无值的变量。未使用值来声明的变量，其值实际上是 undefined。

在执行过以下语句后，变量 colorname 的值将是 undefined：

```js
var colorname;
```

#### 重新声明 JavaScript 变量

如果重新声明 JavaScript 变量，该变量的值不会丢失：

在以下两条语句执行后，变量 colorname 的值依然是 "blue"：

```js
var colorname="blue"; 
var colorname;
```

#### JavaScript 算数

您可以通过 JavaScript 变量来做算数，使用的是 = 和 + 这类运算符：

```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>加法运算</title> 
</head>
<body>
<p>假设 b=12，计算 a=b+22，并显示结果。</p>
<button onclick="myFunction()">按钮</button>
<p id="demo"></p><!--显示a=34-->
<script>
function myFunction(){
    var b=12;
    var a=b+22;//34
    var demoG=document.getElementById("demo");
    demoG.innerHTML="a=" + a;//a=34
}
</script>
</body>
</html>
```

### JavaScript条件语句if...else

- if语句

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>if语句</title>
</head>
<body>
<p>如果时间早于 12:00，会获得问候 "Good morning"。</p>
<button onclick="myFunction()">按钮</button>
<p id="demo"></p>
<script>
function myFunction(){
	var a="";
	var time=new Date().getHours();//getHours():返回Date对象的小时(0~23).
	if (time<=12){
		a="Good morning";
    }
	document.getElementById("demo").innerHTML=a;
}
</script>
</body>
</html>
```

- if...else语句

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>if...else语句</title>
</head>
<body>
<p>点击这个按钮，获得基于时间的问候。</p>
<button onclick="myFunction()">按钮</button>
<p id="demo"></p>
<script>
function myFunction(){
    var a="";
    var time=new Date().getHours();//getHours():返回Date对象的小时(0~23).
    if (time<=12){
        a="Good morning";
     }
    else{
        a="Good afternoon";
    }
    document.getElementById("demo").innerHTML=a;
}
</script>
</body>
</html>
```

- 随机链接

```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>随机链接</title> 
</head>
<body>
<p id="demo"></p>
<script>
var r=Math.random();//返回0~1之间的随机数
var x=document.getElementById("demo");
if (r>0.5){
    x.innerHTML="<a href='http://www.baidu.com'>百度</a>";
}
else{
    x.innerHTML="<a href='http://www.qq.com'>QQ</a>";
}
</script>
</body>
</html>
```

- Switch语句

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Switch语句</title>
</head>
<body>
<p>点击下面的按钮来显示今天是周几：</p>
<button onclick="myFunction()">按钮</button>
<p id="demo"></p>
<script>
function myFunction(){
	var a;
	var b=new Date().getDay();//Date对象用于处理日期与时间	
    //创建Date对象：new Date()  getDay():从Date对象返回一周中的某一天(0~6).
	switch (b){
  		case 0:a="今天是星期日";
    	break;
 		case 1:a="今天是星期一";
        break;
  		case 2:a="今天是星期二";
        break;
        case 3:a="今天是星期三";
   	 	break;
  		case 4:a="今天是星期四";
    	break;
  		case 5:a="今天是星期五";
        break;
  		case 6:a="今天是星期六";
    	break;
 	}
	document.getElementById("demo").innerHTML=a;
}
</script>
</body>
</html>
```

- 实例解析

#### JavaScript  if...else语句

条件语句用于基于不同的条件来执行不同的动作。

#### 条件语句

通常在写代码时，您总是需要为不同的决定来执行不同的动作。您可以在代码中使用条件语句来完成该任务。

在 JavaScript 中，我们可使用以下条件语句：

- **if 语句** - 只有当指定条件为 true 时，使用该语句来执行代码。
- **if...else 语句** - 当条件为 true 时执行代码，当条件为 false 时执行其他代码。
- **if...else if....else 语句**- 使用该语句来选择多个代码块之一来执行。
- **switch 语句** - 使用该语句来选择多个代码块之一来执行。

#### if 语句

只有当指定条件为 true 时，该语句才会执行代码。

##### 语法

```
if (condition)
{
当条件为 true 时执行的代码
}
```

请使用小写的 **if**。使用大写字母（IF）会生成 JavaScript 错误！

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>if语句</title>
</head>
<body>
<p>如果时间早于 12:00，会获得问候 "Good morning"。</p>
<button onclick="myFunction()">按钮</button>
<p id="demo"></p>
<script>
function myFunction(){
	var a="";
	var time=new Date().getHours();//getHours():返回Date对象的小时(0~23).
	if (time<=12){
		a="Good morning";
    }
	document.getElementById("demo").innerHTML=a;
}
</script>
</body>
</html>
```

请注意，在这个语法中，没有 ..else..。您已经告诉浏览器只有在指定条件为 true 时才执行代码。

#### if...else 语句

请使用 if....else 语句在条件为 true 时执行代码，在条件为 false 时执行其他代码。

##### 语法

```
if (condition)
{
当条件为 true 时执行的代码
}
else
{
当条件不为 true 时执行的代码
}
```

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>if...else语句</title>
</head>
<body>
<p>点击这个按钮，获得基于时间的问候。</p>
<button onclick="myFunction()">按钮</button>
<p id="demo"></p>
<script>
function myFunction(){
    var a="";
    var time=new Date().getHours();//getHours():返回Date对象的小时(0~23).
    if (time<=12){
        a="Good morning";
     }
    else{
        a="Good afternoon";
    }
    document.getElementById("demo").innerHTML=a;
}
</script>
</body>
</html>
```

#### if...else if...else 语句

使用 if....else if...else 语句来选择多个代码块之一来执行。

##### 语法

```
if (condition1)
{
当条件 1 为 true 时执行的代码
}
else if (condition2)
{
当条件 2 为 true 时执行的代码
}
else
{
当条件 1 和 条件 2 都不为 true 时执行的代码
}
```

```html
<html>
<head>
<meta charset="utf-8">
<title> if....else if...else 语句</title>
</head>
<body>
<script type="text/javascript">
var d = new Date();//Date对象用于处理日期与时间，创建Date对象：new Date().
var time = d.getHours();//getHours():返回Date对象的小时(0~23).
if (time<=12)
{
	document.write("<b>good morning</b>");
}
else if (time>12 && time<16)
{
	document.write("<b>good afternoon</b>");
}
else
{
	document.write("<b>good evening</b>");
}
</script>
<p>
这个例子演示了 if..else if...else 语句。
</p>
</body>
</html>
```

### JavaScript switch 语句

switch 语句用于基于不同的条件来执行不同的动作。

#### JavaScript switch 语句

请使用 switch 语句来选择要执行的多个代码块之一。

##### 语法

```
switch(n)
{
    case 1:
        执行代码块 1
        break;
    case 2:
        执行代码块 2
        break;
    default:
        与 case 1 和 case 2 不同时执行的代码
}
```

工作原理：首先设置表达式 *n*（通常是一个变量）。随后表达式的值会与结构中的每个 case 的值做比较。如果存在匹配，则与该 case 关联的代码块会被执行。请使用 **break** 来阻止代码自动地向下一个 case 运行。

实例：

显示今天的星期名称。请注意 Sunday=0, Monday=1, Tuesday=2, 等等

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Switch语句</title>
</head>
<body>
<p>点击下面的按钮来显示今天是周几：</p>
<button onclick="myFunction()">按钮</button>
<p id="demo"></p>
<script>
function myFunction(){
	var a;
	var b=new Date().getDay();//Date对象用于处理日期与时间	
    //创建Date对象：new Date()  getDay():从Date对象返回一周中的某一天(0~6).
	switch (b){
  		case 0:a="今天是星期日";
    	break;
 		case 1:a="今天是星期一";
        break;
  		case 2:a="今天是星期二";
        break;
        case 3:a="今天是星期三";
   	 	break;
  		case 4:a="今天是星期四";
    	break;
  		case 5:a="今天是星期五";
        break;
  		case 6:a="今天是星期六";
    	break;
 	}
	document.getElementById("demo").innerHTML=a;
}
</script>
</body>
</html>
```

#### default 关键词

请使用 default 关键词来规定匹配不存在时做的事情：

实例：

如果今天不是星期六或星期日，则会输出默认的消息：

```html
<html>
<head>
<meta charset="utf-8">
<title>default 关键词</title>
</head>
<body>
<p>点击下面的按钮，会显示出基于今日日期的消息：</p>
<button onclick="myFunction()">按钮</button>
<p id="demo"></p>
<script>
function myFunction()
{
    var a;
    var b=new Date().getDay();
    switch (b)
    {
        case 6:a="今天是星期六";
        break;
        case 0:a="今天是星期日";
        break;
        default:
        a="期待周末";
    }
    document.getElementById("demo").innerHTML=a;
}
</script>
</body>
</html>
```

### JavaScript 消息框

- Alert(警告)框

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <script>
  function myFunction(){
      alert("Hello！I\'am Warning box");
  }
  </script>
  </head>
  <body>
  <input type="button" onclick="myFunction()" value="dispaly Warning box" />
  </body>
  </html>
  ```

- 带有换行的警告框

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>带有换行的警告框</title>
  </head>
  <body>
  <p>点击按钮在弹窗总使用换行。</p>
  <button onclick="myFunction()">按钮</button>
  <p id="demo"></p>
  <script>
  function myFunction(){
  	alert("嗨!\n你最近好吗?");//   \n表示换行
  }
  </script>
  </body>
  </html>
  ```

- 确认框

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>确认框</title>
  </head>
  <body>
  <p>点击按钮，显示确认框。</p>
  <button onclick="myFunction()">按钮</button>
  <p id="demo"></p>
  <script>
  function myFunction(){
      var a;
      var b=confirm("你最近过得好吗?");//confirm()；确认消息对话框。用于允许用户做选择的动作。弹出的对话框中包含一确定按钮和一取消按钮。
  //(str) 参数说明：
  //str:确认对话框中用于显示的文本内容。
  //返回值：
  //当用户点击确认按钮时，返回true;
  //当用户点击取消按钮时，返回false;
      if (b==true){
          a="过得很快活!";
      }
      else{
          a="过得跟狗一样!";
      }
      document.getElementById("demo").innerHTML=a;
  }
  </script>
  ```

- 提示框

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>提示框</title>
  </head>
  <body>
  <p>点击按钮查看输入的对话框。</p>
  <button onclick="myFunction()">按钮</button>
  <p id="demo"></p>
  <script>
  function myFunction(){
  	var a;
  	var fruit=prompt("你喜欢什么水果","香蕉");//prompt() 方法用于显示可提示用户进行输入的对话框。prompt(sometext,defaultText) sometext:要在对话框中显示的纯文本（而不是 HTML 格式的文本）。
   //defaultText:默认的输入文本。
  	if (fruit!=null && fruit!=""){
  	    a="你这么喜欢"+fruit+","+"希望你一直喜欢下去!";
  	    document.getElementById("demo").innerHTML=a;
  	}
  }
  </script>
  </body>
  </html>
  ```

  #### JavaScript 弹窗

  可以在 JavaScript 中创建三种消息框：警告框、确认框、提示框。

  #### 警告框

  警告框经常用于确保用户可以得到某些信息。

  当警告框出现后，用户需要点击确定按钮才能继续进行操作。

  #### 语法

  ```js
  window.alert("textcontent");
  ```

  **window.alert()** 方法可以不带上window对象，直接使用**alert()**方法。

​       实例如下：	

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<script>
function myFunction(){
    alert("Hello！I\'am Warning box");
}
</script>
</head>
<body>
<input type="button" onclick="myFunction()" value="dispaly Warning box" />
</body>
</html>
```

#### 确认框

确认框通常用于验证是否接受用户操作。

当确认卡弹出时，用户可以点击 "确认" 或者 "取消" 来确定用户操作。

当你点击 "确认", 确认框返回 true， 如果点击 "取消", 确认框返回 false。

##### 语法

```js
window.("sometext");
```

**window.()** 方法可以不带上window对象，直接使用**()**方法。

实例如下：

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>确认框</title>
</head>
<body>
<p>点击按钮，显示确认框。</p>
<button onclick="myFunction()">按钮</button>
<p id="demo"></p>
<script>
function myFunction(){
    var a;
    var b=("你最近过得好吗?");//()；确认消息对话框。用于允许用户做选择的动作。弹出的对话框中包含一确定按钮和一取消按钮。
//(str) 参数说明：
//str:确认对话框中用于显示的文本内容。
//返回值：
//当用户点击确认按钮时，返回true;
//当用户点击取消按钮时，返回false;
    if (b==true){
        a="过得很快活!";
    }
    else{
        a="过得跟狗一样!";
    }
    document.getElementById("demo").innerHTML=a;
}
</script>
```

#### 提示框

提示框经常用于提示用户在进入页面前输入某个值。

当提示框出现后，用户需要输入某个值，然后点击确认或取消按钮才能继续操纵。

如果用户点击确认，那么返回值为输入的值。如果用户点击取消，那么返回值为 null。

##### 语法

```js
window.prompt("sometext","defaultvalue");//sometext:要在对话框中显示的纯文本（而不是 HTML 格式的文本）。
 //defaultText:默认的输入文本。
```

**window.prompt()** 方法可以不带上window对象，直接使用**prompt()**方法。

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>提示框</title>
</head>
<body>
<p>点击按钮查看输入的对话框。</p>
<button onclick="myFunction()">按钮</button>
<p id="demo"></p>
<script>
function myFunction(){
	var a;
	var hobby=prompt("请输入你的爱好","编程");//prompt() 方法用于显示可提示用户进行输入的对话框。prompt(sometext,defaultText)sometext:要在对话框中显示的纯文本（而不是 HTML 格式的文本）。
 //defaultText:默认的输入文本。
	if (hobby!=null && hobby!=""){
	    a="你的爱好是" + hobby + "! 希望能将你的爱好坚持下去!";
	    document.getElementById("demo").innerHTML=a;
	}
}
</script>
</body>
</html>
```

#### 换行

弹窗使用 反斜杠 + "n"(\n) 来设置换行。

实例如下：

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>带有换行的警告框</title>
</head>
<body>
<p>点击按钮在弹窗总使用换行。</p>
<button onclick="myFunction()">按钮</button>
<p id="demo"></p>
<script>
function myFunction(){
	alert("嗨!\n你最近好吗?");//   \n表示换行
}
</script>
</body>
</html>
```

### JavaScript函数

- 函数

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8"> 
  <title>函数</title> 
  <script>
  function myFunction(){
      alert("hello,Bob");
  }
  </script>
  </head>
  <body>
  <button onclick="myFunction()">按钮</button>
  <p>当按钮点击后，一个函数将被执行，该函数结果警告一条信息。</p>
  </body>
  </html>
  ```

- 带有参数的函数

  ```html
  <!DOCTYPE html>
  <html>	
  <head> 
  <meta charset="utf-8"> 
  <title>带有参数的函数</title> 
  </head>
  <body>
  <p>点击这个按钮，来调用带参数的函数。</p>
  <button onclick="myFunction('Peter','China')">按钮</button>
  <script>
  function myFunction(name,area){
  	alert("欢迎" + name + ", 来到" +area);
  }
  </script>
  </body>
  </html>
  ```

- 带有参数的函数1

```html
<!DOCTYPE html>
<html> 
<head> 
<meta charset="utf-8"> 
<title>带有参数的函数1</title> 
<script> 
function myfunction(text) { 
	alert(text);
} 
</script> 
</head> 
<body> 
<form> 
<input type="button" 
onclick="myfunction('你确定了文本')" 
value="确定文本"> 
<input type="button" 
onclick="myfunction('你取消了文本')" 
value="取消文本"> 
</form> 
<p>
当你点击其中任意一个按钮，一个函数将被执行，函数结果弹出一个警告显示传递的参数。
</p>
</body> 
</html>
```

- 返回值的的函数

```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>返回值的的函数</title> 
<script>
function myFunction(){
	return ("你好!");
}
</script>
</head>
<body>
<script>
document.write(myFunction())
</script>
</body>
</html>
```

- 带有参数并返回值的函数

  ```html
  <!DOCTYPE html>
  <html>
  <head> 
  <meta charset="utf-8"> 
  <title>带有参数并返回值的函数</title> 
  </head>
  <body>
  <p>本例调用的函数会执行一个计算，然后返回结果：</p>
  <p id="demo"></p>
  <script>
  function myFunction(x,y){
  	return x*y;
  }
  document.getElementById("demo").innerHTML=myFunction(5,5);
  </script>
  </body>
  </html>
  ```

  ### JavaScript 闭包

  JavaScript 变量可以是局部变量或全局变量。

  私有变量可以用到闭包。

#### 全局变量

函数可以访问由函数内部定义的变量，如下所示：

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>函数可以访问由函数内部定义的变量</title>
</head>
<body>
<p>函数可以访问函数内部定义的变量:</p>
<button type="button" onclick="myFunction()">按钮</button>
<p id="demo"></p>
<script>
function myFunction() {
    var x= 2;
    document.getElementById("demo").innerHTML = x * x;
} 
</script>
</body>
</html>
```

函数也可以访问函数外部定义的变量，如下所示：

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>函数也可以访问函数外部定义的变量</title>
</head>
<body>
<p>函数可以访问定义在函数外的变量：</p>
<button type="button" onclick="myFunction()">按钮</button>
<p id="demo"></p>
<script>
var b = 5;
function myFunction() {
    document.getElementById("demo").innerHTML = b * b;
} 
</script>
</body>
</html>
```

后面一个实例中， **b**是一个 **全局** 变量。

在web页面中全局变量属于 window 对象。

全局变量可应用于页面上的所有脚本。

在第一个实例中， **x** 是一个 **局部** 变量。

局部变量只能用于定义它函数内部。对于其他的函数或脚本代码是不可用的。

全局和局部变量即便名称相同，它们也是两个不同的变量。修改其中一个，不会影响另一个的值。

注意：变量声明时如果不使用 **var** 关键字，那么它就是一个全局变量，即便它在函数内定义。

#### 变量生命周期

全局变量的作用域是全局性的，即在整个JavaScript程序中，全局变量处处都在。

而在函数内部声明的变量，只在函数内部起作用。这些变量是局部变量，作用域是局部性的；函数的参数也是局部性的，只在函数内部起作用。

#### 计数器困境

设想下如果你想统计一些数值，且该计数器在所有函数中都是可用的。

你可以使用全局变量，函数设置计数器递增：

实例：

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>计数器</title>
</head>
<body>
<p>全局变量计数。</p>
<button type="button" onclick="myFunction()">计数器</button>
<p id="demo">0</p>
<script>
var counter = 0;
function add() {
    return counter += 1;
}
function myFunction(){
    document.getElementById("demo").innerHTML = add();
}
</script>
</body>
</html>
```

计数器数值在执行 add() 函数时发生变化。

但问题来了，页面上的任何脚本都能改变计数器，即便没有调用 add() 函数。

如果我在函数内声明计数器，如果没有调用函数将无法修改计数器的值：

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>无法修改计数器的值</title>
</head>
<body>
<p>局部变量计数。</p>
<button type="button" onclick="myFunction()">计数器</button>
<p id="demo">0</p>
<script>
function add() {
    var counter = 0;
    return counter += 1;
}
function myFunction(){
    document.getElementById("demo").innerHTML = add();
}
</script>

</body>
</html>
```

以上代码将无法正确输出，每次我调用 add() 函数，计数器都会设置为 1。

**JavaScript 内嵌函数可以解决该问题。**

#### JavaScript 内嵌函数

所有函数都能访问全局变量。 

实际上，在 JavaScript 中，所有函数都能访问它们上一层的作用域。

JavaScript 支持嵌套函数。嵌套函数可以访问上一层的函数变量。

该实例中，内嵌函数 **plus()** 可以访问父函数的 **counter** 变量；

实例：

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>JavaScript 内嵌函数</title>
</head>
<body>
<p>局部变量计数。</p>
<p id="demo">0</p>
<script>
document.getElementById("demo").innerHTML = add();
function add() {
	var counter = 0;
    function plus() {counter += 1;}
    plus();    
    return counter; 
}
</script>
</body>
</html>
```

如果我们能在外部访问 **plus()** 函数，这样就能解决计数器的困境。

我们同样需要确保 **counter = 0** 只执行一次。

**我们需要闭包。**

#### JavaScript 闭包

还记得函数自我调用吗？该函数会做什么？

实例：

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>JavaScript 闭包</title>
</head>
<body>
<p>局部变量计数。</p>
<button type="button" onclick="myFunction()">计数器</button>
<p id="demo">0</p>
<script>
var add = (function () {
    var counter = 0;
    return function () {return counter += 1;}
})();
function myFunction(){
    document.getElementById("demo").innerHTML = add();
}
</script>
</body>
</html>
```

#### 实例解析

变量 **add** 指定了函数自我调用的返回字值。

自我调用函数只执行一次。设置计数器为 0。并返回函数表达式。

add变量可以作为一个函数使用。非常棒的部分是它可以访问函数上一层作用域的计数器。

这个叫作 JavaScript **闭包。**它使得函数拥有私有变量变成可能。

计数器受匿名函数的作用域保护，只能通过 add 方法修改。

注意： 闭包是一种保护私有变量的机制，在函数执行时形成私有的作用域，保护里面的私有变量不受外界干扰。直观的说就是形成一个不销毁的栈环境。

### JavaScript循环

- for循环

  ```html
  <!DOCTYPE html>
  <html>
  <head> 
  <meta charset="utf-8"> 
  <title>for循环</title> 
  </head>
  <body>
  
  <p>单击按钮将代码块循环执行7次。</p>
  <button onclick="myFunction()">按钮</button>
  <p id="demo"></p>
  <script>
  function myFunction(){
  	var a="",i;
  	for (i=0;i<7;i++){
  		a=a + "这个数字是" + i + "<br>";
  	}
  	document.getElementById("demo").innerHTML=a;
  }
  </script>
  </body>
  </html>
  ```

- 循环输出HTML标题

  ```html
  <!DOCTYPE html>
  <html>
  <head> 
  <meta charset="utf-8"> 
  <title>循环输出HTML标题</title> 
  </head>
  <body>
  <p>单击按钮将HTML标题设置从1到6的样式显示</p>
  <button onclick="myFunction()">按钮</button>
  <div id="demo"></div>
  <script>
  function myFunction(){
  	var x="",i;
  	for (i=1; i<=6; i++){
  		x=x + "<h" + i + ">你好 " + i + "</h" + i + ">";
  	}
  	document.getElementById("demo").innerHTML=x;
  }
  </script>
  </body>
  </html>
  ```

- While循环

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>While循环</title>
  </head>
  <body>
  <p>点击下面的按钮，只要 i 小于 7 就一直循环代码块。</p>
  <button onclick="myFunction()">按钮</button>
  <p id="demo"></p>
  <script>
  function myFunction(){
  	var a="",i=0;
  	while (i<7){
  		a=a + "该数字为 " + i + "<br>";
  		i++;
  	}
  	document.getElementById("demo").innerHTML=a;
  }
  </script>
  </body>
  </html>
  ```

- Do   While 循环

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>Do   While 循环</title>
  </head>
  <body>
  <p>点击下面的按钮，只要 i 小于 8就一直循环代码块。</p>
  <button onclick="myFunction()">按钮</button>
  <p id="demo"></p>
  <script>
  function myFunction(){
  	var a="",i=0;
  	do{
  		a=a + "该数字为 " + i + "<br>";
  	    i++;
  	}
  	while (i<8)  
  	document.getElementById("demo").innerHTML=a;
  }
  </script>
  </body>
  </html>
  ```

- break语句

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>break语句</title>
  </head>
  <body>
  <p>点击按钮，测试带有 break 语句的循环。</p>
  <button onclick="myFunction()">按钮</button>
  <p id="demo"></p>
  <script>
  function myFunction(){
  	var a="",i=0;
  	for (i=0;i<20;i++){
  		if (i==15){
      			break;
  			}
      	a=a + "该数字为 " + i + "<br>";
      }
  	document.getElementById("demo").innerHTML=a;
  }
  </script>
  </body>
  </html>
  ```

- continue语句

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>continue语句</title>
  </head>
  <body>
  <p>点击下面的按钮来执行循环，该循环会跳过 i=10 的数字。</p>
  <button onclick="myFunction()">按钮</button>
  <p id="demo"></p>
  <script>
  function myFunction(){
      var a="",i=0;
      for (i=0;i<20;i++){
          if (i==10){
              continue;
          }
          a=a + "该数字为 " + i + "<br>";
      }
      document.getElementById("demo").innerHTML=a;
  }
  </script>
  </body>
  </html>
  ```

- 使用for ....in声明来遍历数组内的元素

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>使用for ....in声明来遍历数组内的元素</title>
  </head>
  <body>
  <p>点击下面的按钮，循环遍历对象 "person" 的属性。</p>
  <button onclick="myFunction()">按钮</button>
  <p id="demo"></p>
  <script>
  function myFunction(){
      var a;
      var text="";
      var person={fname:"Bob",lname:"Tom",age:20}; 
      for (a in person){
          text=text + person[a];
      }
      document.getElementById("demo").innerHTML=text;
  }
  </script>
  </body>
  </html>
  ```

- 实例解析

  ### JavaScript for 循环

  循环可以将代码块执行指定的次数。

  #### JavaScript 循环

  如果您希望一遍又一遍地运行相同的代码，并且每次的值都不同，那么使用循环是很方便的。

  我们可以这样输出数组的值：

  一般写法：

  ```js
  document.write(cars[0] + "<br>"); 
  document.write(cars[1] + "<br>"); 
  document.write(cars[2] + "<br>"); 
  document.write(cars[3] + "<br>"); 
  document.write(cars[4] + "<br>"); 
  document.write(cars[5] + "<br>");
  ```

  使用for循环	

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>使用for循环</title>
  </head>     
  <body>
  <script>
  cars=["小说1","小说2","小说3","小说4"];
  for (var i=0;i<cars.length;i++){ //length:设置或返回数组元素的个数。
      document.write(cars[i] + "<br>");
  }
  </script>
  </body>
  </html>
  ```

  #### 不同类型的循环

  JavaScript 支持不同类型的循环：

  - **for** - 循环代码块一定的次数
  - **for/in** - 循环遍历对象的属性
  - **while** - 当指定的条件为 true 时循环指定的代码块
  - **do/while** - 同样当指定的条件为 true 时循环指定的代码块

  #### For 循环

  for 循环是您在希望创建循环时常会用到的工具。

  下面是 for 循环的语法：

  ```
  for (语句 1; 语句 2; 语句 3)
  {
      被执行的代码块
  }
  ```

  **语句 1** （代码块）开始前执行

  **语句 2** 定义运行循环（代码块）的条件

  **语句 3** 在循环（代码块）已被执行之后执行

  实例：

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>for循环</title>
  </head>
  <body>
  <p>点击按钮循环代码15次。</p>
  <button onclick="myFunction()">按钮</button>
  <p id="demo"></p>
  <script>
  function myFunction(){
  	var a="";
  	for (var i=0;i<15;i++){
  		a=a + "该数字为 " + i + "<br>";
  	}
  	document.getElementById("demo").innerHTML=a;
  }
  </script>
  </body>
  </html>
  ```

  从上面的例子中，您可以看到：

  Statement 1 在循环开始之前设置变量 (var i=0)。

  Statement 2 定义循环运行的条件（i 必须小于 15）。

  Statement 3 在每次代码块已被执行后增加一个值 (i++)。

  #### 语句 1

  通常我们会使用语句 1 初始化循环中所用的变量 (var i=0)。

  语句 1 是可选的，也就是说不使用语句 1 也可以。

  您可以在语句 1 中初始化任意（或者多个）值：

  实例：

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>使用for循环</title>
  </head>     
  <body>
  <script>
  cars=["小说1","小说2","小说3","小说4"];
  for (var i=0;i<cars.length;i++){ //length:设置或返回数组元素的个数。
      document.write(cars[i] + "<br>");
  }
  </script>
  </body>
  </html>
  ```

  同时您还可以省略语句 1（比如在循环开始前已经设置了值时）：

  实例：

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>使用for循环</title>
  </head>
  <body>
  <script>
  cars=["BMW","Volvo","Saab","Ford"];
  var i=2,len=cars.length;
  for (; i<len; i++){
  	document.write(cars[i] + "<br>");
  }
  </script>
  </body>
  </html>
  ```

  #### 语句 2

  通常语句 2 用于评估初始变量的条件。

  语句 2 同样是可选的。

  如果语句 2 返回 true，则循环再次开始，如果返回 false，则循环将结束。

  注意：如果您省略了语句 2，那么必须在循环内提供 *break*。否则循环就无法停下来。这样有可能令浏览器崩溃。请在本教程稍后的章节阅读有关 break 的内容。

  #### 语句 3

  通常语句 3 会增加初始变量的值。

  语句 3 也是可选的。

  语句 3 有多种用法。增量可以是负数 (i--)，或者更大 (i=i+15)。

  语句 3 也可以省略（比如当循环内部有相应的代码时）：

  实例:

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>for循环</title>
  </head>
  <body>
  <script>
  cars=["小说1","小说2","小说3","小说4"];
  var i=0,len=cars.length;
  for (; i<len; ){
  	document.write(cars[i] + "<br>");
  	i++;
  }
  </script>
  </body>
  </html>
  ```

  #### For/In 循环

  JavaScript for/in 语句循环遍历对象的属性：

  实例：

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>使用for ....in声明来遍历数组内的元素</title>
  </head>
  <body>
  <p>点击下面的按钮，循环遍历对象 "person" 的属性。</p>
  <button onclick="myFunction()">按钮</button>
  <p id="demo"></p>
  <script>
  function myFunction(){
      var a;
      var text="";
      var person={fname:"Bob",lname:"Tom",age:20}; 
      for (a in person){
          text=text + person[a];
      }
      document.getElementById("demo").innerHTML=text;
  }
  </script>
  </body>
  </html>
  ```

  ### JavaScript while 循环

  只要指定条件为 true，循环就可以一直执行代码块。

  #### while 循环

  while 循环会在指定条件为真时循环执行代码块。

  ##### 语法

  ```
  while (条件)
  {
      需要执行的代码
  }
  ```

  ##### 实例

  本例中的循环将继续运行，只要变量 i 小于 8：

  实例

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>while循环</title>
  </head>
  <body>
  <p>点击下面的按钮，只要 i 小于 8 就一直循环代码块。</p>
  <button onclick="myFunction()">按钮</button>
  <p id="demo"></p>
  <script>
  function myFunction(){
  	var a="",i=0;
  	while (i<8){
  		a=a + "该数字为 " + i + "<br>";
  		i++;
  	}
  	document.getElementById("demo").innerHTML=a;
  }
  </script>
  </body>
  </html>
  ```

  注意： 如果您忘记增加条件中所用变量的值，该循环永远不会结束。这可能导致浏览器崩溃。

  #### do/while 循环

  do/while 循环是 while 循环的变体。该循环会在检查条件是否为真之前执行一次代码块，然后如果条件为真的话，就会重复这个循环。

  ##### 语法

  ```
  do
  {
      需要执行的代码
  }
  while (条件);
  ```

  ##### 实例	

  下面的例子使用 do/while 循环。该循环至少会执行一次，即使条件为 false 它也会执行一次，因为代码块会在条件被测试前执行：

  实例

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>do/while 循环</title>
  </head>
  <body>
  <p>点击下面的按钮，只要 i 小于 9 就一直循环代码块。</p>
  <button onclick="myFunction()">按钮</button>
  <p id="demo"></p>
  <script>
  function myFunction(){
      var x="",i=0;
      do{
          x=x + "该数字为 " + i + "<br>";
          i++;
      }
      while (i<9)  
      document.getElementById("demo").innerHTML=x;
  }
  </script>
  </body>
  </html>
  ```

  别忘记增加条件中所用变量的值，否则循环永远不会结束！

  #### 比较 for 和 while

  如果您已经阅读了前面那一章关于 for 循环的内容，您会发现 while 循环与 for 循环很像。

  本例中的循环使用 **for 循环**来显示 cars 数组中的所有值：

  实例

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>for循环</title>
  </head>
  <body>
  <script>
  cars=["BMW","Volvo","Saab","Ford"];
  var i=0;
  for (;cars[i];){
  	document.write(cars[i] + "<br>");
  	i++;
  }
  </script>
  </body>
  </html>
  ```

  本例中的循环使用 **while 循环**来显示 cars 数组中的所有值：

  实例

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>while 循环</title>
  </head>
  <body>
  <script>
  cars=["BMW","Volvo","Saab","Ford"];
  var i=0;
  while (cars[i]){
      document.write(cars[i] + "<br>");
      i++;
  }
  </script>
  </body>
  </html>
  ```

  ### JavaScript break 和 continue 语句
  
  break 语句用于跳出循环。
  
  continue 用于跳过循环中的一个迭代。
  
  #### break 语句
  
  我们已经在本教程之前的章节中见到过 break 语句。它用于跳出 switch() 语句。
  
  break 语句可用于跳出循环。
  
  continue 语句跳出循环后，会继续执行该循环之后的代码（如果有的话）：
  
  实例
  
  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>break语句</title>
  </head>
  <body>
  <p>点击按钮，测试带有 break 语句的循环。</p>
  <button onclick="myFunction()">按钮</button>
  <p id="demo"></p>
  <script>
  function myFunction(){
  	var a="",i=0;
  	for (i=0;i<10;i++){
  		if (i==5){
      			break;
  			}
      	a=a + "该数字为 " + i + "<br>";
      }
  	document.getElementById("demo").innerHTML=a;
  }
  </script>
  </body>
  </html>
  ```
  
  由于这个 if 语句只有一行代码，所以可以省略花括号：
  
  ```js
  for (i=0;i<10;i++)
  {
      if (i==5) break;
      x=x + "The number is " + i + "<br>";
  }
  ```
  
  #### continue 语句	
  
  **continue 语句**中断循环中的迭代，如果出现了指定的条件，然后继续循环中的下一个迭代。 该例子跳过了值 7：
  
  实例
  
  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>for循环</title>
  </head>
  <body>
  <p>点击下面的按钮来执行循环，该循环会跳过 i=7 的数字。</p>
  <button onclick="myFunction()">按钮</button>
  <p id="demo"></p>
  <script>
  function myFunction(){
  	var a="",i=0;
  	for (i=0;i<10;i++){
    		if (i==7){
      		continue;
      	}
  		a=a + "该数字为 " + i + "<br>";
    	}
  	document.getElementById("demo").innerHTML=a;
  }
  </script>
  </body>
  </html>
  ```
  
  #### JavaScript 标签
  
  正如您在 switch 语句那一章中看到的，可以对 JavaScript 语句进行标记。
  
  如需标记 JavaScript 语句，请在语句之前加上冒号：
  
  ```
  label:
  statements
  ```
  
  break 和 continue 语句仅仅是能够跳出代码块的语句。
  
  语法:
  
  ```js
  break labelname; 
   
  continue labelname;
  ```
  
  continue 语句（带有或不带标签引用）只能用在循环中。
  
  break 语句（不带标签引用），只能用在循环或 switch 中。
  
  通过标签引用，break 语句可用于跳出任何 JavaScript 代码块：
  
  实例
  
  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>通过标签引用，break 语句可用于跳出任何 JavaScript 代码块</title>
  </head>
  <body>
  <script>
  cars=["BMW","Volvo","Saab","Ford"];
  list:{
  	document.write(cars[0] + "<br>"); 
  	document.write(cars[1] + "<br>"); 
  	document.write(cars[2] + "<br>"); 
  	break list;
  	document.write(cars[3] + "<br>"); 
  	document.write(cars[4] + "<br>"); 
  	document.write(cars[5] + "<br>"); 
  }
  </script>
  </body>
  </html>
  ```

### JavaScript 事件

- onclick事件

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>onclick事件</title>
<script>
function displayDate(){
	document.getElementById("demo").innerHTML=Date();
}
</script>
</head>
<body>
<h1>我的第一个 JavaScript 程序</h1>
<p id="demo">显示日期的地方</p>
<button type="button" onclick="displayDate()">显示日期</button>
</body>
</html>
```

- onmouseover事件

```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>onmouseover事件</title> 
<script>
function writeText(txt){
	document.getElementById("desc").innerHTML=txt;
}
</script>
</head>
<body>
<img src ="planets.gif" width ="145" height ="126" alt="Planets" usemap="#planetmap" />
<map name="planetmap">
<area shape ="rect" coords ="0,0,82,126"
onmouseover="writeText('太阳和气体巨星类似木星是太阳系中最大的物体。')"
href ="sun.htm" target ="_blank" alt="Sun" />
<area shape ="circle" coords ="90,58,3"
onmouseover="writeText('从地球上很难研究水星，因为它太接近太阳。')"
href ="mercur.htm" target ="_blank" alt="Mercury" />
<area shape ="circle" coords ="124,58,8"
onmouseover="writeText('至到1960年，金星经常被认为是地球的孪生妹妹，因为金星是最靠近我们的行星，并且两个行星有很多相似的特点。')" t')"
href ="venus.htm" target ="_blank" alt="Venus" />
</map> 
<p id="desc">鼠标在太阳和星星上移动，可以看到不同的描述。</p>
</body>
</html>
```

### JavaScript HTML DOM 事件

HTML DOM 使 JavaScript 有能力对 HTML 事件做出反应。

#### 对事件做出反应

我们可以在事件发生时执行 JavaScript，比如当用户在 HTML 元素上点击时。

如需在用户点击某个元素时执行代码，请向一个 HTML 事件属性添加 JavaScript 代码：

```
onclick=JavaScript
```

HTML 事件的例子：

- 当用户点击鼠标时
- 当网页已加载时
- 当图像已加载时
- 当鼠标移动到元素上时
- 当输入字段被改变时
- 当提交 HTML 表单时
- 当用户触发按键时

在本例中，当用户在 <h1> 元素上点击时，会改变其内容：

实例

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>onclick事件</title>
</head>
<body>
<h1 onclick="this.innerHTML='你好!'">点击文本!</h1>
</body>
</html>
```

本例从事件处理器调用一个函数：

实例

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>onclick事件</title>
</head>
<head>
<script>
function changetext(id){
    id.innerHTML="你好!";
}
</script>
</head>
<body>
<h1 onclick="changetext(this)">点击文本!</h1>
</body>
</html>
```

#### HTML 事件属性

如需向 HTML 元素分配 事件，您可以使用事件属性。

实例

向 button 元素分配 onclick 事件：

```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>向 button 元素分配 onclick 事件</title> 
</head>
<body>
<p>点击按钮执行 <em>displayDate()</em> 函数.</p>
<button onclick="displayDate()">按钮</button>
<script>
function displayDate(){
    document.getElementById("demo").innerHTML=Date();
}
</script>
<p id="demo"></p>
</body>
</html>
```

在上面的例子中，名为 displayDate 的函数被分配给 id="myBtn" 的 HTML 元素。

按钮点击时Javascript函数将会被执行。

#### onload 和 onunload 事件

onload 和 onunload 事件会在用户进入或离开页面时被触发。

onload 事件可用于检测访问者的浏览器类型和浏览器版本，并基于这些信息来加载网页的正确版本。

onload 和 onunload 事件可用于处理 cookie。

实例

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>弹窗</title>
</head>
<body onload="checkCookies()">
<script>
function checkCookies(){
	if (navigator.cookieEnabled==true){
		alert("Cookies 可用")
	}
	else{
		alert("Cookies 不可用")
	}
}
</script>
<p>弹窗-提示浏览器 cookie 是否可用。</p>
</body>
</html>
```

#### onchange 事件

onchange 事件常结合对输入字段的验证来使用。

下面是一个如何使用 onchange 的例子。当用户改变输入字段的内容时，会调用 upperCase() 函数。

实例

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>改变字母</title>
</head>
<head>
<script>
function myFunction(){
	var x=document.getElementById("fname");
	x.value=x.value.toUpperCase();
}
</script>
</head>
<body>
输入你的名字: <input type="text" id="fname" onchange="myFunction()">
<p>当你离开输入框后，函数将被触发，将小写字母转为大写字母。</p>
</body>
</html>
```

#### onmouseover 和 onmouseout 事件

onmouseover 和 onmouseout 事件可用于在用户的鼠标移至 HTML 元素上方或移出元素时触发函数。

实例

一个简单的 onmouseover-onmouseout 实例：

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>onmouseover-onmouseout 实例/title>
</head>
<body>
<div onmouseover="mOver(this)" onmouseout="mOut(this)" style="background-color:#D94A38;width:120px;height:20px;padding:40px;">Mouse Over Me</div>
<script>
function mOver(obj){
	obj.innerHTML="Thank You"
}
function mOut(obj){
	obj.innerHTML="Mouse Over Me"
}
</script>

</body>
</html>
```

------

#### onmousedown、onmouseup 以及 onclick 事件

onmousedown, onmouseup 以及 onclick 构成了鼠标点击事件的所有部分。首先当点击鼠标按钮时，会触发 onmousedown 事件，当释放鼠标按钮时，会触发 onmouseup 事件，最后，当完成鼠标点击时，会触发 onclick 事件。

实例

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>onmousedown和onmouseup事件</title>
</head>
<head>
<script>
function lighton(){
	document.getElementById('myimage').src="bulbon.gif";
}
function lightoff(){
	document.getElementById('myimage').src="bulboff.gif";
}
</script>
</head>
<body>
<img id="myimage" onmousedown="lighton()" onmouseup="lightoff()" src="bulboff.gif" width="100" height="180" />
<p>点击不释放鼠标灯将一直亮着!</p>
</body>
</html>
```

onload

当页面完成加载时，显示一个提示框。

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>当页面完成加载时，显示一个提示框</title>
</head>
<head>
<script>
function mymessage(){
	alert("消息在 onload 事件触发后弹出。");
}
</script>
</head>
<body onload="mymessage()"></body>
</html>
```

onfocus

当输入字段获得焦点时，改变其背景色。

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>当输入字段获得焦点时，改变其背景色</title>
</head>
<head>
<script>
function myFunction(x){
	x.style.background="blue";
}
</script>
</head>
<body>
输入你的名字: <input type="text" onfocus="myFunction(this)">
<p>当输入框获取焦点时，修改背景色（background-color属性） 将被触发。</p>
</body>
</html>
```

鼠标事件

当指针移动到元素上方时，改变其颜色；当指针移出文本后，会再次改变其颜色。

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>鼠标事件</title>
</head>
<body>
<h1 onmouseover="style.color='green'"onmouseout="style.color='black'">鼠标移过来</h1>
</body>
</html>
```

### JavaScript 错误处理

- try...catch语句

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>try...catch语句</title>
<script>
var txt="";
function message(){
	try {
		abcdlert("Welcome guest!");
	}
	catch(err) {
		txt="本页有一个错误。\n\n";
		txt+="错误描述：" + err.message + "\n\n";
		txt+="点击确定继续。\n\n";
		alert(txt);
	}
}
</script>
</head>
<body>
<input type="button" value="查看消息" onclick="message()" />
</body>
</html>
```

- 带有确认框的 try...catch 语句

```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>带有确认框的 try...catch 语句</title> 
<script>
var txt="";
function message(){
	try{
		adddlert("Welcome guest!");
	}
	catch(err){
		txt="本页有一个错误。\n\n";
		txt+="单击确定继续跳转\n";	
		txt+="或者单击取消返回\n\n";
		if((txt)){
			document.location.href="//www.runoob.com/";
		}
	}
}
</script>
</head>
<body>
<input type="button" value="查看消息" onclick="message()" />
</body>
</html>
```

- onerror事件

```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>onerror事件</title> 
<script>
onerror=handleErr;
var txt="";
function handleErr(msg,url,l){
    txt="该页面有一个错误\n\n";
    txt+="错误: " + msg + "\n";
    txt+="URL: " + url + "\n";
    txt+="行: " + l + "\n\n";
    txt+="点击确定继续。\n\n";
    alert(txt);
    return true;
}
function message(){
    adddlert("Welcome guest!");
}
</script>
</head>
<body>
<input type="button" value="查看消息" onclick="message()" />
</body>
</html>
```

### JavaScript 错误 - throw、try 和 catch

**try** 语句测试代码块的错误。

**catch** 语句处理错误。

**throw** 语句创建自定义错误。

**finally** 语句在 try 和 catch 语句之后，无论是否有触发异常，该语句都会执行。

####  JavaScript 错误

当 JavaScript 引擎执行 JavaScript 代码时，会发生各种错误。

可能是语法错误，通常是程序员造成的编码错误或错别字。

可能是拼写错误或语言中缺少的功能（可能由于浏览器差异）。

可能是由于来自服务器或用户的错误输出而导致的错误。

当然，也可能是由于许多其他不可预知的因素。

#### JavaScript 抛出（throw）错误

当错误发生时，当事情出问题时，JavaScript 引擎通常会停止，并生成一个错误消息。

描述这种情况的技术术语是：JavaScript 将**抛出**一个错误。

#### JavaScript try 和 catch

**try** 语句允许我们定义在执行时进行错误测试的代码块。

**catch** 语句允许我们定义当 try 代码块发生错误时，所执行的代码块。

JavaScript 语句 **try** 和 **catch** 是成对出现的。

##### 语法

```
try {
    ...    //异常的抛出
} catch(e) {
    ...    //异常的捕获与处理
} finally {
    ...    //结束处理
}
```

#### 实例

在下面的例子中，我们故意在 try 块的代码中写了一个错字。

catch 块会捕捉到 try 块中的错误，并执行代码来处理它。

实例

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>捕获异常</title>
<script>
var txt="";
function message(){
	try {
		adddlert("Welcome guest!");
	}
	catch(err) {
		txt="本页有一个错误。\n\n";
		txt+="错误描述：" + err.message + "\n\n";
		txt+="点击确定继续。\n\n";
		alert(txt);
	}
}
</script>
</head>
<body>
<input type="button" value="查看消息" onclick="message()" />
</body>
</html>
```

#### finally 语句

finally 语句不论之前的 try 和 catch 中是否产生异常都会执行该代码块。

实例

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>finally 语句</title>
</head>
<body>
<p>不管输入是否正确，输入框都会再输入后清空。</p>
<p>请输入 5 ~ 10 之间的数字：</p>
<input id="demo" type="text">
<button type="button" onclick="myFunction()">点我</button>
<p id="p01"></p>
<script>
function myFunction() {
  var message, x;
  message = document.getElementById("p01");
  message.innerHTML = "";
  x = document.getElementById("demo").value;
  try { 
    if(x == "") throw "值是空的";
    if(isNaN(x)) throw "值不是一个数字";
    x = Number(x);
    if(x > 10) throw "太大";
    if(x < 5) throw "太小";
  }
  catch(err) {
    message.innerHTML = "错误: " + err + ".";
  }
  finally {
    document.getElementById("demo").value = "";
  }
}
</script>
</body>
</html>
```

#### Throw 语句

throw 语句允许我们创建自定义错误。

正确的技术术语是：创建或**抛出异常**（exception）。

如果把 throw 与 try 和 catch 一起使用，那么您能够控制程序流，并生成自定义的错误消息。

##### 语法

```
throw exception
```

异常可以是 JavaScript 字符串、数字、逻辑值或对象。

#### 实例

本例检测输入变量的值。如果值是错误的，会抛出一个异常（错误）。catch 会捕捉到这个错误，并显示一段自定义的错误消息：

实例

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>throw抛出异常</title>
</head>
<body>
<p>请输出一个 5 到 10 之间的数字:</p>
<input id="demo" type="text">
<button type="button" onclick="myFunction()">测试输入</button>
<p id="message"></p>
<script>
function myFunction() {
    var message, x;
    message = document.getElementById("message");
    message.innerHTML = "";
    x = document.getElementById("demo").value;
    try { 
        if(x == "")  throw "值为空";
        if(isNaN(x)) throw "不是数字";
        x = Number(x);
        if(x < 5)    throw "太小";
        if(x > 10)   throw "太大";
    }
    catch(err) {
        message.innerHTML = "错误: " + err;
    }
}
</script>
</body>
</html>
```

请注意，如果 getElementById 函数出错，上面的例子也会抛出一个错误。

### 高级 JavaScript 实例

- 创建一个欢迎的cookie

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>创建一个欢迎的cookie</title>
</head>
<head>
<script>
function setCookie(cname,cvalue,exdays){
	var d = new Date();
	d.setTime(d.getTime()+(exdays*24*60*60*1000));//setTime():setTime()方法以毫秒设置 Date 对象。getTime():返回 1970 年 1 月 1 日至今的毫秒数。
	var expires = "expires="+d.toUTCString();//toUTCString():根据世界时，把 Date 对象转换为字符串。
	document.cookie = cname+"="+cvalue+"; "+expires;
}
function getCookie(cname){
	var name = cname + "=";
	var ca = document.cookie.split(';');//split:把字符串分割为字符串数组。
	for(var i=0; i<ca.length; i++) {//length:设置或返回数组元素的个数。
		var c = ca[i].trim();//trim() 方法用于删除字符串的头尾空格。trim() 方法不会改变原始字符串。
		if (c.indexOf(name)==0) { return c.substring(name.length,c.length); }
	}//indexOf:返回某个指定的字符串值，在字符串中首次出现的位置。substring:提取字符串中两个指定的索引号之间的字符。
	return "";
}
function checkCookie(){
	var user=getCookie("username");
	if (user!=""){
		alert("欢迎 " + user + " 再次访问");
	}
	else {
		user = prompt("请输入你的名字:","");//prompt() 方法用于显示可提示用户进行输入的对话框。
  		if (user!="" && user!=null){
    		setCookie("username",user,30);
    	}
	}
}
</script>
</head>
<body onload="checkCookie()"></body>
</html>
```

#### JavaScript Cookie

Cookie 用于存储 web 页面的用户信息。

#### 什么是 Cookie？

Cookie 是一些数据, 存储于你电脑上的文本文件中。

当 web 服务器向浏览器发送 web 页面时，在连接关闭后，服务端不会记录用户的信息。

Cookie 的作用就是用于解决 "如何记录客户端的用户信息":

- 当用户访问 web 页面时，他的名字可以记录在 cookie 中。
- 在用户下一次访问该页面时，可以在 cookie 中读取用户访问记录。

Cookie 以名/值对形式存储，如下所示:

```
username=John Doe
```

当浏览器从服务器上请求 web 页面时， 属于该页面的 cookie 会被添加到该请求中。服务端通过这种方式来获取用户的信息。

#### 使用 JavaScript 创建Cookie

JavaScript 可以使用 **document.cookie** 属性来创建 、读取、及删除 cookie。

JavaScript 中，创建 cookie 如下所示：

```js
document.cookie="username=John Doe";
```

您还可以为 cookie 添加一个过期时间（以 UTC 或 GMT 时间）。默认情况下，cookie 在浏览器关闭时删除：

```js
document.cookie="username=John Doe; expires=Thu, 18 Dec 2043 12:00:00 GMT";
```

您可以使用 path 参数告诉浏览器 cookie 的路径。默认情况下，cookie 属于当前页面。

```js
document.cookie="username=John Doe; expires=Thu, 18 Dec 2043 12:00:00 GMT; path=/";
```

#### 使用 JavaScript 读取 Cookie

在 JavaScript 中, 可以使用以下代码来读取 cookie：

```js
var x = document.cookie;
```

注意： document.cookie 将以字符串的方式返回所有的 cookie，类型格式： cookie1=value; cookie2=value; cookie3=value;

#### 使用 JavaScript 修改 Cookie

在 JavaScript 中，修改 cookie 类似于创建 cookie，如下所示：

```js
document.cookie="username=John Smith; expires=Thu, 18 Dec 2043 12:00:00 GMT; path=/";
```

旧的 cookie 将被覆盖。

#### 使用 JavaScript 删除 Cookie

删除 cookie 非常简单。您只需要设置 expires 参数为以前的时间即可，如下所示，设置为 Thu, 01 Jan 1970 00:00:00 GMT

```js
document.cookie = "username=; expires=Thu, 01 Jan 1970 00:00:00 GMT";
```

注意，当您删除时不必指定 cookie 的值。

------

#### Cookie 字符串

document.cookie 属性看起来像一个普通的文本字符串，其实它不是。

即使您在 document.cookie 中写入一个完整的 cookie 字符串, 当您重新读取该 cookie 信息时，cookie 信息是以名/值对的形式展示的。

如果您设置了新的 cookie，旧的 cookie 不会被覆盖。 新 cookie 将添加到 document.cookie 中，所以如果您重新读取document.cookie，您将获得如下所示的数据：

cookie1=value; cookie2=value;

<button>显示所有Cookie</button>   <button>创建Cookie1</button>    <button>创建Cookie2 </button>    <button>删除Cookie1 </button>    <button>删除Cookie2</button>

如果您需要查找一个指定 cookie 值，您必须创建一个JavaScript 函数在 cookie 字符串中查找 cookie 值。

#### JavaScript Cookie 实例

在以下实例中，我们将创建 cookie 来存储访问者名称。

首先，访问者访问 web 页面, 他将被要求填写自己的名字。该名字会存储在 cookie 中。

访问者下一次访问页面时，他会看到一个欢迎的消息。

在这个实例中我们会创建 3 个 JavaScript 函数:

1. 设置 cookie 值的函数
2. 获取 cookie 值的函数
3. 检测 cookie 值的函数

#### 设置 cookie 值的函数

首先，我们创建一个函数用于存储访问者的名字：

```js
function setCookie(cname,cvalue,exdays)
{
  var d = new Date();
  d.setTime(d.getTime()+(exdays*24*60*60*1000));
  var expires = "expires="+d.toGMTString();
  document.cookie = cname + "=" + cvalue + "; " + expires;
}
```

##### 函数解析：

以上的函数参数中，cookie 的名称为 cname，cookie 的值为 cvalue，并设置了 cookie 的过期时间 expires。

该函数设置了 cookie 名、cookie 值、cookie过期时间。

#### 获取 cookie 值的函数

然后，我们创建一个函数用户返回指定 cookie 的值：

```js
function getCookie(cname)
{
  var name = cname + "=";
  var ca = document.cookie.split(';');
  for(var i=0; i<ca.length; i++) 
  {
    var c = ca[i].trim();
    if (c.indexOf(name)==0) return c.substring(name.length,c.length);
  }
  return "";
}
```

##### 函数解析：

cookie 名的参数为 cname。

创建一个文本变量用于检索指定 cookie :cname + "="。

使用分号来分割 document.cookie 字符串，并将分割后的字符串数组赋值给 ca (ca = document.cookie.split(';'))。

循环 ca 数组 (i=0;i<ca.length;i++)，然后读取数组中的每个值，并去除前后空格 (c=ca[i].trim())。

如果找到 cookie(c.indexOf(name) == 0)，返回 cookie 的值 (c.substring(name.length,c.length)。

如果没有找到 cookie, 返回 ""。

#### 检测 cookie 值的函数

最后，我们可以创建一个检测 cookie 是否创建的函数。

如果设置了 cookie，将显示一个问候信息。

如果没有设置 cookie，将会显示一个弹窗用于询问访问者的名字，并调用 setCookie 函数将访问者的名字存储 365 天：

```js
function checkCookie()
{
  var username=getCookie("username");
  if (username!="")
  {
    alert("Welcome again " + username);
  }
  else 
  {
    username = prompt("Please enter your name:","");
    if (username!="" && username!=null)
    {
      setCookie("username",username,365);
    }
  }
}
```

#### 完整实例

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Cookie</title>
</head>
<head>
<script>
function setCookie(cname,cvalue,exdays){
	var d = new Date();
	d.setTime(d.getTime()+(exdays*24*60*60*1000));
	var expires = "expires="+d.toGMTString();
	document.cookie = cname+"="+cvalue+"; "+expires;
}
function getCookie(cname){
	var name = cname + "=";
	var ca = document.cookie.split(';');
	for(var i=0; i<ca.length; i++) {
		var c = ca[i].trim();
		if (c.indexOf(name)==0) { return c.substring(name.length,c.length); }
	}
	return "";
}
function checkCookie(){
	var user=getCookie("username");
	if (user!=""){
		alert("欢迎 " + user + " 再次访问");
	}
	else {
		user = prompt("请输入你的名字:","");
  		if (user!="" && user!=null){
    		setCookie("username",user,30);
    	}
	}
}
</script>
</head>	
<body onload="checkCookie()"></body>
</html>
```

- 简单的计时

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>简单的计时</title>
</head>
<body>
<p>点击按钮，在等待 3 秒后弹出 "Hello"。</p>
<button onclick="myFunction()">点我</button>
<script>
function myFunction(){
	setTimeout(function(){alert("Hello")},3000);//setTimeout() 是属于 window 的方法，该方法用于在指定的毫秒数后调用函数或计算表达式。setTimeout(要执行的代码, 等待的毫秒数),setTimeout(JavaScript 函数, 等待的毫秒数),setTimeout() 是设定一个指定等候时间 (单位是千分之一秒, millisecond), 时间到了, 浏览器就会执行一个指定的代码.
}
</script>
</body>
</html>
```

- 另一个简单的计时

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>另一个简单的计时</title>
</head>
<head>
<script>
function timedText(){
	var a=document.getElementById('txt');
	var b1=setTimeout(function(){a.value="1 秒"},1000);
	var b2=setTimeout(function(){a.value="2 秒"},2000);
	var b3=setTimeout(function(){a.value="3 秒"},3000);
}
</script>
</head>
<body>
<form>
<input type="button" value="显示文本时间!" onclick="timedText()" />
<input type="text" id="txt" />
</form>
<p>点击上面的按钮，输出的文本将告诉你2秒，4秒，6秒已经过去了。</p>
</body>

```

- 在一个无穷循环中的计时事件

```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>在一个无穷循环中的计时事件</title> 
<script>
var c=0;
var t;
var timer_is_on=0;
function timedCount(){
	document.getElementById('txt').value=c;
	c=c+1;
	t=setTimeout("timedCount()",1000);
}
function doTimer(){
	if (!timer_is_on)
	{
		timer_is_on=1;
		timedCount();
	}
}
</script> 
</head>
<body>
<form>
<input type="button" value="开始计数!" onClick="doTimer()">
<input type="text" id="txt">
</form>
<p>单击按钮，输入框将从0开始一直计数。</p>
</body>
</html>
```

- 带有停止按钮的无穷循环中的计时事件

```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>带有停止按钮的无穷循环中的计时事件</title> 
<script>
var c=0;
var t;
var timer_is_on=0;
function timedCount(){
	document.getElementById('txt').value=c;
	c=c+1;
	t=setTimeout(function(){timedCount()},1000);
}
function doTimer(){
	if (!timer_is_on){
		timer_is_on=1;
		timedCount();
	}
}
function stopCount(){
	clearTimeout(t);//clearTimeout() 方法可取消由 setTimeout() 方法设置的 timeout。 
	timer_is_on=0;
}
</script>
</head>
<body>
<form>
<input type="button" value="开始计数!" onclick="doTimer()" />
<input type="text" id="txt" />
<input type="button" value="停止计数!" onclick="stopCount()" />
</form>
<p>
单击开始计数按钮，按下时开始计数，输入框将从0开始一直计数。单击停止计数按钮，按下时停止计数，再次点击开始计数按钮，又再次开始计数。
</p>
</body>
</html>
```

- 使用计时事件制作的钟表

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>使用计时事件制作的钟表</title>
<script>
function startTime(){
	var today=new Date();//Date 对象用于处理日期与时间，创建 Date 对象： new Date()。
	var h=today.getHours();//返回 Date 对象的小时 (0 ~ 23)。
	var m=today.getMinutes();//返回 Date 对象的分钟 (0 ~ 59)。
	var s=today.getSeconds();//返回 Date 对象的秒数 (0 ~ 59)。
    // 在小于10的数字前加一个‘0’
	m=checkTime(m);
	s=checkTime(s);
	document.getElementById('txt').innerHTML=h+":"+m+":"+s;
	t=setTimeout(function(){startTime()},500);
}
function checkTime(i){
	if (i<10){
		i="0" + i;
	}
	return i;
}
</script>
</head>
<body onload="startTime()">
<div id="txt"></div>
</body>
</html>
```

- 创建对象的实例

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>创建对象的实例</title>
</head>
<body>
<script>
person={firstname:"Bob",lastname:"Tom",age:18,eyecolor:"yellow"}
document.write(person.firstname + " is " + person.age + " years old.");
</script>
</body>
</html>
```

- 创建用于对象的模板

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>创建用于对象的模板</title>
</head>
<body>
<script>
function person(firstname,lastname,age,eyecolor){
	this.firstname=firstname;
	this.lastname=lastname;
	this.age=age;
    this.eyecolor=eyecolor;
}
myFather=new person("John","Doe",50,"blue");
document.write(myFather.firstname + " is " + myFather.age + " years old.");
</script>
</body>
</html>
```

### JavaScript 应用实例

#### javascript 幻灯片代码(含自动播放)

HTML+CSS+JavaScript 代码：


```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>轮播图</title>
    <style>
    * {box-sizing:border-box}
body {font-family: Verdana,sans-serif;}
.mySlides {display:none}
 
/* 幻灯片容器 */
.slideshow-container {
  max-width: 1000px;
  position: relative;
  margin: auto;
}
 
/* 下一张 & 上一张 按钮 */
.prev, .next {
  cursor: pointer;
  position: absolute;
  top: 50%;
  width: auto;
  margin-top: -22px;
  padding: 16px;
  color: white;
  font-weight: bold;
  font-size: 18px;
  transition: 0.6s ease;
  border-radius: 0 3px 3px 0;
}
 
/* 定位 "下一张" 按钮靠右 */
.next {
  right: 0;
  border-radius: 3px 0 0 3px;
}
 
/* On hover, add a black background color with a little bit see-through */
.prev:hover, .next:hover {
  background-color: rgba(0,0,0,0.8);
}
 
/* 标题文本 */
.text {
  color: #f2f2f2;
  font-size: 15px;
  padding: 8px 12px;
  position: absolute;
  bottom: 8px;
  width: 100%;
  text-align: center;
}
 
/* 数字文本 (1/3 等) */
.numbertext {
  color: #f2f2f2;
  font-size: 12px;
  padding: 8px 12px;
  position: absolute;
  top: 0;
}
 
/* 标记符号 */
.dot {
  cursor:pointer;
  height: 13px;
  width: 13px;
  margin: 0 2px;
  background-color: #bbb;
  border-radius: 50%;
  display: inline-block;
  transition: background-color 0.6s ease;
}
 
.active, .dot:hover {
  background-color: #717171;
}
 
/* 淡出动画 */
.fade {
  -webkit-animation-name: fade;
  -webkit-animation-duration: 1.5s;
  animation-name: fade;
  animation-duration: 1.5s;
}
 
@-webkit-keyframes fade {
  from {opacity: .4} 
  to {opacity: 1}
}
 
@keyframes fade {
  from {opacity: .4} 
  to {opacity: 1}
}</style>
	</head>
	<body>
		<div class="slideshow-container">
		  <div class="mySlides fade">
		    <div class="numbertext">1 / 3</div>
		    <img src="img1.jpg" style="width:100%">
		    <div class="text">文本 1</div>
		  </div>

		  <div class="mySlides fade">
		    <div class="numbertext">2 / 3</div>
		    <img src="img2.jpg" style="width:100%">
		    <div class="text">文本 2</div>
		  </div>

		  <div class="mySlides fade">
		    <div class="numbertext">3 / 3</div>
		    <img src="img3.jpg" style="width:100%">
		    <div class="text">文本 3</div>
		  </div>

	  <a class="prev" onclick="plusSlides(-1)">❮</a>
      <a class="next" onclick="plusSlides(1)">❯</a>
		</div>
		<br>	 
		<div style="text-align:center">
		  <span class="dot" onclick="currentSlide(1)"></span> 
		  <span class="dot" onclick="currentSlide(2)"></span> 
		  <span class="dot" onclick="currentSlide(3)"></span> 
		</div>
        <script>//幻灯片不能自动播放
        var slideIndex = 1;
showSlides(slideIndex);

function plusSlides(n) {
  showSlides(slideIndex += n);
}

function currentSlide(n) {
  showSlides(slideIndex = n);
}
 //index 属性可返回下拉列表中选项的索引位置。
 //slideIndex返回幻灯片集合中指定幻灯片的索引号。 此为只读属性。
 //length设置或返回数组元素的个数。
//showSlides函数记住口诀：3个var 两if 两for配上两数组
function showSlides(n) {
  var i;
  var slides = document.getElementsByClassName("mySlides");
  var dots = document.getElementsByClassName("dot");
  if (n > slides.length) {slideIndex = 1} 
  if (n < 1) {slideIndex = slides.length}
  for (i = 0; i < slides.length; i++) {
      slides[i].style.display = "none"; 
  }
  for (i = 0; i < dots.length; i++) {
      dots[i].className = dots[i].className.replace(" active", "");
  }
  slides[slideIndex-1].style.display = "block"; 
  dots[slideIndex-1].className += " active";
}
        </script>
        <script>//幻灯片设置为自动播放
       var slideIndex = 0;
showSlides();
 //showSlides函数口诀:三个var 两for中if  两个数组加setTimeout参数。
function showSlides() {
    var i;
    var slides = document.getElementsByClassName("mySlides");
    var dots = document.getElementsByClassName("dot");
    for (i = 0; i < slides.length; i++) {
       slides[i].style.display = "none";  
    }
    slideIndex++;
    if (slideIndex > slides.length) {slideIndex = 1}    
    for (i = 0; i < dots.length; i++) {
        dots[i].className = dots[i].className.replace(" active", "");//replace() 方法用于在字符串中用一些字符替换另一些字符，或替换一个与正则表达式匹配的子串。
    }
    slides[slideIndex-1].style.display = "block";  
    dots[slideIndex-1].className += " active";
    setTimeout(showSlides, 2000); // 切换时间为 2 秒
} 
        </script>
 </body>
</html>

```

#### 京东轮播图实例

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>轮播图</title>
    <style>
    * {box-sizing:border-box}
body {font-family: Verdana,sans-serif;}
.mySlides {display:none}
 
/* 幻灯片容器 */
.slideshow-container {
  max-width: 1000px;
  position: relative;
  margin: auto;
}
 
/* 下一张 & 上一张 按钮 */
.prev, .next {
  cursor: pointer;
  position: absolute;
  top: 50%;
  width: auto;
  margin-top: -22px;
  padding: 16px;
  color: white;
  font-weight: bold;
  font-size: 18px;
  transition: 0.6s ease;
  border-radius: 0 3px 3px 0;
}
 
/* 定位 "下一张" 按钮靠右 */
.next {
  right: 0;
  border-radius: 3px 0 0 3px;
}
 
/* On hover, add a black background color with a little bit see-through */
.prev:hover, .next:hover {
  background-color: rgba(0,0,0,0.8);
}
 
/* 标题文本 */
.text {
  color: #f2f2f2;
  font-size: 15px;
  padding: 8px 12px;
  position: absolute;
  bottom: 8px;
  width: 100%;
  text-align: center;
}
 
/* 数字文本 (1/3 等) */
.numbertext {
  color: #f2f2f2;
  font-size: 12px;
  padding: 8px 12px;
  position: absolute;
  top: 0;
}
 
/* 标记符号 */
.dot {
  cursor:pointer;
  height: 13px;
  width: 13px;
  margin: 0 2px;
  background-color: #bbb;
  border-radius: 50%;
  display: inline-block;
  transition: background-color 0.6s ease;
}
 
.active, .dot:hover {
  background-color: #717171;
}
 
/* 淡出动画 */
.fade {
  -webkit-animation-name: fade;
  -webkit-animation-duration: 1.5s;
  animation-name: fade;
  animation-duration: 1.5s;
}
 
@-webkit-keyframes fade {
  from {opacity: .4} 
  to {opacity: 1}
}
 
@keyframes fade {
  from {opacity: .4} 
  to {opacity: 1}
}</style>
	</head>
	<body>
		<div class="slideshow-container">
		  <div class="mySlides fade">
		    <div class="numbertext">1 / 3</div>
		    <img src="img1.jpg" style="width:100%">
		    <div class="text">文本 1</div>
		  </div>

		  <div class="mySlides fade">
		    <div class="numbertext">2 / 3</div>
		    <img src="img2.jpg" style="width:100%">
		    <div class="text">文本 2</div>
		  </div>

		  <div class="mySlides fade">
		    <div class="numbertext">3 / 3</div>
		    <img src="img3.jpg" style="width:100%">
		    <div class="text">文本 3</div>
		  </div>

	  <a class="prev" onclick="plusSlides(-1)">❮</a>
      <a class="next" onclick="plusSlides(0)">❯</a>
		</div>
		<br>	 
		<div style="text-align:center">
		  <span class="dot" onclick="currentSlide(1)"></span> 
		  <span class="dot" onclick="currentSlide(2)"></span> 
		  <span class="dot" onclick="currentSlide(3)"></span> 
		</div>
<script type="text/javascript">
		function plusSlides(n) {
		  showSlides(slideIndex += n);
		}
		 
		function currentSlide(n) {
		  showSlides(slideIndex = n);
		}
		  var slideIndex = 0;
		 showSlides();
		  //showSlides函数口诀:三个var 两for中if  两个数组加setTimeout参数。
		 function showSlides() {
		     var i;
		     var slides = document.getElementsByClassName("mySlides");
		     var dots = document.getElementsByClassName("dot");
		     for (i = 0; i < slides.length; i++) {
		        slides[i].style.display = "none";  
		     }
		     slideIndex++;
		     if (slideIndex > slides.length) {slideIndex = 1}    
		     for (i = 0; i < dots.length; i++) {
		         dots[i].className = dots[i].className.replace(" active", "");//replace() 方法用于在字符串中用一些字符替换另一些字符，或替换一个与正则表达式匹配的子串。
		     }
		     slides[slideIndex-1].style.display = "block";  
		     dots[slideIndex-1].className += " active";
		     setTimeout(showSlides, 10000); // 切换时间为 10 秒
		 } 
	</script>
    </body>
</html>
```

### JavaScript 对象 实例

使用内置的JavaScript对象实例。

#### String（字符串）对象

- 返回字符串的长度

```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>返回字符串的长度</title> 
</head>
<body>
<script>
var txt = "你好";
document.write(txt.length);//2
</script>
</body>
</html>
```

- 为字符串添加样式

```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>为字符串添加样式</title> 
</head>
<body>
<script>
var txt = "Hello World!";
document.write("<p>字体变大: " + txt.big() + "</p>");
document.write("<p>字体缩小: " + txt.small() + "</p>");
document.write("<p>字体加粗: " + txt.bold() + "</p>");
document.write("<p>斜体: " + txt.italics() + "</p>");
document.write("<p>固定定位: " + txt.fixed() + "</p>");
document.write("<p>加删除线: " + txt.strike() + "</p>");
document.write("<p>字体颜色: " + txt.fontcolor("green") + "</p>");
document.write("<p>字体大小: " + txt.fontsize(6) + "</p>");
document.write("<p>下标: " + txt.sub() + "</p>");
document.write("<p>上标: " + txt.sup() + "</p>");
document.write("<p>链接: " + txt.link("http://www.w3cschool.cc") + "</p>");
document.write("<p>闪动文本: " + txt.blink() + " (不能用于IE,Chrome,或者Safari)</p>");
</script>
</body>
</html>
```

- 返回字符串中指定文本首次出现的位置-indexOf()方法

```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>返回字符串中指定文本首次出现的位置-indexOf()方法</title> 
</head>
<body>
<p id="demo">单击按钮来定位指定文本首次出现的位置。</p>
<button onclick="myFunction()">按钮</button>
<script>
function myFunction(){
	var str="Hello world, welcome to the universe.";
	var n=str.indexOf("welcome");//indexOf():从0开始，数到找到位置，未找到返回-1;
	document.getElementById("demo").innerHTML=n;
}
</script>
</body>
</html>
```

- 查找字符串中特定的字符，若找到，则返回该字符-match()方法

```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>查找字符串中特定的字符，若找到，则返回该字符-match()方法</title> 
</head>
<body>
<script>
var str="Hello Bob!";
document.write(str.match("Bob") + "<br>");
document.write(str.match("bob") + "<br>");
document.write(str.match("bob!") + "<br>");
document.write(str.match("Bob!"));
</script>
</body>
</html>
```

- 替换字符串中的字符-replace()

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<title></title>
	</head>
	<body>
		<p>单击按钮将段落中的第一个 Hello 替换成 你好</p>
		<p id="demo">Hello! Hello Bob!</p>
		<button onclick="myFunction()">按钮</button>
		<script>
			function myFunction() {
				var str = document.getElementById("demo").innerHTML;
				var a = str.replace("Hello", "你好"); //replace("Hello","你好"):替换字符串中的字符，Hello将被替换成你好
				document.getElementById("demo").innerHTML = a;
			}
		</script>
	</body>
</html>
```

#### Date（日期）对象

-  使用Date()方法来返回今天的日期和时间

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>使用Date()方法来返回今天的日期和时间</title>
</head>
<body>
<script>
var d=new Date();
document.write(d);
</script>
</body>
</html>
```

- 使用getTime()计算从1970年到今天有多少毫秒

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>使用getTime()计算从1970年到今天有多少毫秒</title>
</head>
<body>
<p id="demo">单击按钮显示1970年1月1号至今的毫秒数。</p>
<button onclick="myFunction()">按钮</button>
<script>
function myFunction(){
    var d = new Date();
    var a = document.getElementById("demo");
    a.innerHTML=a.getTime();//getTime():显示1970年1月1号至今的毫秒数。
}
</script>
</body>
</html>
```

- 使用setFullYear()设置具体的日期

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>使用setFullYear()设置具体的日期</title>
</head>
<body>
<p id="demo">单击按钮显示修改后的年月日。</p>
<button onclick="myFunction()">按钮</button>
<script>
function myFunction(){
	var d = new Date();
	d.setFullYear(2020,5,1);
	var x = document.getElementById("demo");
	x.innerHTML=d;//星期，月 日 年 时间
}
</script>
<p>记住 JavaScript 月数是从0至11。10是11月。</p>
</body>
</html>
```

- 使用toUTCString()把当日的日期（根据UTC）转换为字符串

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>使用toUTCString()把当日的日期（根据UTC）转换为字符串</title>
</head>
<body>
<p id="demo">点击按钮把UTC日期和时间转换成字符串。</p>
<button onclick="myFunction()">点我</button>
<script>
function myFunction(){
	var d = new Date();
	var x = document.getElementById("demo");
	x.innerHTML=d.toUTCString();//toUTCString():把UTC日期和时间转换成字符串
}
</script>
</body>
</html>
```

- 使用getDay()来显示星期，而不仅仅是数字

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>使用getDay()来显示星期，而不仅仅是数字</title>
</head>
<body>
<p id="demo">单击按钮显示今天周几</p>
<button onclick="myFunction()">按钮</button>
<script>
function myFunction(){
	var d = new Date();
	var weekday=new Array(7);
	weekday[0]="周日";
	weekday[1]="周一";
	weekday[2]="周二";
	weekday[3]="周三";
	weekday[4]="周四";
	weekday[5]="周五";
	weekday[6]="周六";
	var a = document.getElementById("demo");
	a.innerHTML=weekday[d.getDay()];//getDay():显示星期
}
</script>
</body>
</html>
```

- 显示一个钟表

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>显示一个钟表</title>
<script>
function startTime(){
	var today=new Date();
	var h=today.getHours();
	var m=today.getMinutes();
	var s=today.getSeconds();// 在小于10的数字前加一个‘0’
	m=checkTime(m);
	s=checkTime(s);
	document.getElementById('txt').innerHTML=h+":"+m+":"+s;
	t=setTimeout(function(){startTime()},500);
}
function checkTime(i){
	if (i<10){
		i="0" + i;
	}
	return i;
}
</script>
</head>
<body onload="startTime()">
<div id="txt"></div>
</body>
</html>
```

#### Array(数组)对象

- 创建数组

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>创建数组</title>
</head>
<body>
<script>
var i;
var myname= new Array();
myname[0] = "Bob";
myname[1] = "Tom";
myname[2] = "lisha";
for (i=0;i<myname.length;i++){//length:设置或返回数组元素的个数。
	document.write(myname[i] + "<br />");
}
</script>
</body>
</html>
```

- 合并两个数组-concat()

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>合并两个数组-concat()</title>
</head>
<body>
<script>
var hege = ["Cecilie", "Lone"];
var stale = ["Emil", "Tobias", "Linus"];
var children = hege.concat(stale);//concat():合并两个数组
document.write(children);
//var  a=["我","是"];
//var  b=["小","朋","友"];
//var  c=a.concat(b);
//document.write(c);
</script>
</body>
</html>
```

- 合并三个数组-concat()

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>合并三个数组-concat()</title>
</head>
<body>
<script>
var parents = ["Jani", "Tove"];
var brothers = ["Stale", "Kai Jim", "Borge"];
var children = ["Cecilie", "Lone"];
var family = parents.concat(brothers, children);
document.write(family);
</script>
</body>
</html>
```

- 用数组的元素组成字符串-join()

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>用数组的元素组成字符串-join()</title>
</head>
<body>
<p id="demo">点击按钮将数组作为字符串输出。</p>
<button onclick="myFunction()">按钮</button>
<script>
function myFunction(){
	var fruits = ["Banana", "Orange", "Apple", "Mango"];
	var x=document.getElementById("demo");
	x.innerHTML=fruits.join();//join():将数组作为字符串输出
}
</script>
</body>
</html>
```

- 删除数组的最后一个元素-pop()

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>删除数组的最后一个元素-pop()</title>
</head>
<body>
<p id="demo">单击按钮删除数组的最后一个元素。</p>
<button onclick="myFunction()">按钮</button>
<script>
var fruits = ["Banana", "Orange", "Apple", "Mango"];
function myFunction(){
	fruits.pop();//pop():删除数组的最后一个元素
	var x=document.getElementById("demo");
	x.innerHTML=fruits;
}
</script>
</body>
</html>
```

- 数组的末尾添加新的元素-push()

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>数组的末尾添加新的元素-push()</title>
</head>
<body>
<p id="demo">单击按钮给数组添加新的元素。</p>
<button onclick="myFunction()">按钮</button>
<script>
var fruits = ["Banana", "Orange", "Apple", "Mango"];
function myFunction(){
	fruits.push("")
	var x=document.getElementById("demo");
	x.innerHTML=fruits;
}
</script>
</body>
</html>
```

- 反转一个数组中的元素的顺序-reverse()

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>反转一个数组中的元素的顺序-reverse()/title>
</head>
<body>
<p id="demo">单击按钮将数组反转排序。</p>
<button onclick="myFunction()">按钮</button>
<script>
var fruits = ["Banana", "Orange", "Apple", "Mango"];
function myFunction(){
	fruits.reverse();//reverse():反转一个数组中的元素的顺序
	var x=document.getElementById("demo");
	x.innerHTML=fruits;
}
</script>
</body>
</html>
```

- 删除数组的第一个元素-shift()

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>删除数组的第一个元素-shift()</title>
</head>
<body>
<p id="demo">单击按钮删除数组的第一个元素。</p>
<p id="demo2"></p>
<button onclick="myFunction()">按钮</button>
<script>
var fruits = ["Banana", "Orange", "Apple", "Mango"];
function myFunction(){
	var delell = fruits.shift();//shift():删除数组的第一个元素。
	var x=document.getElementById("demo");
	x.innerHTML= '删除后数组为：' +  fruits;
	document.getElementById("demo2").innerHTML= '删除的元素是：' +  delell;
}
</script>
</body>
</html>
```

- 从一个数组中的选择元素-slice()

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>从一个数组中的选择元素-slice()</title>
</head>
<body>
<p id="demo">点击按钮截取数组下标 1 到 2 的元素。</p>
<button onclick="myFunction()">按钮</button>
<script>
function myFunction(){
	var fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
	var citrus = fruits.slice(1,3);//slice():截取数组下标 1 到 2 的元素
	var x=document.getElementById("demo");
	x.innerHTML=citrus;
}
</script>
</body>
</html>
```

- 数组排序（按字母顺序升序）-sort()

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>数组排序（按字母顺序升序）-sort()</title>
</head>
<body>
<p id="demo">单击按钮升序排列数组。</p>
<button onclick="myFunction()">按钮</button>
<script>
function myFunction(){
	var fruits = ["Banana", "Orange", "Apple", "Mango"];
	fruits.sort();//sort():按字母顺序，升序排列数组
	var x=document.getElementById("demo");
	x.innerHTML=fruits;
}
</script>
</body>
</html>
```

- 数组排序（按数字顺序升序）-sort()

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>数组排序（按数字顺序升序）-sort()</title>
</head>
<body>
<p id="demo">单击按钮升序排列数组。</p>
<button onclick="myFunction()">按钮</button>
<script>
function myFunction(){
	var points = [40,100,1,5,25,10];
	points.sort(function(a,b){return a-b});//a-b是升序，b-a是降序
	var x=document.getElementById("demo");
	x.innerHTML=points;
}
</script>
</body>
</html>
```

- 数组排序（按数字顺序降序）-sort()

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>数组排序（按数字顺序降序）-sort()</title>
</head>
<body>
<p id="demo">单击按钮降序排列数组。</p>
<button onclick="myFunction()">按钮</button>
<script>
function myFunction(){
	var points = [40,100,1,5,25,10];
	points.sort(function(a,b){return b-a});//a-b是升序，b-a是降序
	var x=document.getElementById("demo");
	x.innerHTML=points;
}
</script>
</body>
</html>
```

- 在数组的第2位置添加一个元素-splice()

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>在数组的第2位置添加一个元素-splice()</title>
</head>
<body>
<p id="demo">点击按钮向数组添加元素。</p>
<button onclick="myFunction()">按钮</button>
<script>
function myFunction(){
    var fruits = ["Banana", "Orange", "Apple", "Mango"];
    fruits.splice(2,0,"Lemon","Kiwi");//splice():在数组的第几个位置添加一个元素
    var x=document.getElementById("demo");
    x.innerHTML=fruits;
}
</script>
</body>
</html>
```

- 转换数组到字符串-toString()

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>转换数组到字符串-toString()</title>
</head>
<body>
<p id="demo">点击按钮将数组转为字符串并返回。</p>
<button onclick="myFunction()">按钮</button>
<script>
function myFunction(){
	var fruits = ["Banana", "Orange", "Apple", "Mango"];
	var str = fruits.toString();//toString():将数组转为字符串并返回
	var x=document.getElementById("demo");
	x.innerHTML= str;
}
</script>
</body>
</html>
```

- 在数组的开头添加新元素-unshift()

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>在数组的开头添加新元素-unshift()</title>
</head>
<body>
<p id="demo">单击按钮在数组中插入元素。</p>
<button onclick="myFunction()">按钮</button>
<script>
function myFunction(){
	var fruits = ["Banana", "Orange", "Apple", "Mango"];
	fruits.unshift("Lemon","Pineapple");//unshift():数组的开头添加新元素
	var x=document.getElementById("demo");
	x.innerHTML=fruits;
}
</script>
<p><b>注意:</b> unshift()方法不能用于 Internet Explorer 8 之前的版本，插入的值将被返回成<em> undefined </em>。</p>
</body>
</html>
```

#### Boolean(布尔)对象

- 检查逻辑值

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>检查逻辑值</title>
</head>
<body>
<script>
var b1=new Boolean(0);
var b2=new Boolean(1);
var b3=new Boolean("");
var b4=new Boolean(null);
var b5=new Boolean(NaN);
var b6=new Boolean("false");
document.write("0 为布尔值 "+ b1 +"<br>");
document.write("1 为布尔值 "+ b2 +"<br>");
document.write("空字符串是布尔值 "+ b3 + "<br>");
document.write("null 是布尔值 "+ b4+ "<br>");
document.write("NaN 是布尔值 "+ b5 +"<br>");
document.write("字符串'false' 是布尔值"+ b6 +"<br>");
</script>
</body>
</html>
```

#### Math（算数）对象

- 使用round()对数字进行舍入

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>使用round()对数字进行舍入</title>
</head>
<body>
<p id="demo">单击按钮舍入与“2.5”最接近的整数</p>
<button onclick="myFunction()">按钮</button>
<script>
function myFunction(){
	document.getElementById("demo").innerHTML=Math.round(2.5);//round():对数字进行舍入，2.4是2,2.5是3，四舍五入法
}
</script>
</body>
</html>
```

- 使用random()来返回0到1之间的随机数

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>使用random()来返回0到1之间的随机数</title>
</head>
<body>
<p id="demo">点击按钮显示一个随机数</p>
<button onclick="myFunction()">按钮</button>
<script>
function myFunction(){
    document.getElementById("demo").innerHTML=Math.random();//random():返回0到1之间的随机数
}
</script>
</body>
</html>
```

- 使用max()来返回两个给定的数中的较大的数

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>使用max()来返回两个给定的数中的较大的数</title>
</head>
<body>
<p id="demo">单击按钮返回5到10之间的最大值。</p>
<button onclick="myFunction()">按钮</button>
<script>
function myFunction(){
    document.getElementById("demo").innerHTML=Math.max(1,2);//max():返回两个给定的数中的较大的数,就是返回两个数中其中一个较大的值。
}
</script>
</body>
</html>
```

- 使用min()来返回两个给定的数中的较小的数

```html
!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>使用min()来返回两个给定的数中的较小的数</title>
</head>
<body>
<p id="demo">单击按钮返回5到10之间最小的值。</p>
<button onclick="myFunction()">按钮</button>
<script>
function myFunction(){
	document.getElementById("demo").innerHTML=Math.min(1,2);
}
</script>
</body>
</html>
```

- 摄氏度与华氏转换

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>摄氏度与华氏转换</title>
</head>
<head>
<script>
function convert(degree){
	if (degree=="C"){
		F=document.getElementById("c").value * 9 / 5 + 32;
		document.getElementById("f").value=Math.round(F);
	}
	else{
		C=(document.getElementById("f").value -32) * 5 / 9;
		document.getElementById("c").value=Math.round(C);
	}
}
</script>
</head>
<body>
<p><b>在下面输入框中插入一个数值：</b></p>
<form>
<input id="c" name="c" onkeyup="convert('C')"> 摄氏度<br><!--onkeyup 事件会在键盘按键被松开时发生。-->
等于<br> 
<input id="f" name="f" onkeyup="convert('F')"> 华氏度 
</form>
<p>注意使用<b>Math.round()</b> 方法返回的结果是一个整数。</p>
</body>
</html>
```

#### 一般

- 通过对象元素使用for-in语句

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>通过对象元素使用for-in语句</title>
</head>
<body>	
<p>点击下面的按钮，循环遍历对象 "person" 的属性。</p>
<button onclick="myFunction()">按钮</button>
<p id="demo"></p>
<script>
function myFunction(){
	var x;
	var txt="";
	var person={fname:"Bill",lname:"Gates",age:56}; 
	for (x in person){
		txt=txt + person[x];
	}
	document.getElementById("demo").innerHTML=txt;
}
</script>	
</body>
</html>
```

### JavaScript Browser 对象 实例

使用JavaScript来访问和控制浏览器对象实例。

#### Window 对象

- 弹出一个警告框

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<script>
function myFunction(){
	alert("你好，我是一个警告框！");
}
</script>
</head>
<body>
<input type="button" onclick="myFunction()" value="显示警告框" />
</body>
</html>
```

- 弹出一个带折行的警告框

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>弹出一个带折行的警告框</title>
</head>
<body>
<p>点击按钮在弹窗总使用换行。</p>
<button onclick="myFunction()">按钮</button>
<script>
function myFunction(){
	alert("Hello\nHow are you?");//\n:表示换行
}
</script>
</body>
</html>
```

- 弹出一个确认框，并提醒访客点击的内容

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>弹出一个确认框，并提醒访客点击的内容</title>
</head>
<body>
<p>点击按钮，显示确认框。</p>
<button onclick="myFunction()">按钮</button>
<p id="demo"></p>
<script>
function myFunction(){
    var q;
    var b=("你是不是boy");//()；确认消息对话框。用于允许用户做选择的动作。弹出的对话框中包含一确定按钮和一取消按钮。
    if (b==true){
        q="yes";
    }
    else{
        q="no";
    }
    document.getElementById("demo").innerHTML=q;
}
</script>
</body>
</html>
```

- 弹出一个提示框

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>弹出一个提示框</title>
</head>
<body>
<p>点击按钮查看输入的对话框。</p>
<button onclick="myFunction()">按钮</button>
<p id="demo"></p>
<script>
function myFunction(){
    var a;
    var car=prompt("请输入你的车名","");//prompt() 方法用于显示可提示用户进行输入的对话框。prompt(sometext,defaultText) sometext:要在对话框中显示的纯文本（而不是 HTML 格式的文本）。
 //defaultText:默认的输入文本。
    if (car!=null && car!=""){
        a="你的车名叫 " + car + "! 非常好听的车名！";
        document.getElementById("demo").innerHTML=a;
    }
}
</script>
</body>
</html>
```

- 点击一个按钮时，打开一个新窗口

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>点击一个按钮时，打开一个新窗口</title>
<script>
function open_win() {
	window.open("http://www.baidu.com");
}
</script>
</head>
<body>	
<form>
<input type="button" value="跳转百度的页面" onclick="open_win()">
</form>
</body>
</html>
```

- 打开一个新窗口，并控制其外观

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
<script>
function open_win(){
	window.open("http://www.runoob.com","_blank","toolbar=yes, location=yes, directories=no, status=no, menubar=yes, scrollbars=yes, resizable=no, copyhistory=yes, width=400, height=400");
}
</script>
</head>
<body>
	
<form>
<input type="button" value="打开窗口" onclick="open_win()">
</form>
	
</body>
</html>
```

- 打开多个新窗口

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>打开多个新窗口</title>
<script>
function open_win() {
	window.open("https://www.baidu.com/");
	window.open("http://www.sina.com.cn/");
}
</script>
</head>
<body>
<form>
<input type="button" value="打开窗口" onclick="open_win()">
</form>
</body>
</html>
```

- 确保新的窗口没有获得焦点

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>打开多个新窗口</title>
<script>
function open_win() {
	window.open("https://www.baidu.com/");
	window.open("http://www.sina.com.cn/");
}
</script>
</head>
<body>
<form>
<input type="button" value="打开窗口" onclick="open_win()">
</form>
</body>
</html>
```

- 确保新的窗口获得焦点

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>确保新的窗口获得焦点</title>
<script>
function openWin(){
    myWindow=window.open('','','width=200,height=200');//width和height是打开新窗口的高度和宽度
    myWindow.document.write("<p>这是'我的窗口'</p>");
    myWindow.focus();
}
</script>
</head>
<body>
<input type="button" value="打开窗口" onclick="openWin()" />
</body>
</html>
```

- 关闭新的窗口

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>关闭新的窗口</title>
<script>
function openWin(){
	myWindow=window.open("","","width=200,height=100");
	myWindow.document.write("<p>这是'我的窗口'</p>");
}
function closeWin(){
	myWindow.close();
}
</script>
</head>
<body>
<input type="button" value="打开我的窗口" onclick="openWin()" />
<input type="button" value="关闭我的窗口" onclick="closeWin()" />
</body>
</html>
```

- 检查新的窗口是否已关闭

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>检查新的窗口是否已关闭</title>
<script>
var myWindow;
function openWin(){
    myWindow=window.open("","","width=400,height=200");
}
function closeWin(){
    if (myWindow){
        myWindow.close();
    }
}
function checkWin(){
    if (!myWindow){
        document.getElementById("msg").innerHTML="我的窗口没有被打开!";
    }
    else{
        if (myWindow.closed){
            document.getElementById("msg").innerHTML="我的窗口被关闭!";
        }
        else{
            document.getElementById("msg").innerHTML="我的窗口没有被关闭!";
        }
    }   
}
</script>
</head>
<body>
<input type="button" value="打开我的窗口" onclick="openWin()" />
<input type="button" value="关闭我的窗口" onclick="closeWin()" />
<br><br>
<input type="button" value="我的窗口被关闭了吗?" onclick="checkWin()" />
<br><br>
<div id="msg"></div>  
</body>
</html>
```

- 返回新窗口的名字

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回新窗口的名字</title>
<script>
var myWindow;
function openWin(){
    myWindow=window.open('','MsgWindow','width=200,height=100');//Msgwindow是名字
    myWindow.document.write("<p>窗口名称为: " + myWindow.name + "</p>");
}
</script>
</head>
<body>
<input type="button" value="打开我的窗口" onclick="openWin()" />
</body>
</html>
```

- 传输一些文本到源（父）窗口

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>传输一些文本到源（父）窗口</title>
<script>
function openWin(){
    myWindow=window.open('','','width=200,height=100');
    myWindow.document.write("<p>这是我的窗口</p>");
    myWindow.focus();
    myWindow.opener.document.write("<p>这个是源窗口!</p>");
}
</script>
</head>
<body>
<input type="button" value="打开我的窗口" onclick="openWin()" />
</body>
</html>
```

- 相对于当前位置移动新窗口

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>相对于当前位置移动新窗口</title>
<script>
function openWin(){
	myWindow=window.open('','','width=200,height=100');
	myWindow.document.write("<p>这个窗口宽为200，高为100</p>");
}
function moveWin(){
	myWindow.moveBy(250,250);//moveBy() 方法可相对窗口的当前坐标把它移动指定的像素。
	myWindow.focus();
}
</script>
</head>
<body>
<input type="button" value="打开我的窗口" onclick="openWin()" />
<br><br>
<input type="button" value="移动我的窗口" onclick="moveWin()" />
</body>
</html>
```

- 移动新窗口到指定位置

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>移动新窗口到指定位置</title>
<script>
function openWin(){
	myWindow=window.open('','','width=200,height=100');
	myWindow.document.write("<p>这是我的窗口</p>");
}
function moveWin(){
	myWindow.moveTo(0,0);//moveTO():移动新窗口到指定位置,(0,0)表示回到原处
	myWindow.focus();
}
</script>
</head>
<body>
<input type="button" value="打开窗口" onclick="openWin()" />
<br><br>
<input type="button" value="移动窗口" onclick="moveWin()" />
</body>
</html>
```

- 打印当前页面

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>打印当前页面</title>
<script>
function printpage(){
	window.print();
}
</script>
</head>
<body> 
<input type="button" value="打印页面" onclick="printpage()" />
</body>
</html>
```

- 用像素指定窗口大小

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>用像素指定窗口大小</title>
<script>
function resizeWindow(){
	top.resizeBy(100,100);//窗口没有变化
}
</script>
</head>
<body>
<form>
<input type="button" onclick="resizeWindow()" value="调整窗口">
</form>
<p><b>注意：</b>我们使用了 <b>top</b> 元素而不是<b>window</b>元素, 因为我们使用<b>frames</b>。如果你不使用<b>frames</b>，使用<b>window</b>元素来代替。</p>
</body>
</html>
```

- 指定窗口大小

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>指定窗口大小</title>
<script>
var w;
function openwindow(){
	w=window.open('','', 'width=100,height=100');
	w.focus();
}
function myFunction(){
	w.resizeTo(500,500);//调整窗口大小
	w.focus();
}
</script>
</head>
<body>
<button onclick="openwindow()">创建窗口</button>
<button onclick="myFunction()">调整窗口</button>
</body>
</html>
```

- 由指定的像素数滚动内

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>由指定的像素数滚动内容</title>
<script>
function scrollWindow(){
	window.scrollBy(100,100);//scrollBy() 方法可把内容滚动指定的像素数。注意： 要使此方法工作 window 滚动条的可见属性必须设置为true！
}
</script>
</head>
<body>

<input type="button" onclick="scrollWindow()" value="滚动条" />
<p>你好 你好你好你好你好你好你好你好你好</p>
<br>
<br>
<br>
<br>
<br>
<p>你好你好你好你好你好你好你好你好你好你好</p>
<br>
<br>
<br>
<br>
<br>
<p>你好你好你好你好你好你好你好你好你好 </p>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<p>你好你好你好你好你好你好你好你好你好你好</p>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<p>滚动 滚动 滚动 滚动 滚动 滚动 滚动 滚动 滚动 </p>
<br>
<br>
<br>
<br>
<br>
<br>
<p>你好你好你好你好你好你好你好你好你好你好你好 </p>
<br>
<br>
<br>
<br>
<br>
<p>你好你好你好你好你好你好你好你好你好你好你好</p>
<br>
<br>
<br>
<br>
<p>你好你好你好你好你好你好你好你好你好你好你好</p>
<br>
<br>
<br>
</body>
</html>
```

- 滚动到指定内容处

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>滚动到指定内容处</title>
<script>
function scrollWindow(){
    window.scrollTo(100,500);
}
</script>
</head>
<body>
<input type="button" onclick="scrollWindow()" value="滚动条" />
    <p>你好 你好你好你好你好你好你好你好你好</p>
<br>
<br>
<br>
<br>
<br>
<p>你好你好你好你好你好你好你好你好你好你好</p>
<br>
<br>
<br>
<br>
<br>
<p>你好你好你好你好你好你好你好你好你好 </p>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<p>你好你好你好你好你好你好你好你好你好你好</p>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<p>滚动 滚动 滚动 滚动 滚动 滚动 滚动 滚动 滚动 </p>
<br>
<br>
<br>
<br>
<br>
<br>
<p>你好你好你好你好你好你好你好你好你好你好你好 </p>
<br>
<br>
<br>
<br>
<br>
<p>你好你好你好你好你好你好你好你好你好你好你好</p>
<br>
<br>
<br>
<br>
<p>你好你好你好你好你好你好你好你好你好你好你好</p>
<br>
<br>
<br>
```

- 一个简单的时钟

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>一个简单的时钟</title>
</head>
<head>
<script>
function timedText(){
	var x=document.getElementById('txt');
	var t1=setTimeout(function(){x.value="1 秒"},1000);
	var t2=setTimeout(function(){x.value="2 秒"},2000);
	var t3=setTimeout(function(){x.value="3 秒"},3000);
}
</script>
</head>
<body>
	
<form>
<input type="button" value="显示文本时间!" onclick="timedText()" />
<input type="text" id="txt" />
</form>
<p>点击上面的按钮，输出的文本将告诉你2秒，4秒，6秒已经过去了。</p>
</body>
</html>
```

- 用setTimeout()和clearTimeout()设置和停止定时器

```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>用setTimeout()和clearTimeout()设置和停止定时器</title> 
<script>
var c=0;
var t;
var timer_is_on=0;
function timedCount(){
    document.getElementById('txt').value=c;
    c=c+1;
    t=setTimeout(function(){timedCount()},1000);
}
function doTimer(){
    if (!timer_is_on){
        timer_is_on=1;
        timedCount();
    }
}
function stopCount(){
    clearTimeout(t);
    timer_is_on=0;
}
</script>
</head>
<body>
    
<form>
<input type="button" value="开始计数!" onclick="doTimer()" />
<input type="text" id="txt" />
<input type="button" value="停止计数!" onclick="stopCount()" />
</form>
<p>
单击开始计数按钮，按下时开始计数，输入框将从0开始一直计数。单击停止计数按钮，按下时停止计数，再次点击开始计数按钮，又再次开始计数。
</p>
    </body>  
</html>
```

- 用setlnterval()和clearlnterval()设置和停止定时器

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>用setlnterval()和clearlnterval()设置和停止定时器</title>
</head>
<body>
<p>点击按钮，等待 1 秒会弹出 "你好"。</p>
<p>在弹出的对话框中点击 “确定”, 1 秒后会继续弹出。如此循环下去...</p>
<button onclick="myFunction()">点我</button>
<script>
function myFunction() {
    setInterval(function(){ alert("你好"); }, 1000);
}
</script>
    <script type="text/javascript">
        //开始和停止
		var a;
		var  timer_is_on=0;
		function myFunction(){
			a=setInterval(function(){alert("你好")},3000);
		}
		function doTimer(){
			if(!timer_is_on){
				timer_is_on=1;
				myFunction();
			}
		}
		function Stop(){
			clearInterval(a);
			timer_is_on=0;
		}
	</script>
<button onclick="myFunction()">开始</button>	
<button onclick="Stop()">结束</button>
</body>
</html>
```

#### Navigator对象

- 访问者的浏览器的详细

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8">
  <title>访问者的浏览器的详细</title>
  </head>
  <body>
  <div id="example"></div>
  <script>
  txt = "<p>浏览器代号: " + navigator.appCodeName + "</p>";//Mozilla
      
  txt+= "<p>浏览器名称: " + navigator.appName + "</p>";//Netscape
      
  txt+= "<p>浏览器版本: " + navigator.appVersion + "</p>";//5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.132 Safari/537.36
      
  txt+= "<p>启用Cookies: " + navigator.cookieEnabled + "</p>";//true
      
  txt+= "<p>硬件平台: " + navigator.platform + "</p>";//Win32
      
  txt+= "<p>用户代理: " + navigator.userAgent + "</p>";//Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.132 Safari/537.36
      
  ```

txt+= "<p>用户代理语言: " + navigator.systemLanguage + "</p>";//undefined
  document.getElementById("example").innerHTML=txt;
  </script>
  </body>
  </html>
  ```
  

#### Screen对象

- 访问者的屏幕的详细

​```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>访问者的屏幕的详细</title>
</head>
<body>
<h3>你的屏幕:</h3>
<script>
document.write("总宽度/高度: ");
document.write(screen.width + "*" + screen.height);
document.write("<br>");
document.write("可以宽度/高度: ");
document.write(screen.availWidth + "*" + screen.availHeight);
document.write("<br>");
document.write("颜色深度: ");
document.write(screen.colorDepth);
document.write("<br>");
document.write("颜色分辨率: ");
document.write(screen.pixelDepth);
</script>
</body>
</html>
  ```

#### History对象

- 返回一个url的历史清单

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回一个url的历史清单</title>
</head>
<body>
<script>
document.write("历史列表中URL的数量： " + history.length);
</script>
</body>
</html>
```

- 创建一个后退按钮

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>创建一个后退按钮</title>
<script>
function goBack(){
	window.history.back()
}
</script>
</head>
<body>

<input type="button" value="返回" onclick="goBack()">

<p>注意,点击后退按钮在这里不会导致任何行动,因为以前的历史列表中没有该URL</p>

</body>
</html>
```

- 创建一个前进按钮

```html
<!DOCTYPE html>
<html>
<head>
<script>
function goForward(){
	window.history.forward()
}
</script>
</head>
<body>
<input type="button" value="前进" onclick="goForward()">
<p>注意,点击这里的前进按钮不会导致任何行动,因为历史列表中没有下一个URL。</p>
</body>
</html>
```

- 从url转的历史清单转到指定的url

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>从url转的历史清单转到指定的url</title>
<script>
function goBack(){
	window.history.go(-2)
}
</script>
</head>
<body>
<input type="button" value="后退2页" onclick="goBack()">
    <p>注意,点击“后退2页”按钮将不会导致任何行动,因为以前的历史列表中没有URL。</p>
</body>
</html>
```

#### Location对象

- 返回主机名和当前url的端口号

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回主机名和当前url的端口号</title>
</head>
<body>
<script>
document.write(location.host);
</script>
</body>
</html>
```

- 返回当前页面的整个URL

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回当前页面的整个URL</title>
</head>
<body>	
<script>
document.write(location.href);
</script>
</body>
</html>
```

- 返回当前url的路径名

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回当前url的路径名</title>
</head>
<body>
<script>
document.write(location.pathname);
</script>
</body>
</html>
```

- 返回当前URL的协议部分

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回当前URL的协议部分</title>
</head>
<body>
<script>
document.write(location.protocol);
</script>
</body>
</html>
```

- 加载个新文档

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>加载个新文档</title>
<script>
function newDoc(){
    window.location.assign("http://www.baidu.com")
}
</script>
</head>
<body>
<input type="button" value="载入新文档" onclick="newDoc()">
</body>
</html>
```

- 重新载入当前文档

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>重新载入当前文档</title>
<script>
function reloadPage(){
  location.reload()
}
</script>
</head>
<body>
<input type="button" value="重新加载页面" onclick="reloadPage()">
</body>
</html>
```

- 替代当前文档

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>替代当前文档</title>
<script>
function replaceDoc(){
    window.location.replace("https://www.baidu.com")
}
</script>
</head>
<body>
<input type="button" value="载入新文档替换当前页面" onclick="replaceDoc()">
</body>
</html>
```

- 跳出框架

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>跳出框架</title>
<script>
function breakout(){
	if (window.top!=window.self) {
		window.top.location="index62.html";
	}
}
</script>
</head>
<body>
<input type="button" onclick="breakout()" value="跳出框架!">
</body>
</html>
```

### JavaScript 对象 实例

使用内置JavaScript的对象实例。

#### Document 对象

- 使用document write()输出文本

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>使用document write()输出文本</title>
</head>
<body>
<script>
document.write("你好");
</script>
</body>
</html>
```

- 使用document write()输出HTML

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>使用document write()输出HTML</title>
</head>
<body>
<script>
document.write("<h2>你好</h2>");
</script>
</body>
</html>
```

- 返回文档中锚的数目

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回文档中锚的数目</title>
</head>
<body>
<a name="null">空</a><br>
<a name="color">颜色</a><br>
<a name="car">车</a><br>
<a  name="baidu" href="https://www.baidu.com">百度</a>
<p>锚的数量:
<script>
document.write(document.anchors.length);//返回锚的数目:4
</script></p>
</body>
</html>
```

- 返回文档中第二个锚的innerHTML

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回文档中第二个锚的innerHTML</title>
</head>
<body>
<a name="name">Tom</a><br>
<a name="cars">BWm</a><br>
<a name="color">bule</a>
<p>文档中第二个锚:
<script>
document.write(document.anchors[1].innerHTML);//BWm
</script>
</p>
</body>
</html>
```

- 返回文档中表单的数目

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回文档中表单的数目</title>
</head>
<body>
<form name="Form1"></form>
<form name="Form2"></form>
<form name="Form3"></form>
<p>表单数目:
<script>
document.write(document.forms.length);//3
</script></p>
</body>
</html>
```

- 返回文档中第一个表单的名字

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回文档中第一个表单的名字</title>
</head>
<body>
<form name="Form1"></form>
<form name="Form2"></form>
<form></form>
<p>第一个表单名称:
<script>
document.write(document.forms[0].name);
</script></p>
</body>
</html>
```

- 返回文档中的图像数

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回文档中的图像数</title>
</head>
<body>
<img border="0" src="图像路径" width="150" height="113">
<img border="0" src="图像路径" width="152" height="128">
<p>图像数目:
<script>
document.write(document.images.length);//注意image要有s
</script></p>
</body>
</html>
```

- 返回文档中的一个图像的ID

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回文档中的一个图像的ID</title>
</head>
<body>
<img id="img1" border="0" src="图像路径" width="150" height="113">
<img id="img2" border="0" src="图像路径" width="152" height="128">
<p>第一个图像的ID：
<script>
document.write(document.images[0].id);//img1
</script></p>
</body>
</html>
```

- 返回文档中的链接数

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回文档中的链接数</title>
</head>
<body>
<img src="../images/bg.png"  width="990px" height="480" alt="bg" usemap="#bgmap">
<map name="bgmap">
<area target="_blank" shape="rect" coords="82,49,504,145" href ="https://www.baidu.com" alt="百度"  />
<area target="_blank" shape="rect" coords="112,153,540,395" href ="https://www.jd.com" alt="京东" />
<area target="_blank" shape="circle" coords="770,187,120" href="https://www.sina.com" alt="新浪">
</map>
<p><a href="https://www.w3school.com.cn">w3school</a></p>
<p>链接数目：
<script type="text/javascript">
document.write(document.links.length);
</script>		
</p>
</body>
</html>
```

- 返回文档中的第一个链接的ID

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回文档中的第一个链接的ID</title>
</head>
<body>
<img src="../images/bg.png"  width="990px" height="480" alt="bg" usemap="#bgmap">
<map name="bgmap">
<area id="baidu" target="_blank" shape="rect" coords="82,49,504,145" href ="https://www.baidu.com" alt="百度"  />
<area id="jd" target="_blank" shape="rect" coords="112,153,540,395" href ="https://www.jd.com" alt="京东" />
<area id="sina" target="_blank" shape="circle" coords="770,187,120" href="https://www.sina.com" alt="新浪">
</map>
<p><a href="https://www.w3school.com.cn">w3school</a></p>
<p>链接数目：
<script type="text/javascript">
document.write(document.links[0].id);
</script>		
</p>
</body>
</html>
```

- 返回文档中所有cookies的名称/值对

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回文档中所有cookies的名称/值对</title>
</head>
<body>
与此文档相关的Cookies: 
<script>
document.write(document.cookie);
</script>
</body>
</html>
```

- 返回加载的文档的服务器域名

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回加载的文档的服务器域名</title>
</head>
<body>
<script>
document.write(document.domain);//加载这个文件的域名
</script>
</body>
</html>
```

- 返回文档的最后一次修改时间

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回文档的最后一次修改时间</title>
</head>
<body>
文档最后修改:
<script>
document.write(document.lastModified);
</script>
</body>
</html>
```

- 返回加载的当前文档的URL

```html
!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回加载的当前文档的URL</title>
</head>
<body>
本文档的引用地址:
<script>
document.write(document.referrer);
</script>
</body>
</html>
```

- 返回文档的标题

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回文档的标题</title>
</head>
<body>
文档的标题为: 
<script>
document.write(document.title);//返回文档的标题
</script>
</body>
</html>
```

- 返回文档的完整的URL

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回文档的完整的URL</title>
</head>
<body>
文档的完整的URL: 
<script>
document.write(document.URL);
</script>
</body>
</html>
```

- 打开输出流，向流中输入文本

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>打开输出流，向流中输入文本</title>
<script>
function createDoc(){
	var doc=document.open("text/html","replace");
	var txt="<!DOCTYPE html><html><body>有BUG</body></html>";
	doc.write(txt);
	doc.close();
}
</script>
</head>
<body>
<input type="button" value="新文档" onclick="createDoc()">
</body>
</html>
```

- write()和writeln()的不同

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>write()和writeln()的不同</title>
</head>
<body>
<p>注意write()方法不会在每个语句后面新增一行：</p>
<pre>
<script>
//简单理解，write和writeln区别就是一个不新增一行，一个新增一行
document.write("Hello ");
document.write("Hello");
</script>
</pre>
<p>注意writeln()方法在每个语句后面新增一行：</p>
<pre>
<script>
document.writeln("Hello ");
document.writeln("Hello");
</script>
</pre>
</body>
</html>
```

- 用指定的ID弹出一个元素的innerHTML

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>用指定的ID弹出一个元素的innerHTML</title>
</head>
<head>
<script>
function getValue(){
  var a=document.getElementById("myHeader");
  alert(a.innerHTML);
}
</script>
</head>
<body>
<h1 id="myHeader" onclick="getValue()">你好</h1>
</body>
</html>
```

- 用指定的Name弹出元素的数量

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>用指定的Name弹出元素的数量</title>
<script>
function getElements(){
	var a=document.getElementsByName("a");
	alert(a.length);
}
</script>
</head>
<body>
cat:
<input name="a" type="radio" value="cat">
dog:
<input name="a" type="radio" value="dog">
<input type="button" onclick="getElements()" value="多少名称为a的元素">
</body>
</html>
```

- 用指定的tagname弹出元素的数量

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>用指定的tagname弹出元素的数量</title>
<!--案例1-->
<script>
function getElements(){
  var a=document.getElementsByTagName("input");
  alert(a.length);
}
</script>
</head>
<body>
<input type="text" size="20"><br>
<input type="text" size="20"><br>
<input type="text" size="20"><br><br>
<input type="button" onclick="getElements()" value="多少input元素?">
 <!--案例2-->
<script type="text/javascript">
			function getElements(){
				var a=document.getElementsByTagName('p');
				alert(a.length);
			}
</script>
<p>1</p>
<p>2</p>
<p>3</p>
<p>4</p>
<p>5</p>
<input type="button" onclick="getElements()" value="多少p元素" />
</body>
</html>
```

#### Anchor对象

- 返回和设置链接的charset属性

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回和设置链接的charset属性</title>
</head>
<body>
<a id="baidu" charset="ISO-8859-1" href="//www.baidu.com/">百度</a><br>
<script>
document.write("返回链接的charset: ");
document.write(document.getElementById('baidu').charset);
document.write("<br><br>");
</script>
<a id="google" href="//www.google.com/">Google</a><br>
<script>
document.getElementById('google').charset="utf-8";
document.write("设置链接的charset: ");
document.write(document.getElementById('google').charset);
</script>

</body>
</html>
```

- 返回和设置链接的href属性

```html
<!DOCTYPE html>
<html>
<head> 
<meta charset="utf-8"> 
<title>返回和设置链接的href属性</title> 
</head>
<body>
<p><a id="baidu" href="//www.baidu.com/">百度</a></p>
<script>
document.write("返回 href 链接: ");
document.write(document.getElementById('baidu').href);
</script>
</body>
</html>
```

- 返回和设置链接的hreflang属性

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回和设置链接的hreflang属性</title>
</head>
<body>
<a id="baidu" hreflang="zh-cn" href="//www.baidu.com/">百度</a><br>
<script>
document.write("返回链接的hreflang: ");
document.write(document.getElementById('baidu').hreflang);
document.write("<br><br>");
</script>
<a id="google" href="//www.google.com/">Google</a><br>
<script>
document.getElementById('google').hreflang="no";
document.write("设置链接的hreflang: ");
document.write(document.getElementById('google').hreflang);
</script>
</body>
</html>
```

- 返回一个锚的名字

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回一个锚的名字</title>
</head>
<body>
<p><a href="#C7">参见第7章</a></p>
<h2>第1章</h2>
<p>这一章解释了 ba bla bla</p>
<h2>第2章</h2>
<p>这一章解释了 ba bla bla</p>
<h2>第3章</h2>
<p>这一章解释了 ba bla bla</p>
<h2>第4章</h2>
<p>这一章解释了 ba bla bla</p>
<h2>第5章</h2>
<p>这一章解释了 ba bla bla</p>
<h2>第6章</h2>
<p>这一章解释了 ba bla bla</p>
<h2><a id="c7" name="C7">第7章</a></h2>
<p>这一章解释了 ba bla bla</p>
<script>
document.write("返回锚: ");
document.write(document.getElementById("c7").name);
</script>
</body>
</html>
```

- 返回当前的文件和链接的文档之间的关系

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回当前的文件和链接的文档之间的关系</title>
</head>
<body>
<p><a id="func" rel="friend" href="//www.baidu.com/">百度</a></p>
<script>
document.write("当前文档和链接的文档之间的关系: ");
document.write(document.getElementById("func").rel);
</script>
</body>
</html>
```

- 改变链接的target属性

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>改变链接的target属性</title>
<script>
function changeTarget(){
	document.getElementById('baidu').target="_blank";
}
</script>
</head>

<body>
<a id="baidu" href="//www.baidu.com">百度</a>
<br><br>
<input type="button" onclick="changeTarget()" value="修改target">
<p>尝试在你单击按钮之前点击链接。</p>

</body>
</html>
```

- 返回一个链接的type属性的值

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回一个链接的type属性的值</title>
</head>
<body>
<p><a id="baidu" type="text/html" href="//www.baidu.com">百度</a></p>
<script>
document.write("返回链接的type属性值：");
document.write(document.getElementById("baidu").type);
</script>
</body>
</html>
```

#### Area对象

- 返回图像眏射某个区域的替代文字

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
	<img src="../images.1/aa.jpg" width="200" height="200" usemap="#plantmap">
	<map name="plantmap">
	<area id="baidu" shape="circle" coords="200,200,200" href ="https://www.baidu.com/" alt="百度" />
	</map>
	<p>替代文本：</p>
	<script type="text/javascript">
		document.write(document.getElementById('baidu').alt);
	</script>
	</body>
</html>
```

- 返回图像眏射某个区域的坐标

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
	<img src="../images.1/aa.jpg" width="200" height="200" usemap="#plantmap">
	<map name="plantmap">
	<area id="baidu" shape="circle" coords="200,200,200" href ="https://www.baidu.com/" alt="百度" />
	</map>
	<p>百度的坐标：</p>
	<script type="text/javascript">
		document.write(document.getElementById('baidu').coords);
	</script>
	</body>
</html>
```

- 返回一个区域的href属性的锚部分

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
	<img src="../images.1/aa.jpg" width="200" height="200" usemap="#plantmap">
	<map name="plantmap">
	<area id="baidu" shape="circle" coords="200,200,200" href ="https://www.baidu.com/#description" alt="百度" />
	</map>
	<p>百度href属性的锚：</p>
	<script type="text/javascript">
		document.write(document.getElementById('baidu').hash);
	</script>
	</body>
</html>
```

- 返回的主机名：图像眏射的某个区域的端口

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
	<img src="../images.1/aa.jpg" width="200" height="200" usemap="#plantmap">
	<map name="plantmap">
	<area id="baidu" shape="circle" coords="200,200,200" href ="https://www.baidu.com/" alt="百度" />
	</map>
	<p>百度区域的端口port：</p>
	<script type="text/javascript">
		document.write(document.getElementById('baidu').host);
	</script>
	<p><b>注意:</b>如果没有指定端口部分的URL,或者是80(默认),一些浏览器将不会显示端口的部分。</p>
	</body>
</html>

```

- 返回图像眏射的某个区域的hostname

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
	<img src="../images.1/aa.jpg" width="200" height="200" usemap="#plantmap">
	<map name="plantmap">
	<area id="baidu" shape="circle" coords="200,200,200" href ="https://www.baidu.com/" alt="百度" />
	</map>
	<p>百度区域的主机名称：</p>
	<script type="text/javascript">
		document.write(document.getElementById('baidu').hostname);
	</script>
	</body>
</html>
```

- 返回图像眏射的某个区域的port

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
	<img src="../images.1/aa.jpg" width="200" height="200" usemap="#plantmap">
	<map name="plantmap">
	<area id="baidu" shape="circle" coords="200,200,200" href ="https://www.baidu.com/" alt="百度" />
	</map>
	<p>百度区域的port：</p>
	<script type="text/javascript">
		document.write(document.getElementById('baidu').port);
	</script>
	<p><b>注意:</b>如果没有指定端口部分的URL,或者是80(默认),一些浏览器会显示0或什么都没有。</p>
	</body>
</html>
```

- 返回图像眏射的某个区域的href

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
	<img src="../images.1/aa.jpg" width="200" height="200" usemap="#plantmap">
	<map name="plantmap">
	<area id="baidu" shape="circle" coords="200,200,200" href ="https://www.baidu.com/" alt="百度" />
	</map>
	<p>百度区域的href属性值：</p>
	<script type="text/javascript">
		document.write(document.getElementById('baidu').href);
	</script>
	</body>
</html>
```

- 返回图像眏射的某个区域的pathname

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
	<img src="../images.1/aa.jpg" width="200" height="200" usemap="#plantmap">
	<map name="plantmap">
	<area id="baidu" shape="circle" coords="200,200,200" href ="https://www.baidu.com/fuji" alt="百度" />
	</map>
	<p>百度区域的路径：</p>
	<script type="text/javascript">
		document.write(document.getElementById('baidu').pathname);
	</script>
	<p><b>注意:</b> IE和Opera浏览器返回 空
	而Firefox, Chrome, 和 Safari浏览器返回 &quot;/fuji &quot;.</p>
	</body>
</html>
```

- 返回图像眏射的某个区域的protocol

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
	<img src="../images.1/aa.jpg" width="200" height="200" usemap="#plantmap">
	<map name="plantmap">
	<area id="baidu" shape="circle" coords="200,200,200" href ="https://www.baidu.com/fuji" alt="百度" />
	</map>
	<p>百度区域的protocol：</p>
	<script type="text/javascript">
		document.write(document.getElementById('baidu').protocol);//protocol 加密协议
	</script>
	</body>
</html>
```

- 返回一个区域的href属性的querystring部分

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
	<img src="../images.1/aa.jpg" width="200" height="200" usemap="#plantmap">
	<map name="plantmap">
	<area id="baidu" shape="circle" coords="200,200,200" href ="https://www.baidu.com/?id=baidu" alt="百度" />
	</map>
	<p>百度区域的查询字符串部分：</p>
	<script type="text/javascript">
		document.write(document.getElementById('baidu').search);
	</script>
	</body>
</html>
```

- 返回图像眏射的某个区域的shape

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
	<img src="../images.1/aa.jpg" width="200" height="200" usemap="#plantmap">
	<map name="plantmap">
	<area id="baidu" shape="circle" coords="200,200,200" href ="https://www.baidu.com/?id=baidu" alt="百度" />
	</map>
	<p>百度区域的形状：</p>
	<script type="text/javascript">
		document.write(document.getElementById('baidu').shape);
	</script>
	</body>
</html>
```

- 返回图像眏射的某个区域的target的值

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
	<img src="../images.1/aa.jpg" width="200" height="200" usemap="#plantmap">
	<map name="plantmap">
	<area id="baidu" shape="circle" coords="200,200,200" href ="https://www.baidu.com/?id=baidu" alt="百度" target="_blank" />
	</map>
	<p>百度区域target属性值是：</p>
	<script type="text/javascript">
		document.write(document.getElementById('baidu').target);
	</script>
	</body>
</html>
```

#### Base对象

- 返回页面上所有相对URL的基URL

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回页面上所有相对URL的基URL</title>
<base id="htmldom" href="//www.baidu.com/">
</head>
<body>
<p>基础URL 是:
<script>
document.write(document.getElementById("htmldom").href);
</script>
</p>
</body>
</html>
```

- 返回页面上所有相对链接的基链接

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回页面上所有相对链接的基链接</title>
<base id="htmldom" target="_blank" href="//www.baidu.com/">
</head>
<body>
<p>所有链接的基链接:
<script>
document.write(document.getElementById("htmldom").target);
</script>
</p>
</body>
</html>
```

#### Button对象

- 当点击完button不可用

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>当点击完button不可用</title>
</head>
<body>
<form>
按钮:
<input type="button" id="firstbtn" value="OK">
<input type="button" id="secondbtn" value="OK">
</form>
<p>点击下面的按钮取消上面的第一个按钮。</p>
<button onclick="disableElement()">取消按钮</button>
<script>
function disableElement(){
	document.getElementById("firstbtn").disabled=true;
}
</script>
</body>
</html>
```

- 返回一个button的name

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回一个button的name</title>
</head>
<body>
<button id="button" name="button">按钮</button>
<p>按钮的名称：
<script>
document.write(document.getElementById("button").name);
</script></p>
</body>
</html>
```

- 返回一个button的type

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回一个button的type</title>
<script>
function alertType(){
	alert(document.getElementById("myButton").type)
}
</script>
</head>
<body>
<button id="myButton" type="button" onclick="alertType()">按钮</button>
</body>
</html>
```

- 返回一个button的value

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回一个button的value</title>
</head>
<body>
<input type="button" id="btn" value="按钮">
<p>按钮的文本: 
<script>
document.write(document.getElementById("btn").value);
</script></p>
</body>
</html>
```

- 返回一个button所属表的ID

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回一个button所属表的ID</title>
</head>
<body>
<form id="form1">
<button id="button" type="button">按钮</button>
</form>
<p>含有按钮的表单的ID: 
<script>
document.write(document.getElementById("button").form.id);
</script></p>
</body>
</html>
```

#### Form对象

- 返回一个表单中所有元素的value

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回一个表单中所有元素的value</title>
</head>
<body>
<form id="frm1" action="test.php">
第一个名字: <input type="text" name="fname" value="Name"><br>
第二个名字: <input type="text" name="lname" value="User"><br>
<input type="submit" value="提交">
</form> 
<p>返回表单中每个元素的值：</p>
<script>
var x=document.getElementById("frm1");
for (var i=0;i<x.length;i++){
  document.write(x.elements[i].value);
  document.write("<br>");
}
</script>
</body>
</html>
```

- 返回一个表单acceptCharset属性的值

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回一个表单acceptCharset属性的值</title>
</head>
<body>
<form id="frm1" accept-charset="utf-8">
第一个名字: <input type="text" name="fname" value="Donald"><br>
最后一个名字: <input type="text" name="lname" value="Duck"><br>
</form>
<p>the accept-charset属性的值:
<script>
document.write(document.getElementById("frm1").acceptCharset)
</script>
</p>
</body>
</html>
```

- 返回一个表单action属性的值

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回一个表单action属性的值</title>
</head>
<body>
<form id="frm1" action="test.php">
第一个名字: <input type="text" name="fname" value="Donald"><br>
最后一个名字: <input type="text" name="lname" value="Duck"><br>
<input type="submit" value="提交">
</form>
<p>action属性的值为：
<script>
document.write(document.getElementById("frm1").action);
</script>
</p>
</body>
</html>
```

- 返回表单中的enctype属性的值

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回表单中的enctype属性的值</title>
</head>
<body>
<form id="frm1" enctype="text/plain">
第一个名字: <input type="text" name="fname" value="Donald"><br>
第二个名字: <input type="text" name="lname" value="Duck"><br>
</form>
<p>表单数据将被编码为：
<script>
document.write(document.getElementById("frm1").enctype);
</script>
</p>
</body>
</html>
```

- 返回一个表单中元素的数量

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回一个表单中元素的数量</title>
</head>
<body>
<form id="frm1" action="test.php">
第一个名称: <input type="text" name="fname" value="Donald"><br>
第二个名称: <input type="text" name="lname" value="Duck"><br>
<input type="submit" value="提交">
</form>
<p>"frm1"元素的数量为:
<script>
document.write(document.getElementById("frm1").length);
</script>
</p>
</body>
</html>
```

- 返回发送表单数据的方法

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回发送表单数据的方法</title>
</head>
<body>
<form id="frm1" action="form_action.asp" method="get">
First name: <input type="text" name="fname" value="Donald"><br>
Last name: <input type="text" name="lname" value="Duck"><br>
<input type="submit" value="提交">
</form>
<p>发送表单数据的方法：
<script>
document.write(document.getElementById("frm1").method);
</script>
</p>
</body>
</html>
```

- 返回一个表单的name

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回一个表单的name</title>
</head>
<body>
<form id="frm" name="form">
第一个名字: <input type="text" name="fname" value="Bob"><br>
第二个名字: <input type="text" name="lname" value="Tom"><br>
</form>
<p>表单名称为:
<script>
document.write(document.getElementById("frm").name);
</script>
</p>
</body>
</html>
```

- 返回一个表单target属性的值

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回一个表单target属性的值</title>
</head>
<body>
<form id="frm" action="form_action.asp" target="_blank">
第一个名称: <input type="text" name="fname" value="Bob"><br>
最后一个名称: <input type="text" name="lname" value="Tom"><br>
<input type="submit" value="提交">
</form>
<p>target属性的值为: 
<script>
document.write(document.getElementById("frm1").target);
</script>
</p>
</body>
</html>
```

- 重置表单

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>重置表单</title>
<script>
function formReset(){
	document.getElementById("frm").reset();//重置一个表单
}
</script>
</head>
<body>
<p>在下面的输入框中输入一些文本,然后按下“重置表单”按钮重置表单。</p>
<form id="frm">
第一个名称: <input type="text" name="fname"><br>
最后一个名称: <input type="text" name="lname"><br><br>
<input type="button" onclick="formReset()" value="重置表单">
</form>
</body>
</html>
```

- 提交表单

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>提交表单</title>
<script>
function formSubmit(){
	document.getElementById("frm").submit();
}
</script>
</head>
<body>
<p>在下面的输入框中输入一些文本,然后按下“提交表单”按钮提交表单。</p>
<form id="frm" action="test.asp">
第一个名称: <input type="text" name="fname"><br>
最后一个名称: <input type="text" name="lname"><br><br>
<input type="button" onclick="formSubmit()" value="提交表单">
</form>
</body>
</html>
```

#### Frame/IFrame对象

- 对iframe排版

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>对iframe排版</title>
</head>
<body>
<p>JavaScript你好。 JavaScript你好。JavaScript你好。
JavaScript你好。JavaScript你好。JavaScript你好。
JavaScript你好。JavaScript你好。JavaScript你好。
<iframe id="myframe" src="//www.baidu.com">
<p>你的浏览器不支持iftames。</p>
</iframe>
JavaScript你好。JavaScript你好。JavaScript你好。
JavaScript你好。JavaScript你好。JavaScript你好。
JavaScript你好。JavaScript你好。JavaScript你好。</p>
<script>
document.getElementById("myframe").align="right";
</script>
</body>
</html>
```

- 改变一个包含在iframe中的文档的背景颜色

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>改变一个包含在iframe中的文档的背景颜色</title>
<script>
function changeStyle(){
    var x=document.getElementById("myframe");
//contentDocument 属性以 HTML 对象返回框架容纳的文档。可以通过所有标准的 DOM 方法来处理被返回的对象。 //contentDocument 属性能够以 HTML 对象来返回 iframe 中的文档。可以通过所有标准的 DOM 方法来处理被返回的对象。  
    var y=(x.contentWindow || x.contentDocument);
    if (y.document)  y=y.document;
    y.body.style.backgroundColor="#0000ff";
}
</script>
</head>
<body>
<iframe src="index17.html" width="200" height="200" id="myframe">
		<p>浏览器不支持iframes</p>
</iframe>
<br><br>
<input type="button" onclick="changeStyle()" value="修改背景颜色">
</body>
</html>
```

- 返回一个iframe中的frameborder属性的值

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回一个iframe中的frameborder属性的值</title>
</head>
<body>
<iframe id="myframe" src="//www.baidu.com" frameborder="0">
<p>你的浏览器不支持 iframes.</p>
</iframe>
<p>这个frameborder已设置:
<script>
document.write(document.getElementById("myframe").frameBorder);
</script>
</p>
</body>
</html>
```

- 删除iframe的frameborder

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>删除iframe的frameborder</title>
<script>
function removeBorder(){
	document.getElementById("myframe").frameBorder="0";
}
</script>
</head>
<body>
<iframe id="myframe" src="//www.baidu.com">
<p>你的浏览器不支持iframes。</p>
</iframe>
<br><br>
<input type="button" onclick="removeBorder()" value="移除边界">
<p><b>注意:</b> 该实例不能工作在IE浏览器。</p>
</body>
</html>
```

- 改变iframe的高度和宽度

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>改变iframe的高度和宽度</title>
<script>
function changeSize(){
	document.getElementById("myframe").height="300";
	document.getElementById("myframe").width="300";
}
</script>
</head>
<body>	
<iframe id="myframe" src="//www.baidu.com" height="200" width="200">
<p>你的浏览器不支持iframes。</p>
</iframe>
<br><br>
<input type="button" onclick="changeSize()" value="修改大小">
</body>
</html>
```

- 返回一个iframe中的longdesc属性的值

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回一个iframe中的longdesc属性的值</title>
</head>
<body>
<iframe id="myframe" src="//www.baidu.com" longdesc="test.txt">
<p>你的浏览器不支持iframes.</p>
</iframe>
<p>图像描述信息页面的 URL:
<script>
document.write(document.getElementById("myframe").longDesc);
</script>
<p>
</body>
</html>
```

- 返回一个iframe中的marginheight属性的值

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回一个iframe中的marginheight属性的值</title>
</head>
<body>
<iframe id="myframe" src="//www.baidu.com" marginheight="50" marginwidth="50">
<p>你的浏览器不支持iframes。</p>
</iframe>
<br><br>
<p>marginheight属性的值为:
<script>
document.write(document.getElementById("myframe").marginHeight);
</script>
<p>
<p>marginwidth属性的值为:
<script>
document.write(document.getElementById("myframe").marginWidth);
</script>
<p>
</body>
</html>
```

- 返回一个iframe中的name属性的值

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回一个iframe中的name属性的值</title>
</head>
<body>
<iframe id="myframe" src="//www.baidu.com" name="myframe">
<p>你的浏览器不支持iframes.</p>
</iframe>
<p>iframe的名称为:
<script>
document.write(document.getElementById("myframe").name);
</script>
<p>
</body>
</html>
```

- 返回和设置一个iframe中的scrolling属性的值

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回和设置一个iframe中的scrolling属性的值</title>
<script>
function removeScroll(){
	document.getElementById("myframe").scrolling="no";
}
</script>
</head>
<body>
<iframe id="myframe" src="//www.baidu.com" scrolling="auto">
<p>你的浏览器不支持iframes。</p>
</iframe>
<p>scrolling属性的值为:
<script>
document.write(document.getElementById("myframe").scrolling);
</script>
</p>
<input type="button" onclick="removeScroll()" value="移除滚动条">
<p>IE,Google Chrome,Opera,和Safari 在设置滚动条时会出现问题。</p>
</body>
</html>
```

- 改变一个iframe的src

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>改变一个iframe的src</title>
<script>
function changeSrc(){
	document.getElementById("myframe").src="//www.baidu.com";
}
</script>
</head>
<body>
<iframe id="myframe" src="//www.sina.com">
<p>你的浏览器不支持iframes。</p>
</iframe>
<br><br>
<input type="button" onclick="changeSrc()" value="修改源链接">
</body>
</html>
```

#### Image对象

- 对image排版

```html
<!DOCTYPE html>
<html lang="zh">
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<title>对image排版</title>
		<script type="text/javascript">
			function alignImg(){
				document.getElementById('myimage').align="right";
			}
		</script>
	</head>
	<body>
	<img id="myimage" src="../images/aa.jpg" alt="图片" width="200" height="200"><br>	
	<p>小孩你好！小孩你好！小孩你好！
	小孩你好！小孩你好！小孩你好！
	</p>
	<input type="button" onclick="alignImg()" value="图像对齐">
	</body>
</html>
```

- 返回image的替代文本

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>返回image的替代文本</title>
</head>
<body>
<img id="myimage" src="../images/aa.jpg" alt="图片" width="200" height="200">
<p>alt属性值为: 
<script>
document.write(document.getElementById("myimage").alt);
</script>
</p>
</body>
</html>
```

- 给image加上border

```html
<!DOCTYPE html>
<html lang="zh">
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<title>给image加上border</title>
		<script type="text/javascript">
			function addBorder(){
				document.getElementById('myimage').border='2';
			}
		</script>
	</head>
	<body>
	<img id="myimage" src="../images/aa.jpg" alt="图片" width="200" height="200"><br>	
		<input type="button" onclick="addBorder()" value="加上边框">
	</body>
</html>
```

- 改变imagedd的高度和宽度

```html
<!DOCTYPE html>
<html lang="zh">
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<title>改变imagedd的高度和宽度</title>
		<script type="text/javascript">
			function changeSize(){
				document.getElementById('myimage').width='400';
				document.getElementById('myimage').height='400';
			}
		</script>
	</head>
	<body>
	<img id="myimage" src="../images/aa.jpg" alt="图片" width="200" height="200"><br>	
		<input type="button" onclick="changeSize()" value="改变大小">
	</body>
</html>

```

- 改变image的hspace和vspace属性

```html
<!DOCTYPE html>
<html lang="zh">
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<title>改变image的hspace和vspace属性</title>
		<script type="text/javascript">
			function setSpace(){
                //hspace:左侧和右侧边距为50像素的图像
				document.getElementById('myimage').hspace='50';
                //vspace:顶部和底部边距为 50 像素的图像
				document.getElementById('myimage').vspace='50';
			}
		</script>
	</head> 
	<body>
	<img id="myimage" src="../images/aa.jpg" alt="图片" width="200" height="200">
	<p>你好你好你好</p>
		<input type="button" onclick="setSpace()" value="设置水平和垂直间距">
	</body>
</html>

```

- 返回image的longdesc属性的值

```html
<!DOCTYPE html>
<html lang="zh">
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<title>返回image的longdesc属性的值</title>
	</head>
	<body>
	<img src="../images.1/aa.jpg" alt="图片" longdesc="image.html" id="myimage"><br>
	<p>longdesc属性值为：
	<script type="text/javascript">
		var x=document.getElementById('myimage');
		document.write(x.longDesc);
	</script>
	</p>
	</body>
</html>

```

- 创建一个链接指向一个低分辨率的image

```html
<!DOCTYPE html>
<html lang="zh">
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<meta http-equiv="X-UA-Compatible" content="ie=edge">
		<title>创建一个链接指向一个低分辨率的image</title>
	</head>
	<body>
	<img src="../images.1/aa.jpg" alt="图片" longdesc="image.html" id="myimage" lowsrc="index39.html"><br>
	<p>longdesc属性值为：
	<script type="text/javascript">
		var x=document.getElementById('myimage');
		document.write('<a href="'+x.lowsrc+'">低分辨率</a>');
	</script>
	</p>
	</body>
</html>

```

- 返回image的name

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
	<img src="../images.1/aa.jpg" name="myimage" alt="图片"  id="myimage" ><br>
	<script type="text/javascript">
		document.write("图像名称：<br>");
		document.write(document.getElementById('myimage').name);
	</script>
	</body>
</html>

```

- 改变image的src

  ```html
  <!DOCTYPE html>
  <html lang="zh">
  	<head>
  		<meta charset="UTF-8">
  		<meta name="viewport" content="width=device-width, initial-scale=1.0">
  		<meta http-equiv="X-UA-Compatible" content="ie=edge">
  		<title></title>
  	<script type="text/javascript">
  		function changeSrc(){
  			var a=document.getElementById('myimage');
  			a.src="../images/雪.jpg";
  		}
  	</script>
  	</head>
  	<body>
  	<img src="../images.1/aa.jpg"  id="myimage" width="200" height="200"><br>
  	<input type="button"  value="修改图片" onclick="changeSrc()" />
  	</body>
  </html>
  
  ```

- 返回一个客户端图像眏射的usemap的值

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
  	<img src="../images.1/aa.jpg"  id="myimage" width="200" height="200" usemap="#plants">
  	<map name="plants">
  		<area shape="circle" coords="100,100,100" href ="/www.baiud.com"  />
  	</map>
  	<p>usemap属性值为：
  	<script type="text/javascript">
  		document.write(document.getElementById('myimage').useMap);
  	</script>
  	</p>
  	</body>
  </html>
  ```


#### Event对象

- 被按下的键盘键的keycode

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>被按下的键盘键的keycode</title>
<script>
function whichButton(event){
	alert(event.keyCode);
}
</script>
</head>
<body onkeyup="whichButton(event)"><!--onkeyup:当松开按键时运行脚本-->
<p><b>注释：</b>在测试这个例子时，要确保右侧的框架获得了焦点。</p>
<p>在键盘上按一个键。消息框会提示出该按键的 unicode。</p>
</body>
</html>
```

- 鼠标的坐标

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>鼠标的坐标</title>
<script>
function show_coords(event){
	var x=event.clientX;
	var y=event.clientY;
	alert("X coords: " + x + ", Y coords: " + y);
}
</script>
</head>
<body>
   <!--onmousedown:当按下鼠标按钮时运行脚本-->
<p onmousedown="show_coords(event)">点击这一行。一个消息框会提示出鼠标指针的 x 和 y 坐标。</p>
</body>
</html>
```

- 鼠标相对于屏幕的坐标

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>鼠标相对于屏幕的坐标</title>
<script type="text/javascript">
function coordinates(event){
	x=event.screenX
	y=event.screenY
	alert("X=" + x + " Y=" + y)
}
</script>
</head>
 <!--onmousedown:当按下鼠标按钮时运行脚本-->
<body onmousedown="coordinates(event)">
<p>
在文档中点击某个位置。消息框会提示出指针相对于屏幕的 x 和 y 坐标。
</p>
</body>
</html>
```

- shift键被按下了吗

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>shift键被按下了吗</title>
<script>
function isKeyPressed(event){
	if (event.shiftKey==1){
		alert(" shift 键被按下!");
	}
	else{
		alert(" shift 键没被按下!");
	}
}
</script>
</head>
<body onmousedown="isKeyPressed(event)">
<p>点击该段落，弹窗会提示是否按下 shift 键。</p>
</body>
</html>
```

- 哪个事件发生了

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>哪个事件发生了</title>
<script type="text/javascript">
function getEventType(event){ 
  alert(event.type);
}
</script>
</head>
<body onmousedown="getEventType(event)">
<p>在文档中点击某个位置。消息框会提示你触发的事件类型。</p>
</body>
</html>
```

#### Option和Select对象

- 禁用和启用下拉列表

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>禁用和启用下拉列表</title>
<script>
function disable(){
	document.getElementById("mySelect").disabled=true;
}
function enable(){
	document.getElementById("mySelect").disabled=false;
}
</script>
</head>
<body>
<form>
<select id="mySelect">
<option>学习html</option>
<option>学习css</option>
<option>学习JavaScript</option>
<option>学习jQuery</option>
</select>
<br><br>
<input type="button" onclick="disable()" value="禁用列表">
<input type="button" onclick="enable()" value="启用列表">
</form>
</body>
</html>
```

- 获得下拉列表的表单的ID

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>获得下拉列表的表单的ID</title>
</head>
<body>
<form id="myForm">
<select id="mySelect">
  <option>学习html</option>
  <option>学习css</option>
  <option>学习JavaScript</option>
  <option>学习jquery</option>
</select>
</form>
<p>form的ID为：
<script>
document.write(document.getElementById("mySelect").form.id);
</script>
</p>
</body>
</html>
```

- 获得下拉列表的选项数量

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>获得下拉列表的选项数量</title>
<script>
function getLength(){
	alert(document.getElementById("mySelect").length);
}
</script>
</head>
<body>
<form>
<select id="mySelect">
<option>学习html</option>
<option>学习css</option>
<option>学习JavaScript</option>
<option>学习jquery</option>
<option>学习vue.js</option>
</select>
<input type="button" onclick="getLength()" value="列表数组有多少个">
</form>
</body>
</html>
```

- 将下拉列表变成多行列表

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>将下拉列表变成多行列表</title>
<script>
function changeSize(){
	document.getElementById("mySelect").size=4;
}
</script>
</head>
<body>
<form>
<select id="mySelect">
<option>苹果</option>
<option>香蕉</option>
<option>橙子</option>
<option>甜瓜</option>
</select>
<input type="button" onclick="changeSize()" value="修改列表大小">
</form>
</body>
</html>
```

- 在下拉列表中选择多个选项

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>在下拉列表中选择多个选项</title>
<script>
function selectMultiple(){
	document.getElementById("mySelect").multiple=true;
}
</script>
</head>
<body>

<form>
<select id="mySelect" size="4">
<option>rap</option>
<option>trap</option>
<option>old school</option>
<option>fire</option>
</select>
<input type="button" onclick="selectMultiple()" value="选择多个">
</form>
<p>在你点击“选择多个”按钮之前,尽量选择一个以上的选项(通过按下shift或Ctrl键)。然后尝试点击“选择多个”按钮。</p>

</body>
</html>
```

- 弹出下拉列表中被选中的选项

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>弹出下拉列表中被选中的选项</title>
<script>
function getOptions(){
    var x=document.getElementById("mySelect");
    var txt="选中的人物是: ";
    var i;
    for (i=0;i<x.length;i++){
        if(x.options[i].selected) {
            txt=txt + "\n" + x.options[i].text;
        }
    }
    alert(txt);
}
</script>
</head>
<body>
<form>
你喜欢的人物是：
<select id="mySelect">
  <option>诸葛亮</option>
  <option>刘备</option>
  <option>张飞</option>
  <option>关羽</option>
</select>
<br><br>
<input type="button" onclick="getOptions()" value="输出选中人物选项">
</form>
    
</body>
</html>
```



### JavaScript 和 HTML DOM 参考手册

所有内置的JavaScript对象

所有浏览器对象

所有HTML DOM对象

#### JavaScript 对象参考手册

#### JavaScript Array 对象

#### Array 对象

Array 对象用于在变量中存储多个值:

```js
var name = ["Tom", "Bob", "Joe"];
```

第一个数组元素的索引值为 0，第二个索引值为 1，以此类推。

#### 数组属性

|    属性     |              描述              |
| :---------: | :----------------------------: |
| constructor |   返回创建数组对象的原型函数   |
|   length    |    设置或返回数组元素的个数    |
|  prototype  | 允许你向数组对象添加属性或方法 |

#### JavaScript constructor 属性

返回name数组对象原型创建的函数：

```
name.constructor
```

结果输出：

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>点击按钮创建一个数组，并显示它的构造函数.=。</title>
</head>
<body>
<p id="demo"></p>
<button onclick="myFunction()">按钮</button>
<script>
function myFunction()
{
	var name= ["Tom", "Bob", "Joe", "Jie"];
	var x=document.getElementById("demo");
	x.innerHTML=fruits.constructor;//function Array() { [native code] }
}
</script>
</body>
</html>
```

#### 定义和用法

在 JavaScript 中, constructor 属性返回对象的构造函数。

返回值是函数的引用，不是函数名：

JavaScript 数组 constructor 属性返回 **function Array() { [native code] }**

JavaScript 数字 constructor 属性返回 **function Number() { [native code] }**

JavaScript 字符串 constructor 属性返回 **function String() { [native code] }**

如果一个变量是数组你可以使用 constructor 属性来定义。

#### 浏览器支持

所有主流浏览器都支持 constructor 属性。

#### 语法

```
array.constructor
```

#### 技术细节

| 返回值               | 一个函数对象，该函数由数组对象的原始创建。 |
| -------------------- | ------------------------------------------ |
| **JavaScript 版本:** | 1.1                                        |

#### JavaScript length 属性

返回数组的数目：

```
name.length
```

结果输出：

```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>length属性</title>
</head>
<body>
<p id="demo">点击按钮创建数组，并显示数组元素个数。</p>
<button onclick="myFunction()">按钮</button>
<script>
function myFunction()
{
var name = ["Bob", "Tom", "Joe", "Jie"];
var x=document.getElementById("demo");
x.innerHTML=name.length;
}
</script>
</body>
</html>
```

#### 定义和用法

length 属性可设置或返回数组中元素的数目。

#### 浏览器支持

所有主要浏览器都支持length 属性。

#### 语法

设置数组的数目：

```
array.elngth=number
```

Return the length of an array:

```
array.length
```

#### 技术细节

| **返回值：**         | 一个数字，表示数组中的对象的元素数目。 |
| -------------------- | -------------------------------------- |
| **JavaScript 版本:** | 1.1                                    |

#### JavaScript Array 属性 构造器

一个新的数组的方法，将数组值转为大写：

```
Array.prototype.myName=myfunction(){
    for(i=0;i<this.length;i++){
        this[i]=this[i].toUpperCase();//把字符串转换为大写
    }
}
```

创建一个数组，然后调用 myName 方法：

```
var  name=["tom","joe","bob"];
name.myName();
```

*fruits* 数组现在的值为：

```
TOM,JOE,BOB
```

结果输出：

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>小写变大写</title>
</head>
<body>
<p id="demo">点击按钮创建数组，并调用新建的 ucase() 方法, 最后显示结果。</p>
<button onclick="myFunction()">按钮</button>
<script>
Array.prototype.myName=function()
{
    for (i=0;i<this.length;i++)
    {
        this[i]=this[i].toUpperCase();
    }
}
function myFunction()
{
    var name= ["Bob", "Tom", "Joe"];
    name.myName();
    var x=document.getElementById("demo");
    x.innerHTML=name;
}
</script>
</body>
</html>
```

#### 定义和用法

prototype 属性使您有能力向对象添加属性和方法。

当构建一个属性，所有的数组将被设置属性，它是默认值。

在构建一个方法时，所有的数组都可以使用该方法。

**注意：** Array.prototype 单独不能引用数组, Array() 对象可以。

**注意：** 在JavaScript对象中，Prototype是一个全局属性。

#### 浏览器支持

所有主要浏览器都支持prototype 属性。

#### 语法

```
Array.prototype.name=value;
```

#### Array对象方法

|     方法      |                         描述                         |
| :-----------: | :--------------------------------------------------: |
|   concat()    |          连接两个或更多的数组，并返回结果。          |
| copyWithin()  |  从数组的指定位置拷贝元素到数组的另一个指定位置中。  |
|   entries()   |                返回数组的可迭代对象。                |
|    every()    |        检测数值元素的每个元素是否都符合条件。        |
|    fill()     |              使用一个固定值来填充数组。              |
|   filter()    |     检测数值元素，并返回符合条件所有元素的数组。     |
|    find()     |       返回符合传入测试（函数）条件的数组元素。       |
|  findIndex()  |     返回符合传入测试（函数）条件的数组元素索引。     |
|   forEach()   |           数组每个元素都执行一次回调函数。           |
|    from()     |            通过给定的对象中创建一个数组。            |
|   includes    |          判断一个数组是否包含一个指定的值。          |
|   indexOf()   |        搜索数组中的元素，并返回它所在的位置。        |
|   isArray()   |                 判断对象是否为数组。                 |
|    join()     |           把数组的所有元素放入一个字符串。           |
|    keys()     |    返回数组的可迭代对象，包含原始数组的键(key)。     |
| lastIndexOf() |      搜索数组中的元素，并返回它最后出现的位置。      |
|     map()     | 通过指定函数处理数组的每个元素，并返回处理后的数组。 |
|     pop()     |       删除数组的最后一个元素并返回删除的元素。       |
|    push()     |   向数组的末尾添加一个或更多元素，并返回新的长度。   |
|   reduce()    |         将数组元素计算为一个值（从左到右）。         |
| reduceRight() |         将数组元素计算为一个值（从右到左）。         |
|   reverse()   |                 反转数组的元素顺序。                 |
|    shift()    |             删除并返回数组的第一个元素。             |
|    slice()    |        选取数组的的一部分，并返回一个新数组。        |
|    some()     |         检测数组元素中是否有元素符合指定条件         |
|    sort()     |                对数组的元素进行排序。                |
|   splice()    |               从数组中添加或删除元素。               |
|  toString()   |           把数组转换为字符串，并返回结果。           |
|   unshift()   |   向数组的开头添加一个或更多元素，并返回新的长度。   |
|   valueOf()   |                返回数组对象的原始值。                |

####  JavaScript concat() 方法         

#### 实例

合并三个数组的值：

```js
var name1=["小美","小红"];
var name2=["小杰"];
var name3=["小明"];
var myName=name1.concat(name2,name3);
```

myName输出结果：

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>concat() 方法用于连接两个或多个数组。</title>
</head>
<body>
<script>
var name1=["小美","小红"];
var name2=["小杰"];
var name3=["小明"];
var myName=name1.concat(name2,name3);
document.write(myName);
</script>	
</body>
</html>
```

#### 定义和用法

concat() 方法用于连接两个或多个数组。

该方法不会改变现有的数组，而仅仅会返回被连接数组的一个副本。

#### 浏览器支持

所有主要浏览器都支持concat()属性。

#### 语法

```
array1.contcat(array2,array3,array4,.....,arrayN)
```

#### 参数

| 参数                                              | 描述                                                         |
| ------------------------------------------------- | ------------------------------------------------------------ |
| array1.contcat(array2,array3,array4,.....,arrayN) | 必需。该参数可以是具体的值，也可以是数组对象。可以是任意多个。 |

#### 返回值

| Type       | 描述                                                         |
| ---------- | ------------------------------------------------------------ |
| Array 对象 | 返回一个新的数组。该数组是通过把所有 arrayX 参数添加到 arrayObject 中生成的。如果要进行 concat() 操作的参数是数组，那么添加的是数组中的元素，而不是数组。 |

#### 技术细节

| 版本                 | 版本号支持 |
| -------------------- | ---------- |
| **JavaScript 版本:** | 1.2        |

#### JavaScript copyWithin() 方法

#### 实例

复制数组的前面两个元素到后面两个元素上：

```js
var names=["Tom","Jie","lisa","Joe"];
names.copyWithin(2,0);//就是把前两个数组元素复制到后面
```

names输出结果：

```
Tom，Jie，Tom，Jie
```

实例输出结果：

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>copyWithin() 方法用于从数组的指定位置拷贝元素到数组的另一个指定位置中。</title>
</head>
<body>
<p>点击按钮复制数组的前面两个元素到后面两个元素上。</p>
<button onclick="myFunction()">按钮</button>
<p id="demo"></p>
<p><strong>注意:</strong> IE 11 及更早版本不支持 copyWithin() 方法。</p>
<script>
var  names=["Tom","Jie","lisa","Joe"];
document.getElementById("demo").innerHTML = names;
function myFunction() {  
    document.getElementById("demo").innerHTML = names.copyWithin(2,0);
}
</script>
</body>
</html>
```

#### 定义和用法

copyWithin() 方法用于从数组的指定位置拷贝元素到数组的另一个指定位置中。

#### 浏览器支持

表格中的数字表示支持该方法的第一个浏览器版本号。

| 方法         | Google Chrome | IE   | fireFox | Safari | Opera |
| ------------ | ------------- | ---- | ------- | ------ | ----- |
| copyWithin() | 45.0          | 12.0 | 32.0    | 9      | 32.0  |

#### 语法

```
array.copyWithin(target,start,end)
```

#### 参数

| 参数   | 描述                                                         |
| ------ | ------------------------------------------------------------ |
| target | 必需。复制到指定目标索引位置。                               |
| start  | 可选。元素复制的起始位置。                                   |
| end    | 可选。停止复制的索引位置 (默认为 *array*.length)。如果为负值，表示倒数。 |

#### 技术细节

| 返回值           | 数组         |
| ---------------- | ------------ |
| JavaScript 版本: | ECMAScript 6 |

​                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            

​                                                                                           

​                                                 