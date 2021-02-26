[toc]

# javascript精华版

# 一、简介



# 二、编辑器

# 三、基础

## 1.写在哪里

​	

```javascript
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<script type="text/javascript">
			// js 代码写在这里
	</script>
</head>
<body>
	
</body>
</html>
```



## 2.注释

```javascript
/**/  注释内容不会被执行， 但是在源码中可以查看
// 单行注释
```



## 3.输出

```javascript
console.log();// 输出到控制台
console.write(); // 输出到html页面
alert();//弹出警示框
```



## 4.执行方式

```javascript
从上到下逐行执行

	<button onclick="alert('1');" >点我弹出js-onclick</button>
	<a href="javascript:alert('2');">点我弹出js-a</a>
	<a href="javascript:;">点我不跳转，不弹出</a>
	虽然可以写在标签中，但是属于结构耦合，不方便管理
	
```

## 5.引入js方式

```javascript
	1.本页面中执行
	<script type="text/javascript">
			// js 代码写在这里
	</script>
	
	2.外部引入 好处可以复用 在标签中就不能写代码了
	<script type="text/javascript" href="1.js" ></script>
```





# 四、使用方法

## 1.基本语法

​	1.js严格区分大小写

​	2.js中每一条语句以分号结尾

​	3.如果不写， 系统解析代码会自动增加，会消耗资源，有可能加载错误。

​	4.自动忽略空格和换行

​	



## 2.字面量 和变量

字面量 ： 不可变的常量值，可以直接使用

例如	： 1，2，3，4

变量	： 可以用来保存字面量，可以任意改变

## 3.声明变量和使用

```javascript
var a = 1; 
console.log(var);
```

## 4.标识符号

由我们在js 中自主 命名的称为标识符

​		例如： 变量名、函数、 属性名都属于

需要遵守规则

​		可以含有字母、数字、下划线、$

​		不能以数字开头

不能是es 中的关键字或保留字

命名规范 一般采用驼峰命名

​	开头单词字母大写余下小写

​	NameGems

es 底层保存表示服时，实际上是采用Unicode 编码

## 5.数据类型

6种 

### 1.String 字符串 

```javascript
var str = “hello”；
var str = 'hello'；
var str = “say:\"hello\"”；\\ 表示转义字符
\n 换行
\t 制表符 按下tab 键 
\\  \  转义 
```



### 2.Number 数值

js中所有的数值都是number类型

包含整数和浮点数（小数）

```javascript
var a = 1.1;
```

检查类型

typeof 变量

```javascript
console.log(typeof a);
```

```javascript
console.log(Number.Max_value);// 最大值1.79e +308
如果超过了最大值，会返回一个Infinity 表示正无穷

var a = "123" *"123" 返回 NaN  不是一个数字
```

js 不允许进行计算资金 容易出错 例如：

```javascript
0.1 +0.2
```



### 3.boolen 布尔值

只有true 和false

```javascript
var a = true; 
var a = false; 
```



### 4.Null 空值

表示对象为null 空对象

```javascript
var a = null ;
console.log（typeof a）  返回  object 

```



### 5.Undefined 未定义

声明变量但未赋值的时候，值就是Undefined 

```javascript
var a ;
console.log(a);
console.log（typeof a）  返回  Undefined  
```



### 6.Object  对象

```javascript
Object 属于引用数据类型

余下属于 基本数据类型
```

## 6.数据转换

### 1.转换string

强制类型转换

将一个类型强制转换为其他数据类型

```javascript
var a = 123;
```

方式一 .toString() 不会影响原变量

会返回转换结果

```javascript
a.toString()  
a = a.toString()
console.log(a)
null 和undefind 转换 报错
```

方式二  调用String 函数并将被转换数据传递给函数

```javascript
var a = 12;
a = String(a); 
console.log(typeof a)
```

### 2.转换Number

调用Number 函数将a 转换为Number 类型

字符串转数值

1.纯数字   直接转换为数字

2.非数字	转为NaN

3 空  转换为 0 

```javascript
var a = "123";
Number();
a = Number(a);
var a = “a1”;  NaN
var a = "";  0
var = true； true 1 false 0 
a = null ; 0 
a = undefined ; nan 

```

```javascript
var a = "123as";
a = paseint(a);
将a 转为number
将字符串中有效数字转为number


var a = "123.12";
a = pasefloat(a);
将a 转为number
将字符串中有效数字转为number

```

### 3.其他进制的数字

```javascript
var a = 0x123;// 16 进制的数字  0x 开头
var a = 070;// 8 进制的数字  0 开头
var a = 0b10;// 2 进制的数字  0b 开头
```

### 4.转为boolen

```javascript
var a = 123;
a = Boolean(a);//true
var a = -123; // true
a = 0 ; false
a = Infinity true
a = nan false 

```

```javascript
字符串 除啦空传其余都是true
var a = "a";// true
 a = " " false
null 和undefined 转换为false 

```

## 7.运算符

### 1.运算符简介

### 

```javascript
运算符 操作符
通过运算符可以进行一个或多个值进行运算
比如 typeof  就是运算符 可以获得一个值得类型

都是会返回结果的
不会对原变量进行影响
```



### 2.算数运算符

```javascript
+
-
*
/
%

```

```javascript
let a = 2+1;
let a = 2-1;
let a = 2*1;
let a = 2/1;
let a = 2%1;
```

### 3.一元运算符

```javascript
只需要一个操作数  成为一元运算符
+  正号
	正号不会对数字产生影响
-  负号
	负号会对数字进行取反
let a = 123;
a= + a
a= -a;

```

### 4.自增自减

```javascript
自增	通过自增 在自身基础上增加指定数值
自减	通过自减 在自身基础上减去指定数值
一个变量自增自减后，原变量会立即改变

变量的值
let a = 1;

表达式的值
a++;	//后加加
++a;	//前加加
a--;
```

```javascript
let a = 1;
console.log(a++); // 输出 1
console.log(a);// 输出 2
a ++ 的值等于原变量的值  自增前的值
```

```javascript
let a = 1;
console.log(++ a); // 输出 2
console.log(a);// 输出 2
++ a 的值等于原变量自增后的值   

```

### 5.逻辑运算符

```javascript
js中为我们提供了三种运算符 
！非
&& 与
|| 或

if(!true){
	console.log(false);
}
if(let a >0 && a <100){

	//0 到100 之间
}
if(a = 1 || b = 2){
	//满足 一个条件即可
}
```

### 6.赋值运算符

```javascript
=  可以将右侧的值赋值给左侧变量
let a = 123;
let a = 123;
a += 1;
a= a +1;
```

### 8.关系运算符

```javascript
可以通过比较运算符进行比较两个值得关系
成立返回true ，否则返回false 
 》
 《
 》=
 《=
 ！=
 =
 
```

### 9.Unicode 编码表

```javascript
   Unicode 编码表   字符编码表
   字符串中使用转义字符输出 Unicode字符编码
   js 中 编码  :  console.log("\u  字符");
   console.log("\u2620");
   网页中 编码 ：&#编码
   计算器-》 查看-》 程序员 十进制  转换十六进制 就可以了
```

### 10.相等运算符

```javascript
比较2个值是否相等
相等返回true 否则返回false 
==

1==1
"123" ===123
类型判断完了再判断值 全等 === 


```

### 11.条件运算符

```javascript
三元运算符
？:
条件？语句1:语句2

let a = 10;
b = 20;
c= true;
a >b ?  c= true  :c = false
let max = a >b ? 1 : 2;
```

### 12.运算符

```javascript
，运算符
使用可以分割多个语句，可以声明多个变量
let a =1,b=2;
```

### 13 优先级

```javascript
从左往右运算 先括号 然后乘除  后加减
```



## 8.流程控制语句

### 1.通过流程控制可以控制程序流程

### 2.可以根据一定的条件执行

### 3.条件分支语句的分类

​	条件判断语句

​	条件分支语句

​	循环语句

​	例如： 

```sequence
李雷 -> 韩梅梅: Hello 梅梅, How are you? 
Note right of 韩梅梅: 韩梅梅心想 
韩梅梅 --> 李雷: I'm fine, thanks, and you?
```

### 	4.条件判断语句

​		使用条件判断语句可以在执行某个语句之前进行判断.成立执行，不成立不执行.

```javascript
语法 1
if(条件表达式){
	语句。。
}
var a =3;
if(a > 3){
	console.log(1);
}
```



```javascript
语法 2
if(条件表达式){
	语句。。
}else  {
	语句。。
}
var a =3;
if(a > 3){
	console.log(1);
}else  {
	console.log(5);
}
```



```javascript
语法 3
if(条件表达式){
	语句。。
}else if(条件表达式){
	语句。。
}
如果满足第一个条件，则不执行下面代码，如果不满足第一个条件则逐层执行下面判断依次类推

var a =3;
if(a > 3){
	console.log(1);
}else if(a > 5){
	console.log(5);
}
```

```javascript
可以弹出一个提示框，带有文本框
用户可以输入后，输入内容会作为该函数的返回值存储到变量中
var a = prompt();
```



### 	5.条件分支语句



```javascript
	switch
	
	语法 ：
	switch（条件表达式）{
		case 表达式：
		case 表达式：
		语句。。。
		break;
		
		case 表达式：
		语句。。。
		break;
		
		case 表达式：
		语句。。。
		break;
		
		default ：
		语句。。。
		break;
		
	
	}
	在执行的时候会依次将case后的表达式的值和
	switch 后的条件表达式进行全等比较
	从上到下进行比较
	比较为true 从当前case 处进行执行代码
	如果为false 则继续进行往下比较
```



```javascript
switch(true){
	case a >6 :
	console.log(a大于6);
	break;
}
```



### 	6.循环语句

#### 1while 循环

```javascript
反复执行 语句称为循环语句
通过循环语句可以反复执行一段代码多次
```

```javascript
while 循环
语法：
while (条件){
	语句。。
	（循环体）
}
判断条件是否为true 如果为true 则执行循环体，执行完毕后重新判断
终止循环方法 
break 终止循环 只能 在循环中使用 立即执行最近的循环语句
	 
			/*for(var i=0 ; i<5 ; i++){
				console.log("@外层循环"+i)
				for(var j=0 ; j<5; j++){
					break;
					console.log("内层循环:"+j);
				}
			}*/
			只是种植内层循环，不终止外层
			outer：  	//别名
			/*for(var i=0 ; i<5 ; i++){
				console.log("@外层循环"+i)
				for(var j=0 ; j<5; j++){
					break outer;
					console.log("内层循环:"+j);
				}
			}*/
			 终止外层 通过别名
			
continue  跳出当前当此循环
			/*for(var i=0 ; i<5 ; i++){
				
				if(i==2){
					continue;
				}
				
				console.log(i);
			}*/
具有三个步骤
// 1.初始化一个变量
var i = 0;
// 2.在循环中设置一个条件表达式
while(i < 10){

 //3.定义一个更新表达式
 i++;
}


```

#### 2do..while 循环

```javascript
do..while 循环
语法：
do{
	语句。。
}while(条件)
先执行语句一遍，完成之后 进行条件判断，符合条件继续执行
不符合退出循环

```

```javascript
假如投资年率为5% ，问从1000 到5000 需要多少年
var mon = 1000;
var i = 1;
while(mon <5000){
	mon = mon* 1.05;
	i ++;
}
console.log(i); 33
```

#### 3for循环

```javascript
for语句，也成为for 循环，也是一个循环语句
提供了专门的位置用来放置 三个表达式
1.初始化表达式
2.条件表达式
3.更新表达式

for（1初始化表达式;2条件表达式;4更新表达式;）{
	3语句。。
}
执行流程
	1.初始化表达式开始初始化变量 只执行一次
	2.执行条件表达式，进行判断
		如果为true ，则执行循环3语句
		如果为false，则终止循环
	3.执行更新表达式,执行完毕后继续执行重复流程
for(let i = 0 ;i<10;i++){
	console.log(i);
}

for 循环i

for(let i = 0 ;i<10;i++){
	// for(let j = 0 ;j<1 +i;j++){
	for(let j = 0 ;j<10-i;j++){
document.write("*&nbsp;&nbsp;&nbsp;");
	}	
		//输出一个换行
	document.write("<br />");
}
```

```javascript
1.打印1-100 之间的奇数之和
奇数 ： 不能被2整除的数就是奇数
let t = 0;
for(let i = 0 ;i<=100;i++){
	if(i%2 != 0){
		t = t +i;
	}
	console.log(i);
}
2.打印1-100 之间7 的倍数的个数之和
let t = 0;
let count = 0 ;
for(let i = 0 ;i<=100;i++){
	if(i%7 === 0){
		t = t +i;
		count ++;
	}
	console.log(i);
}
3.水仙花数
水仙花数是指一个3位数，它的每个位上的数字的3次
mu 幂之和等于它本身。
例如 13 + 53 + 33 = 153，请打印所有的水仙花数
1^3 + 5^3+ 3^3 = 153（百位1的幂 + 十位5的幂+个位 3的幂）

for(int i=100;i< 1000;i++) {
			int g = i/1%10;
			int s = i/10%10;
			int b = i/100;
			if(g*g*g + s*s*s + b*b*b==i) {
				System.out.print(i + " ");
			}
 }


4. 在页面中接收一个用户输入的数字，并判断该数是否是质数。
质数：只能被1和它自身整除的数，1不是质数也不是合数，质数必须是大于1的自然数。	
判断举例 ：
例如1个病人去医院检查：
    耳鼻喉科，内科 ，外科，妇科
    只有四个全部都盖章健康才属于健康
    如果有其中一个盖章不健康  就是属于不健康
	var num = prompt("请输入一个大于1的整数:");
			
			
			//判断这个值是否合法
			if(num <= 1){
				alert("该值不合法！");
			}else{
				
				//创建一个变量来保存当前的数的状态
				//默认当前num是质数
				var flag = true;
				
				//判断num是否是质数
				//获取2-num之间的数
				for(var i=2 ; i<num ; i++){
					//console.log(i);
					//判断num是否能被i整除
					if(num % i == 0){
						//如果num能被i整除，则说明num一定不是质数
						//设置flag为false
						flag = false;
					}
				}
				
				//如果num是质数则输出
				if(flag){
					alert(num + "是质数！！！");
				}else{
					alert("这个不是质数")
				}
				
				
			}	

```

```javascript
九九乘法表
	<script type="text/javascript">
			
			/*
			 * 1.打印99乘法表
			 * 	 1*1=1
			 * 	 1*2=2 2*2=4
			 * 	 1*3=3 2*3=6 3*3=9
			 * 	 1*4=4 2*4=8 3*4=12 4*4=16	
			 * 						....9*9=81
			 * 
			 * 2.打印出1-100之间所有的质数
			 */
			
			//创建外层循环，用来控制乘法表的高度
			for(var i=1 ; i<=9 ; i++ ){
				//创建一个内层循环来控制图形的宽度
				for(var j=1 ; j<=i ; j++){
					document.write("<span>"+j+"*"+i+"="+i*j+"</span>");
				}
				
				//输出一个换行
				document.write("<br />");
				
			}
			
			
		</script>
```



## 9.代码块

我们的程序是由 一条一条语句构成

```javascript
自上而下执行的

在js 中可以使用{} 来为语句进行分组

同一{} 中的语句称为一组语句，要么一起执行，

要么都不知晓

称为一个代码块 ,可以代码块可以不写；

只具有分组的作用，没有其他用途

例如：

 {

var a = 1;

console.log(a)



console.log(2)

}

a = a +1;

{} 外部可以使用
```

## 10 性能测试之计时器

```javascript
console.time("test"); // 需要字符串作为计时器的表示  开启
console.timeEnd("test"); // 终止计时器
```

# 五、对象

## 5.1 简介

```javascript
引用数据类型

​	Object

基本数据类型

​	string 类型

​	number 类型

​	boolean 类型

​	Null 类型

​	undefined类型


```

在js 中表示1个人的信息

```javascript
var name = "zs";

var age = 18 
```

使用基本数据类型的数据，创建的变量是独立的，不能成为一个整体

所以对象属于一种复合的数据类型，一个对象中可以保存多个不同的数据类型的属性

好处：关系明确，操作方便

## 5.2 对象分类

### 	5.2.1 内建对象

​	由es标准定义的对象，在任何的es的实现中都可以使用

比如： math string number boolean function object

### 	5.2.2 宿主对象

由js的运行环境提供的对象主要指浏览器提供的对象

Bom Dom 对象

例如console.log();

doucument.write();

### 	5.2.3 定义对象

由开发人员自己创建的对象

## 5.3 对象的基本操作

### 5.3.1 创建对象

```javascript
var obj = new Object(); // new 调用的函数，是构造函数
用来专门创建对象的函数

```

### 5.3.2 对象操作属性



```javascript
在对象中保存的值成为属性
像对象添加属性
语法：
对象。属性名= 属性值；
```

```javascript
//向obj添加name 属性
obj.name = "zhangsan";
obj.age = 13;
```

```javascript
读取对象中的属性
如果没有此属性，不会报错，会返回undefind
语法：
对象。属性名称
console.log(obj.name);
```

```javascript
修改对象的属性值
语法：
对象。属性名= 属性值；
//向obj修改name 属性
obj.name = "zhangsan2";
```

```javascript
删除对象的属性值
语法：
delete 对象。属性名

delete obj.name 

```

### 5.3.3 对象属性名和属性值

```javascript
// 属性名不强制要求遵守标识符的规范
var obj = new Object();
obj.name = "sun";
//name 属性名  sun 属性值
```



```javascript
如果使用特殊的属性名
添加语法  ：对象【"属性名"】 = 属性值
obj["123"] = 345;
读取
var a = obj["123"];
```



```javascript
属性值
	js 的属性值  可以是任意的数据类型
	obj.t = "123";
	obj.t =	123;
	obj.t = true;
	obj.t =	null;
	obj.t = undefined;
	obj.t =new Object();
	
```



### 5.3.4 检查对象对象

```javascript
in 运算
通过该运算检查一个对象中是否存在指定的属性
存在返回true 否则返回false
语法：
“属性名” in 对象
"test2" in obj

```

### 5.3.5 基本数据类型和引用数据类型

```javascript
基本数据类型
string number boolean null undefined
引用数据类型
object
```

```javascript
基本数据类型和引用数据类型

引用数据类型值改变 
	每次new 的时候会创建 在堆内存 中开辟地址用于存放新的对象
	修改一个变量  会影响其他的
	#保存的是	堆内存		中的地址
基本数据类型值改变
	会复制一份在  栈内存中
	修改一个变量  不会影响其他的
	#保存的是   栈内存  	中的值
```



```javascript
var obj = new Ojbect( );
obj.name = "sunwukong";
var obj2 = obj;
obj.name = "zhubajie";
console.log(obj.name); // 输出"zhubajie";
console.log(obj2.name);// 输出"zhubajie";
```



```javascript
var a = 1;
var b = a;
a++;
console.log(a);// 输出2
console.log(b);// 输出1
```

### 5.3.6 对象字面量

```javascript
使用 对象字面量来创建一个对象
var obj = {};
等同于 
var obj = new Object();
console.log(typeof obj ); // 输出object
使用 对象字面量，可以在创建对象的时候，直接指定对象中的属性
语法：
{属性名：属性值，属性名：属性值，属性名：属性值。。}
var obj = {name :123,age :18,test2 :obj2};
特殊属性需要加引号
例如：
"@aaname"
```



# 六、函数

## 6.1 函数简介

```javascript
函数 ：
函数也是一个对象
函数中可以封装功能（代码）
在需要的时候可以执行这些代码

保存代码  在需要的时候调用
创建方式3种
#创建函数对象 function

var fun = new Function();
封装的代码不会立即执行，
调用函数的时候 进行执行语法
函数对象（）
fun（）；
{
console.log("第一行");
console.log("第二行");
console.log("第三行");
}
var fun = new Function(
"console.log(1);"
);
console.log(fun());
```

  



```javascript
#使用函数声明来创建一个函数
语法：
function 函数名(形参1，形参1，形参1，。。){
	语句。。。
}
function fun2(){
		console.log(2);
	}
	fun2();
```





```javascript
#使用函数表达式进行创建一个函数
var 函数名 = function(){

}
var fun3 = function(){
		console.log(3);
	}
	fun3();
```



## 6.2 函数的参数

```javascript
语法：

function 函数名(形参1，形参1，形参1，。。){
	语句。。。
}
在 调用函数的时候，可以指定实参 实际参数
实参将会赋值给函数中对应的形参
不会检查实参的类型所以要注意会接手到非法参数
需要对参数进行类型检查
不会检查实参的数量
如果实参个数不够就是undefined
sum(实参1，实参2);

var sum = function(a,b){
		console.log(a +b);
	}
	sum(1,2);
```



## 6.3 函数的返回值

### 	6.3.1 返回值

```javascript
语法：
return 值
如果return 语句中不跟任何值 会返回undefined
函数不写return 也会返回 undefined

var sum = function(a,b){
		return a +b;
	}
var sum = sum(1,2);

var result = alert(1);
console.log(result);
返回 undefined 

```



### 	6.3.2 实参可以是任意值

```javascript
//实参可以是任意数据类型，也可以是一个对象
// 参数过多，可以将参数封装到对象中，
创建一个对象，传递到函数中
var obj ={
	name : "zs",
	age : 18,
	address : "hgs"
}
 function sum(obj){
		console.log(obj.name +"--"+obj.age +"--"+obj.age);
	}
	sum(obj);
	// sum(obj); 函数对象 相当于直接使用函数对象
	// sum(obj()); 调用函数 相当于使用函数的返回值
	// 举例 ：店员 卖冰激凌
	有冰激凌 机器 可以卖冰激凌
	sum(obj());  	卖给顾客冰激凌
	sum(obj); 		卖给顾客冰激凌机器 
	//实参可以是任意数据类型，也可以是一个函数
	funcion fun(a){
		console.log(a);
	}
	fun(sum);
	//将匿名函数传递给函数执行
	fun(function(){alert("123");});
```



### 	6.3.3 返回值得类型

```javascript
使用break 可以退出当前的循环 for 循环
使用continue 跳出当前次数循环 for 循环
return 后面的所有语句都不执行了 结束整个函数
函数返回值可以是任意数据类型 也可以是一个对象
function fun2(){
	var obj = {name :"zs";}
	return obj;
}
var a = fun2();
console.log(a.name);
function fun3(){
	function fun4(){
	 console.log(4);
	}
	fun4();
}
cun3();

function fun3(){
	function fun4(){
	 console.log(4);
	}
 return 	fun4();
}
///////////////////////
var c4 = cun3();// 调取fun4
a();// 调取fun4
fun3()(); // 调取fun4
///////////////////////
```



## 6.4 立即执行函数

```javascript
立即执行函数 
创建完成之后 立即执行 调用一次后就不用了
//函数调取方法 函数对象()
(function(){
	 console.log(4);
})
// 函数调用完了，立即执行 只会执行一次
// 没有变量保存它 
(function(){
	 console.log(4);
})();

(function(a,b){
	 console.log(a );
	 console.log(b );
})(123,456);
//123
//456
```



## 6.5 对象的属性方法

枚举

```javascript
var obj = new Object();
obj.name  = "sunwuk";
obj.age = 18;
//对象的属性值可以是任何的数据类型，也可以是个函数
obj.sayname = function(){
	console.log(obj.name);
}
obj.sayname();
```



```javascript
var obj = {
	name : "sun",
	age : 18,
	add : "hgs"
}
//当我们拿到一个对象后，不知道里面的属性方法。
我们如果想使用 ，就需要枚举对象中的属性
使用for 。。 in 语句
语法
    for(var 变量 in 对象){

    }
	对象中有多少个属性，就循环几次循环体
	每次执行时候，会把对象中的属性名称赋值给变量
for(var n in obj){
	console.log(n); // 变量名称
	console.log(obj[n]); // 变量名称 对应的值
}

```



## 6.6 全局作用域

作用域 ：Scope 

区域 作用范围  一个变量的作用的范围   js中一共有2个作用域

1.全局作用域

​	直接在script 标签的js 代码，都在全局作用域

​	在页面打开时候创建，页面关闭时候销毁

​	在全局作用域中，有一个全局对象window（浏览器的窗口，由浏览器创建）我们可以直接调用使用

​	console.log(window) // [object window]

创建的变量都会作为window 对象的属性保存

```javascript
变量的声明提前
	使用var 关键字声明的变量，会在所有代码执行之前被声明
	console.log(a);
	var a  = 123;
	//输入undefined
	  a  = 123;
	  console.log(a);
	  // 会报错
```

```javascript
使用函数声明函数创建的函数  会在所有的代码执行之前就被创建
使用函数表达式创建的函数，不会声明提前，所以会报错 
fun();// 输出1
fun2();// 报错
function fun(){
console.log(1);
}
var fun2 = function(){
console.log(1);
}

```

2.函数作用域

## 6.7 函数作用域

作用域 ：Scope 

区域 作用范围  一个变量的作用的范围   js中一共有2个作用域

1.全局作用域

2.函数作用域

```javascript
函数作用域
	离不开函数 调用函数时候创建函数作用域
	执行完毕函数，函数作用域销毁  
	每调用一次，就会创建一次，之间互相独立的
	函数作用域是局部的，可以访问全局作用域的变量
	function fun(){}
	
	var a = 10;
	function fun(){
		console.log(a); // 可以访问
		var b = 3;
	}
	console.log(b); // 不能访问报错
///////////////
先找作用域中的，如果没有则向上查找，直至找到全局作用域，
如果还没有，就报错  referenceerror 
应用错误 is not defined 
		var a = 10;
	function fun(){
	var a = 20;
		console.log(a); // 输出 20
		console.log(window.a);//函数中访问全局的 加 window
		 
	}
	
	
```



## 6.8 debug 调试

```javascript
1. debug js 中
2. f12 调试
	断点
	右键变量添加监控 add to watch 
查看项目内存结构
```



## 6.9 this 指向 

```javascript
解析器调用函数时候，每次都会向函数内部传递一个隐含的参数
这个隐含参数就是this
指向的是this 对象， 称为函数执行的上下文对象
根据我们的函数调用方式不同，this 会指向不同的对象
	1.以函数的形式 this 永远是window
	2.以方法的形式 this 就是调用方法的对象
function fun(a,b){
	console.log(this);//object window
    
}
fun(12,34);
var obj = {name : "swk",
	sayname :fun
}
console.log(obj.sayname == fun);
obj.sayName();// object object  obj
fun() // object window 	window 

```



```javascript
var name  = "全局";
function fun(){
	console.log(name);
}
var obj = {
	name : "zs",
	say :fun
}
var obj2 = {
	name : "zs2",
	say :fun
}
obj.say();
obj2.say();
这样输出的是全局
我们想输出的是每个对象中的名字，而不是 全局name
解决方法  更改 fun
function fun(){
	console.log(this.name);
}

```



```javascript
this 的情况区分

1当以函数的形式调用的时候，this 是window
2当以方法的形式调用的时候，谁调用方法this 就是谁
3当以构造函数形式调用时候，this就是新创建的对象
```



## 6.10 使用工厂方法创建对象

```javascript
var obj = {
	name : "zs",
	age : 18,
	say() :function(){
		console.log(this.name)
	}
}
var obj2 = {
	name : "zs2",
	age : 18,
	say() :function(){
		console.log(this.name)
	}
}
var obj3 = {
	name : "zs3",
	age : 18,
	say :function(){
		console.log(this.name)
	}
}

提取到一个方法函数中
使用工厂模式进行创建对象
通过该方法可以大批量创建对象
function createP(name,age){
	// 创建新的对象
	var obj = new Object();
	// 添加属性
	obj.name : name,
	obj.age : age,
	obj.say = function(){
		console.log(this.name)
	}
	return obj;
	
}
var obj2 = createP("zbj",18);
var obj3 = createP("bgj",18);
var obj4 = createP("zzj",18);

```

## 

```javascript
通过该方法可以大批量创建对象
function createDog(name,age){
	// 创建新的对象
	var obj = new Object();
	// 添加属性
	obj.name : name,
	obj.age : age,
    obj.wang : "wangwang",
	obj.saywang = function(){
		console.log(this.wang)
	}
	return obj;
	
}
var dog = createP("hashiqi",1);
dog.saywang();
//使用工厂方法创建的对象都是使用函数object 所以创建的是object类型导致我们无法区分不同类型的对象
```



## 6.11 构造函数

```javascript
//创建一个构造函数，专门创建person
//构造函数就是一个普通的函数 ，
//创建方式和普通函数一样
//构造函数和普通函数的区别在于调用方式的不同
// 普通函数直接调用
//var a = Person();
// 构造函数调取
//var per = new Person();
// 执行流程 1 4 
// 1.创建新的对象  new
// 2.将新建的对象设置为函数中的this
// 3.执行函数中的 逐行代码 （只有这一步我们可以看见）
// 4.将新建的对象作为返回值返回
function Person(){
    //2. 当前的this 就是 新new Person 的this
	this.name = "";
    this.age = 18;
}
var per = new Person();
var obj2 = new Dog();
```

```javascript
// 使用同一个构造函数创建的对象，我们称为一类对象
// 也称为一个类 将通过一个构造函数创建的对象，称为是该类的实例
function Person(name, age){
    //2. 当前的this 就是 新new Person 的this
	this.name = name ;
    this.age = age;
    this.sayName = function(){
        console.log(this.name);
    }
}
var per1 = new Person("孙悟空",11);
var per2 = new Person("玉兔精",3);
var per3 = new Person("白骨精",4);
var dog = new Dog();
console.log(per1);
console.log(dog);

// 使用 instanceof 可以检查一个对象是否是一个类的实例

// 语法 ： 对象 instanceof 构造函数
// 是 返回true
console.log(per1 instanceof Person);
所有的对象都是object 的后代
// true 
console.log(per1 instanceof object);
// true
console.log(per1 instanceof object);
```







```javascript
this 的情况区分

1当以函数的形式调用的时候，this 是window
2当以方法的形式调用的时候，谁调用方法this 就是谁
3当以构造函数形式调用时候，this就是新创建的对象
```





```javascript
项目的迭代升级 项目是不断迭代的过程
/*
	问题 ： 
 *  创建一个Person构造函数
 * 	- 在Person构造函数中，为每一个对象都添加了一个sayName方法，
 * 		目前我们的方法是在构造函数内部创建的，
 * 			也就是构造函数每执行一次就会创建一个新的sayName方法
 * 		也是所有实例的sayName都是唯一的。
 * 		这样就导致了构造函数执行一次就会创建一个新的方法，
 * 			执行10000次就会创建10000个新的方法，而10000个方法都是一摸一样的
 * 			这是完全没有必要，完全可以使所有的对象共享同一个方法
*/
function Person(name, age){
    
	this.name = name ;
    this.age = age;
    this.sayName = function(){
        console.log(this.name);
    }
}
// 创建per 实例

var per = new Person("孙悟空",11);
var per2 = new Person("玉兔精",3);
per.sayName();
per2.sayName();
```





```javascript
//解决办法 ： 将当前的sayhello定义到全局作用域之中
//可以太高效率，解决内存的占用率
// 确定定义全局的，容易污染全局作用域的命名空间 不安全
// 直接引出原型 protocol 
 function sayNames(){
        console.log(this.name);
    }
function Person(name, age){
    
	this.name = name ;
    this.age = age;
    this.sayName =sayNames;
}

// 创建per 实例

var per = new Person("孙悟空",11);
var per2 = new Person("玉兔精",3);
per.sayName();
per2.sayName();

// 直接引出原型 protocol 
// 接6.12
// 直接引出原型 protocol 
// 向原型中添加公共方法
Person.prototype.sayName = function(){
     console.log(this.name);
}
所有对象都可以访问到，并且不会污染全局环境
```



## 6.12 原型对象

原型对象  原型链

```javascript
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<script type="text/javascript">
			/*
			 * 原型 prototype
			 * 
			 * 	我们所创建的每一个函数，解析器都会向函数中添加一个属性prototype
			 * 		这个属性对应着一个对象，这个对象就是我们所谓的原型对象
			 * 	如果函数作为普通函数调用prototype没有任何作用
			 * 	当函数以构造函数的形式调用时，它所创建的对象中都会有一个隐含的属性，
			 * 		指向该构造函数的原型对象，我们可以通过__proto__来访问该属性
			 * 
			 * 	原型对象就相当于一个公共的区域，所有同一个类的实例都可以访问到这个原型对象，
			 * 		我们可以将对象中共有的内容，统一设置到原型对象中。
			 * 
			 * 当我们访问对象的一个属性或方法时，它会先在对象自身中寻找，如果有则直接使用，
			 * 	如果没有则会去原型对象中寻找，如果找到则直接使用
			 * 
			 * 以后我们创建构造函数时，可以将这些对象共有的属性和方法，统一添加到构造函数的原型对象中，
			 * 	这样不用分别为每一个对象添加，也不会影响到全局作用域，就可以使每个对象都具有这些属性和方法了
			 */
			
			function MyClass(){
				
			}
			
			//向MyClass的原型中添加属性a
			MyClass.prototype.a = 123;
			
			//向MyClass的原型中添加一个方法
			MyClass.prototype.sayHello = function(){
				alert("hello");
			};
			
			var mc = new MyClass();
			
			var mc2 = new MyClass();
			
			//console.log(MyClass.prototype);
			//console.log(mc2.__proto__ == MyClass.prototype);
			
			//向mc中添加a属性
			mc.a = "我是mc中的a";
			
			//console.log(mc2.a);
			
			mc.sayHello();
			
			
		</script>
	</head>
	<body>
	</body>
</html>

```





```javascript
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<script type="text/javascript">
			
			/*
			 * 创建一个构造函数
			 */
			function MyClass(){
				
			}
			
			//向MyClass的原型中添加一个name属性
			MyClass.prototype.name = "我是原型中的名字";
			
			var mc = new MyClass();
			mc.age = 18;
			
			//console.log(mc.name);
			
			//使用in检查对象中是否含有某个属性时，如果对象中没有但是原型中有，也会返回true
			//console.log("name" in mc);
			
			//可以使用对象的hasOwnProperty()来检查对象自身中是否含有该属性
			//使用该方法只有当对象自身中含有属性时，才会返回true
			//console.log(mc.hasOwnProperty("age"));
			
			//console.log(mc.hasOwnProperty("hasOwnProperty"));
			
			/*
			 * 原型对象也是对象，所以它也有原型，
			 * 	当我们使用一个对象的属性或方法时，会现在自身中寻找，
			 * 		自身中如果有，则直接使用，
			 * 		如果没有则去原型对象中寻找，如果原型对象中有，则使用，
			 * 		如果没有则去原型的原型中寻找,直到找到Object对象的原型，
			 * 		Object对象的原型没有原型，如果在Object原型中依然没有找到，则返回undefined
			 */
			
			//console.log(mc.__proto__.hasOwnProperty("hasOwnProperty"));
			
			//console.log(mc.__proto__.__proto__.hasOwnProperty("hasOwnProperty"));
			
			//console.log(mc.__proto__.__proto__.__proto__);
			
			//console.log(mc.hello);
			
			//console.log(mc.__proto__.__proto__.__proto__)
			
		</script>
	</head>
	<body>
	</body>
</html>

```



## 6.13 toString 方法

```javascript
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<script type="text/javascript">
			
			function Person(name , age , gender){
				this.name = name;
				this.age = age;
				this.gender = gender;
			}
			
			//修改Person原型的toString
			Person.prototype.toString = function(){
				return "Person[name="+this.name+",age="+this.age+",gender="+this.gender+"]";
			};
			
			
			//创建一个Person实例
			var per = new Person("孙悟空",18,"男");
			var per2 = new Person("猪八戒",28,"男");
			
			//当我们直接在页面中打印一个对象时，事件上是输出的对象的toString()方法的返回值
			//如果我们希望在输出对象时不输出[object Object]，可以为对象添加一个toString()方法
			//Person[name=孙悟空,age=18,gender=男]
			/*per.toString = function(){
				return "Person[name="+this.name+",age="+this.age+",gender="+this.gender+"]";
			};*/
			
			var result = per.toString();
			//console.log("result = " + result);
			//console.log(per.__proto__.__proto__.hasOwnProperty("toString"));
			console.log(per2);
			console.log(per);
			
			
		</script>
	</head>
	<body>
	</body>
</html>

```



## 6.14 垃圾回收机制

GC 垃圾回收

```javascript
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<script type="text/javascript">
			/*
			 * 垃圾回收（GC）
			 * 	- 就像人生活的时间长了会产生垃圾一样，程序运行过程中也会产生垃圾
			 * 		这些垃圾积攒过多以后，会导致程序运行的速度过慢，
			 * 		所以我们需要一个垃圾回收的机制，来处理程序运行过程中产生垃圾
			 *  - 当一个对象没有任何的变量或属性对它进行引用，此时我们将永远无法操作该对象，
			 * 		此时这种对象就是一个垃圾，这种对象过多会占用大量的内存空间，导致程序运行变慢，
			 * 		所以这种垃圾必须进行清理。
			 * 	- 在JS中拥有自动的垃圾回收机制，会自动将这些垃圾对象从内存中销毁，
			 * 		我们不需要也不能进行垃圾回收的操作
			 * 	- 我们需要做的只是要将不再使用的对象设置null即可
			 * 
			 */
			var obj = new Object();
			
			//对对象进行各种操作。。。。
			
			
			obj = null;
			
			
			
		</script>
	</head>
	<body>
	</body>
</html>

```

七、 数组

八、