### Javascript现在的意义

1.网页特效

2.服务端开发（Node.js）

3.命令行工具（Node.js）

3.桌面程序（Electron）

4.App（Cordova）

5.控制硬件-物联网（Ruff）

6.游戏开发（cocos2d-js）

### Javascript和HTML、CSS的区别

1. HTML，提供网页的结构，提供网页中的内容
2. CSS：用来美化网页
3. Javascript：可以用来控制网页内容，给网页增加新动态的效果

### Javascript的组成

Javascript由ECMAScript、DOM、BOM

#### ECMAScript-JavaScript的核心

ECMA欧洲计算机制造联合会

网景：Javascript

微软：JScript

定义了Javascript的语法规范

#### BOM-浏览器对象模型

一套操作浏览器功能的API

通过BOM可以操作浏览器窗口，比如，弹出框、控制浏览器跳转、获取分辨率等

#### DOM-文档对象模型

一套操作页面元素的API

DOM可以把HTML看做是文档时，通过DOM提供的API可以对树上的节点进行操作

### js的代码可以分三个地方写：

1.在html的文件中，script的标签中写js代码
2.js代码可以在html的标签中写
3.在js文件中可以写js代码，但是需要在html的页面中引入

### 变量

操作的数据都是在内存中操作
js中存储数据使用变量的方式（名字，值---->数据）
js中声明变量都用var---->存储数据，数据应该用对应的数据类型
js中的字符串类型的值都用双引号或者单引号
存储一个数字11
变量的声明及赋值
var  num=10;
存储一个名字
var 	name='小黑';

变量--作用，存储数据的
变量声明（有var 	有变量名字，没有值）
变量初始化（有var 有变量名字，有值）

var  number;//变量的声明,此时是没有赋值的
一次性声明多个变量
var x,y,z,k,j;//都是声明，没有赋值
	
变量的初始化（变量声明的同时并且赋值了）
=的意思：是赋值的含义
存储一个数字11

```js
var number=11;
// 存储一个人的名字
var name="小黑";
// 存储一个（true）
var flag=true;
// 存储一个null--->相当于是空
var null=null;
// 存储一个对象
var obj=new Object();
```

#### 		什么是变量

-    什么是变量

     变量是计算机内存中存储数据的标识符，根据变量名称可以获取到内存中存储的数据

-    为什么要使用变量

     使用变量可以方便的获取或者修改内存中的数据

  ####   如何使用变量

  1. var声明变量

  ```js
  var age;
  ```

    2.变量的赋值

  ```js
  var	age;
  age=18;
  ```

   3.同时声明多个变量

  ```js
  var age,name,sex;
  age=10;
  name="bob";
  ```

   4.同时声明多个变量并赋值

  ```js
  var	age=10,name='zs';
  ```

  #### 变量在内存中的存储

  ```js
  var	age=18;
  ```

  ### 变量的命名规则和规范

- 规则-必须遵守的，不遵守会报错
  - 有字母、数字、下划线、$符号组成，不能以数字开头
  - 不能是关键字和保留字，例如，for、while、if等等
  - 区分大小写
- 规范-建议遵守的，不遵守不会报错
  - 变量名必须有意义
  - 遵守驼峰命名法。首字母小写，后面单词的首字母需要大写。列如，userName、userPassword
- 下面那些变量名不合法

```select a language
a	合法
1	不合法
age18	合法
18age	不合法
name	合法
$name	合法
_sex	合法
&sex	不合法
theworld	合法	但是需要用驼峰命名法:theWorld
```

#### 案例

1.交换两个变量的值

2.不使用临时变量，交换两个数值变量的值

### 数据类型

#### 简单数据类型

Number、String、Boolean、Undefined、Null

#### Number类型

- 数值字面量，数值端 、固定值的表示法

  110	1024	60.5

- 进制

```select a language
十进制
	var	num	= 9;
	进行算数计算时，八进制和十六进制表示的数值最终都将转换成十进制数值。
十六进制
	var	num = 0XA;
	数字序列范围: 0~9以及A-F
八进制
	var	num1 = 07;//对应十进制的7
	var num2 = 019;//对应十进制的19
	var	num3=08;//对应十进制的8
	数字序列范围：0~7
	如果字面值中的数值超出了范围，那么前导零将被忽略，后面的数值将被当作十进制数值解析
	
```

- 浮点数

  - 浮点数的精度问题

  ```select a language
  浮点数
  	var	n=5e-324	//科学计数法	5乘以10的-324次方
  	浮点数值的最高精度是17为小数，但在进行算术计算时其精确度远远不如整数
  	var	result=0.1+0.2;		//结果不是0.3	而是：0.30000000000004
  	console.log(0.07*100)
  	不要判断两个浮点数是否相等
  ```

- 数值范围

```select a language
  最小值：Number.MIN_VALUE,这个值为：5e-324
  最大值：Number.MAX_VALUE,这个值为：1.7976931348623157e+308
  无穷大：Infinty
  无穷小：-Infinity
```

-  数值判断


  - NaN：not a number
    - NaN与任何值都不相等，包括他本身
  - isNaN：is not a number

#### String类型

'abc' "abc"

- 字符串字面量

  "程序猿"，‘程序猿’，“黑马程序猿”

  思考：如何打印以下字符串

  我是一个“正直”的人

  我很喜欢“黑马程序猿”

- 转义符

  | 字面量 | 含义                                                         |
  | ------ | ------------------------------------------------------------ |
  | \n     | 换行                                                         |
  | \t     | 制表                                                         |
  | \b     | 空格                                                         |
  | \r     | 回车                                                         |
  | \f     | 进纸换页                                                     |
  | \\\    | 斜杠                                                         |
  | \\'    | 单引号（'）,在用单引号表示的字符串中使用。列如：‘  He said，\’hey.\\' ' |
  | \\"    | 双引号（"）,在用双引号表示的字符串中使用。列如："He said，\”hey.\\“ " |
  | \xnn   | 以十六进制代码nn表示的一个字符（其中n为0-F）。例如，\x41表示“A” |
  | \unnnn | 以十六进制代码nnnn表示的一个Unicode字符（其中n为0-F）。例如，\u03a3表示希腊字符如下图所示 |

$$
\sum
$$

- 字符串长度

  length属性用来获取字符串的长度

  ```js
  var  str='黑马程序猿 Hello world';
  console.log(str.length);
  ```

- 字符串拼接

  字符串拼接使用+连接

  ```js
  console.log(11+11);
  console.log('hello'+'world');
  console.log('100'+'100');
  console.log('11'+11);
  console.log('male:'+true);
  ```

  1. 两边只要有一个是字符串，那么+就是字符串拼接功能
  2. 两边如果都是数字，那么就是算术功能。

  ### Boolean类型

- Boolean字面量：true和flase，区分大小写

- 计算机内部存储：true为1， false为0

  ### Undefined和Null

  1. undefined表示一个声明了没有赋值的变量，变量只声明的时候值默认是undefined
  2. null表示一个空，变量的值如果想为null，必须手动设置

  #### 复杂数据类型

  Object

  #### 获取变量的类型

  typeof

  ```js
  var age=18;
  console.log(typeof age); //'number'
  ```

  #### 字面量

  在源代码中一个固定值的表示法。

  数值字面量：8,9,10

  字符串字面量：‘黑马’，‘前端’

  布尔字面量：true，false

  #### 注释

  单行注释

  用来描述下面一个或多行代码的作用

  ```js
  //这是一个变量
  var name='你好';
  ```

  #### 多行注释

  用来注释多条代码

  ```js
  /*
  var age=18;
  var name='zs';
  console.log(name,age);
  */
  ```

  ### 数据类型转换

  如何使用谷歌浏览器，快速的查看数据类型？

  字符串的颜色是黑色的，数值类型是蓝色的，布尔类型也是蓝色的，undefined是灰色的

  #### 转换成字符串类型

- toString()

  ```js
  var num=5;
  console.log(num.toString());
  ```

- String()

  ```
  String()函数存在的意义:有些值没有toString(),这个时候可以使用String()。比如：undefined和null
  ```

- 拼接字符串方式

  num+"",当+两边有个操作符是字符串类型，一个操作符其他类型的时候，会先把其他类型转换成字符串再进行字符串拼接，返回字符串

  #### 转换成数值类型

- Number()

  ```
  Number()可以把任意值转换成数值，如果要转换的字符串中有一个不是数值的字符，返回NaN
  ```

- parseInt

  ```js
  var num1=parseInt("12.3abc");//返回12，如果第一个字符是数字会解析知道遇到非数字结束
  var num2=parseInt("abc123");//返回NaN，如果第一个字符不是数字或者符号就返回NaN
  ```

- parseFloat()

  ```
  parseFloat()把字符串转换成浮点数
  parseFloat()和parseInt非常相似，不同之处在与
  ```

	parseFloat会解析第一个，遇到第二个，或者非数字结束
  	如果解析的内容里只要整数，解析成整数
  ```
  
- +，-0等运算

  ```js
  var str='300';
  console.log(+str); //取正
  console.log(-str);//取负
  console.log(str-0);
  
  ```

  #### 转换成布尔类型

- Boolean()

  0 (“ ”)   null undefined NaN 会转成false 其他都会转成true

  #### 操作符

  运算符 operator

  5+6

  表达式  	组成	操作数和操作符，会有一个结果

  #### 算术运算符

  ```
  + - */%
  ```

  #### 一元运算符

  一元运算符：只有一个操作数的运算符

  5+6两个操作数的运算符 二元运算符

  ++ 自身加1

  -- 自身减1

- 前置++

  ```js
  var num1=5;
  ++num1;
  var num2=6;
  console.log(num+ ++ num2);//13
  ```

- 后置++

  ```js
  var num1=5;
  num1++;
  var num2=6;
  console.log(num1 + num2++);
  ```

- 猜猜看

  ```js
  var a=1; var b= ++a + ++a;	console.log(b);//2+3  5
  var a=1; var b= a++ + ++a;  console.log(b);//1+2+1  4
  var a=1; var b=	a++ + a++;  console.log(b);//2+1  3
  var a=1; var b= ++a + a++;  console.log(b);//2+1+1  4
  ```

  总结

  前置++;先加1，后参与运算

  后置++；先参与运算，后加1

  什么两个理解后，下面两个自通

  前置-：先减1，后参与运算

  后置-：先参与运算，后减1

#### 逻辑运算符（布尔运算符）

```
&&与两个操作数同时为true，结果为true，否则都是false
||或两个操作数有一个为true，结果为true，否则为false
！非 取反
```

#### 关系运算符（比较运算符）

```
<  >  >=  <=  ==  !=  != ===  !==
```

```js
==与===的区别： ==只是进行值的比较，===类型和值同时相等，则相等

var	result = '55' ==55; //true
var result = '55' ===55; //false 值相等，类型不相等
var result = 55 ===55; //true
```

#### 赋值运算符

= +=  -= *=  /= %=

```js
例如：
var num=0;
num +=5; //相当于 num=num+5;
```

#### 运算符的优先级

```   ===
优先级从高到低
	1.() 优先级最高
	2.一元运算符  ++  -- ！
	3.算数运算符  先* /  %  后+ -
	4.关系运算符  >   >=  <   <=
	5.相等运算符  ==  !=  ===  !==
	6.逻辑运算符 先 && 后 ||
	7.赋值运算符
```

```js
//练习1：
var result=(4>=6 || '人' !='猫'&&!(12*2==144)&&true);
console.log(result);//true
//练习2：
var num=10;
var result1=(5== num/2&&(2+2*num).toString()==='22');
console.log(result1);
```

### 表达式和语句

#### 表达式

一个表达式可以产生一个值，有可能是运算、函数调用、有可能是字符面量。表达式可以放在任何需要值的地方。

#### 语句

语句可以理解为一个行为，循环语句和判断语句就是典型的语句，一个程序有很多个语句组成，一般情况下；分割一个一个的语句

#### 流程控制

程序的三种基本结构

#### 顺序结构

从上到下执行的代码就是顺序结构

程序默认就是由上到下顺序执行的

#### 分支结构

根据不同的情况，执行对应代码

#### 循环结构

循环结构：重复做一件事情

#### 分支结构

#### if语句

语法结构

```js
if(/*条件表达式*/){
   //执行语句
   }
if(/*条件表达式*/){
   //成立执行语句
   }else{
    //否则执行该语句
}
if(/*条件表达式*/){
   //成立执行语句
   }else if(/*条件2*/){
    //成立执行语句        
            }else if(/*条件3*/){
           //成立执行语句              
                     }else{
    //最后，默认执行语句
}
```

#### 三元运算符

```
表达式1?表达式2 :表达式3
是对if-else语句的一种简化写法
```

#### switch语句

语法格式：

```js
switch(expression){
   case 常量1:
        语句;
        break;
   case 常量2:
        语句;
        break;
   case 常量3:
        语句;
        break;
   case 常量n:
        语句;
        break;
    default: 
        语句;
        break;
}
```

```
break可以省略，如果省略，代码会继续执行下一个case
switch语句在比较值时使用的是全等操作符，因此不会发生类型转换(例如，字符串'10'不等于数值的10)
```

#### 布尔类型的隐式转换

流程控制语句会把后面的值隐式转换成布尔类型

```
转换为true 非空字符串 非0数字 true 任何对象
转换为false 空字符串 0 false null undefined
var a=!!'123';true
```

#### 循环结构

在JavaScript中，循环语句有三种，while、do..while、for循环。

#### while语句

基本语法：

```js
//当循环条件为true时，执行循环体
//当循环条件为false时，结束循环。
while(循环条件){
    //循环体
}
```

代码示例：

```js
//计算1-100之间所有数的和
//初始化变量
var i=1;
var sum=0;
//判断条件
while(i<=100){
    //循环体
    sum+=i;
    i++;
}
console.log(sum);
```

#### do-while语句

do..while循环和while循环非常相似，二者可以相互替代，但是do..while的特点是不管条件成不成立，都会执行一次。

基础语法：

```js
do{
    //循环体
}
while(循环条件);
```

代码示例：

```js

var i=1;
var sum=0;
//判断条件
	do{
    //循环体
    sum+=i;
    //自增
    i++;
}while(i<=100)//循环条件
console.log(sum);
```

#### for语句

while和do..while一般用来解决无法确认次数的循环。for循环一般在循环次数确定的时候比较方便

for循环语法：

```js
//for循环的表达式之间用的是;号分隔的，千万注意不要写成,
for(初始化表达式1;判断表达式2;自增表达式){
    //循环体
}
```

执行顺序：

1.初始化表达式

2.判断表达式

3.自增表达式

4.循环体

#### continue和break

break：立即跳出整个循环，即循环结束，开始执行循环后面的内容（直接跳到大括号）

continue：立即跳出当前循环，继续下一次循环（跳到i++的地方）、

#### 调试

- 过去调试JavaScript的方式
  -  alert()
  - console.log()
- 断点调试

  断点调试是指自己在程序的某一行设置一个断点，调试时，程序运行到这就会停住，然后你可以一步一步往下调试，调试过程中可以看各个变量当前的值，出错的话，调试到出错的代码行即显示错误，停下。

- 调试步骤

```
浏览器中按F12---->Sources---->找到需要调试的文件------>在程序的某一行设置断点
```

- 调试中的相关操作

```
watch： 监视，通过watch可以监视变量的值的变化，非常的常用。
F10：程序单步执行，让程序一行一行的执行，这个时候，观察watch中变量的值的变化。
F8： 跳到下一个断点处，如果后面没有断点了，则程序执行结束。
```

tips：监视变量，不要监视表达式，因为监视了表达式，那么这个表达式也会执行。

1.代码调试的能力非常重要，只学会了代码调试，才能学会自己解决bug的能力，初学者不要觉得调试代码麻烦就不去调试，一定要有自己独立调试代码的能力。

2.学去学习调试技巧和门路，然后融汇贯通。

### 数组

#### 为什么要学习数组

之前学习的数据类型，只能存储一个值（比如：Number/String）。我们想存储中所有学生的姓名，此时该如何存储？用数组可以解决此问题

#### 数组的概念

所谓数组，就是将多个元素（通常是同一类型）按一定顺序排列放到一个集合中，那么这个集合我们就称之为数组。

#### 数组的第义

数组是一个有序的列表，可以在数组中存放任意的数据，并且数组的长度可以动态的调整。

通过数组字面量创建数组

```js
//创建一个空数组
var arr1=[];
//创建一个包含3个数值的数组，多个数组项以逗号隔开
var arr2=[1,2,3,4,5,6];
//创建一个包含2个字符串的数组
var arr3=['a','b','c'];
//可以通过数组的length属性获取数组的长度
console.log(arr3.length);
//可以设置length属性改变数组中元素的个数
arr3.length=0;
```

#### 获取数组元素

数组的取值

```js
//格式：数组名[下标] 下标又称为索引
//功能：获取数组对应下标的那个值，如果下标不存在，则返回undefined
var arr=["bob","tom","blue"];
arr[0];//bob
arr[2];//blue
arr[3];//这个数组的最大下标为2，因此返回undefined
```

#### 遍历数组

遍历，遍及所有，对数组的每一个元素都访问一次就叫遍历。

数组遍历的基本语法：

```js
for(var i=0;i<arr.length;i++){
    //数组遍历的固定结构
}
```

#### 数组中新增元素

数组的赋值

```js
//格式：数组名[下标/索引]=值;
//如果下标有对应的值，会把原来的值覆盖，如果下标不存在，会给数组新增一个元素。
var arr=[Tom,Bob,Jie];
//把Tom换成小明
arr[0]="小明";
//给数组新增加了一个小美的值
arr[3]="小美";
```

### 函数

#### 为什么要有函数

如果要多个地方求1~100之间所有数的和，应该怎么做？

定义一个函数，然后调用函数，使多个地方都可以用1~100之间的和

#### 什么是函数

把一段相对独立的具有特定功能的代码块封装起来，形成一个独立的实体，就是函数，起个名字（函数名），在后续的开发中可以反复的使用

函数的作用就是封装一段代码，将来可以重复使用

#### 函数的定义

- 函数声明

```js
function 函数名(){
    //函数体
}
```

- 函数表达式

```js
var fn=function(){
    //函数体
}
```

- 特点：

  函数声明的时候，函数体并不执行，只要当函数被调用的时候才执行。

  函数一般都用来干一件事，需用使用动词+名词，表示做一件事情 tellStory sayHello等

#### 函数的调用

- 调用函数的语法：

```
函数名();
```

- 特点：

函数体只有在调用的时候才会执行，调用需要()进行调用。

可以调用多次（重复使用）

代码示例：

```js
//声明函数
function sayHello(){
    console.log("你好");
}
//调用函数
sayHello();
//求1~100之间所有数的和
function getSum(){
    var sum=0;
    for(i=0;i<100;i++){
        sum+=i;
    }
}
```

