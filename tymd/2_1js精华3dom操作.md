

[toc]

# 一、Dom简介

## 1什么是DOM

```javascript

• DOM，全称Document Object Model文档对象模型。
• JS中通过DOM来对HTML文档进行操作。只要理解了DOM就可以随
心所欲的操作WEB页面。
• 文档
	– 文档表示的就是整个的HTML网页文档
• 对象
	– 对象表示将网页中的每一个部分都转换为了一个对象。
• 模型
	– 使用模型来表示对象之间的关系，这样方便我们获取对象。
```

## 2Dom 干什么的?

Dom操作网页的

## 3Dom好处 

把网页的每个点每一部分 转换为对象，可以以纯面向对象的方式操作对象，达到操作页面的效果。

## 4特点 

操作方便



## 5模型 

​	树状关系

​	关系图

​	节点

```javascript
节点Node，是构成我们网页的最基本的组成部分，网页中的
每一个部分都可以称为是一个节点。
• 比如：html标签、属性、文本、注释、整个文档等都是一个节
点。
• 虽然都是节点，但是实际上他们的具体类型是不同的。
• 比如：标签我们称为元素节点、属性称为属性节点、文本称为
文本节点、文档称为文档节点。
• 节点的类型不同，属性和方法也都不尽相同。
```

节点《=》 对象

```javascript
– 文档节点：整个HTML文档
– 元素节点：HTML文档中的HTML标签
– 属性节点：元素的属性
– 文本节点：HTML标签中的文本内容
```



```javascript
例如：
<div class='bm-dynamic-layer' id='one'>123</div>
– 文档节点：整个HTML文档
	全部的html页面内容
– 元素节点：HTML文档中的HTML标签
	<div class='bm-dynamic-layer' id='one'>123</div>
– 属性节点：元素的属性
	id='one'
	class='bm-dynamic-layer'
– 文本节点：HTML标签中的文本内容
	123

```

代码 

```javascript
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<body>
		<button id="btn">我是一个按钮</button>
		<script type="text/javascript">
			
			/*
			 * 浏览器已经为我们提供 文档节点 对象这个对象是window属性
			 * 	可以在页面中直接使用，文档节点代表的是整个网页
			 */
			//console.log(document);
			
			//获取到button对象
			var btn = document.getElementById("btn");
			
			//修改按钮的文字
			btn.innerHTML = "I'm Button";
			
			
		</script>
	</body>
</html>

```

# 二、js事件

```javascript
事件
• 事件，就是文档或浏览器窗口中发生的一
些特定的交互瞬间。
• JavaScript 与 HTML 之间的交互是通过事
件实现的。
• 对于 Web 应用来说，有下面这些代表性的
事件：点击某个元素、将鼠标移动至某个
元素上方、按下键盘上某个键，等等。
• 处理事件
在事件对应的属性中设置js代码，当事件触发执行js代码

dom event
```



```javascript
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<body>
		<!--
			我们可以在事件对应的属性中设置一些js代码，
				这样当事件被触发时，这些代码将会执行 
			这种写法我们称为结构和行为耦合，不方便维护，不推荐使用	
		-->
		<!--<button id="btn" onmousemove="alert('你点我干嘛！');">我是一个按钮</button>-->
		<button id="btn">我是一个按钮</button>
		<script type="text/javascript">
			
			/*
			 * 事件，就是用户和浏览器之间的交互行为，
			 * 	比如：点击按钮，鼠标移动、关闭窗口。。。
			 */ 
			//获取按钮对象
			var btn = document.getElementById("btn"); 
			/*
			 * 可以为按钮的对应事件绑定处理函数的形式来响应事件
			 * 	这样当事件被触发时，其对应的函数将会被调用
			 */
			
			//绑定一个单击事件
			//像这种为单击事件绑定的函数，我们称为单击响应函数
			btn.onclick = function(){
				alert("你还点~~~");
			};
			
			
		</script>
	</body>
</html>

```



# 三、文档加载

```javascript
/*
	 * 浏览器在加载一个页面时，是按照自上向下的顺序加载的，
	 * 	读取到一行就运行一行,如果将script标签写到页面的上边，
	 * 	在代码执行时，页面还没有加载，页面没有加载DOM对象也没有加载
	 * 	会导致无法获取到DOM对象
	 * 	onload事件会在整个页面加载完成之后才触发
	 window.onload = function(){}
	 * 	该事件对应的响应函数将会在页面加载完成之后执行，
	 * 	这样可以确保我们的代码执行时所有的DOM对象已经加载完毕了
*/
			
```

页面加载后在进行js 加载 可以提升效率

# 四、Dom操作-获取元素节点

## 4.1.查询方法

```javascript
1. getElementById()
2. getElementsByTagName()
3. getElementsByName()
```

详解

```javascript
通过document对象调用
1. getElementById()
– 通过id属性获取一个元素节点对象
	<div><button id="btn01"> bj节点</button></div>
	var btn01 = document.getElementById("btn01");
2. getElementsByTagName()
– 通过标签名获取一组元素节点对象
	<div><button id="btn02">查找所有li节点</button></div>
	var lis = document.getElementsByTagName("li");
	for(var i=0 ; i<lis.length ; i++){
						alert(lis[i].innerHTML);
	}
3. getElementsByName()
– 通过name属性获取一组元素节点对象
//查找name=gender的所有节点
<div class="inner">
	gender:
	<input class="hello" type="radio" name="gender" value="male"/>
	Male
	<input class="hello" type="radio" name="gender" value="female"/>
	Female
	<br>
	<br>
	name:
	<input type="text" name="name" id="username" value="abcde"/>
	</div>
	var inputs = document.getElementsByName("gender");
for(var i=0 ; i<lis.length ; i++){
    
						alert(inputs[i].className);
	}
/*
* 如果需要读取元素节点属性，
* 直接使用 元素.属性名
* 例子：元素.id 元素.name 元素.value
* 注意：class属性不能采用这种方式，
* 读取class属性时需要使用 元素.className
*/
	
```

## 4.2.图片切换案例

```javascript
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<style type="text/css">
			
			*{
				margin: 0;
				padding: 0;
			}
			
			#outer{
				width: 500px;
				margin: 50px auto;
				padding: 10px;
				background-color: greenyellow;
				/*设置文本居中*/
				text-align: center;
			}
		</style>
		
		<script type="text/javascript">
			
			window.onload = function(){
				
				/*
				 * 点击按钮切换图片
				 */
				
				//获取两个按钮
				var prev = document.getElementById("prev");
				var next = document.getElementById("next");
				
				/*
				 * 要切换图片就是要修改img标签的src属性
				 */
				
				//获取img标签
				var img = document.getElementsByTagName("img")[0];
				
				//创建一个数组，用来保存图片的路径
				var imgArr = ["img/1.jpg" , "img/2.jpg" , "img/3.jpg" , "img/4.jpg" ,"img/5.jpg"];
				
				//创建一个变量，来保存当前正在显示的图片的索引
				var index = 0;
				
				//获取id为info的p元素
				var info = document.getElementById("info");
				//设置提示文字
				info.innerHTML = "一共 "+imgArr.length+" 张图片，当前第 "+(index+1)+" 张";
				
				
				//分别为两个按钮绑定单击响应函数
				prev.onclick = function(){
					
					/*
					 * 切换到上一张，索引自减
					 */
					index--;
					
					//判断index是否小于0
					if(index < 0){
						index = imgArr.length - 1;
					}
					
					img.src = imgArr[index];
					
					//当点击按钮以后，重新设置信息
					info.innerHTML = "一共 "+imgArr.length+" 张图片，当前第 "+(index+1)+" 张";
				};
				
				next.onclick = function(){
					
					/*
					 * 切换到下一张是index自增
					 */
					index++;
					
					if(index > imgArr.length - 1){
						index = 0;
					}
					
					//切换图片就是修改img的src属性
					//要修改一个元素的属性 元素.属性 = 属性值
					img.src = imgArr[index];
					
					//当点击按钮以后，重新设置信息
					info.innerHTML = "一共 "+imgArr.length+" 张图片，当前第 "+(index+1)+" 张";
					
				};
				
				
			};
			
			
		</script>
	</head>
	<body>
		<div id="outer">
			
			<p id="info"></p>
			
			<img src="img/1.jpg" alt="冰棍" />
			
			<button id="prev">上一张</button>
			<button id="next">下一张</button>
			
		</div>
	</body>
</html>

```

# 五、Dom操作-获取元素节点的子节点

##  5.1.获取方法

```javascript
1. getElementsByTagName()
– 方法，返回当前节点的指定标签名后代节点
2. childNodes
– 属性，表示当前节点的所有子节点
3. firstChild
– 属性，表示当前节点的第一个子节点
4. lastChild
– 属性，表示当前节点的最后一个子节点
```



## 5.2.查询指定元素下的节点

```javascript
//为id为btn04的按钮绑定一个单击响应函数
				var btn04 = document.getElementById("btn04");
				btn04.onclick = function(){
					
					//获取id为city的元素
					var city = document.getElementById("city");
					
					//查找#city下所有li节点
					var lis = city.getElementsByTagName("li");
					// 查找window 下的list var lis = document.getElementsByTagName("li");
					for(var i=0 ; i<lis.length ; i++){
						alert(lis[i].innerHTML);
					}
					
				};
```

## 5.3 childNodes

```javascript
//为id为btn05的按钮绑定一个单击响应函数
				var btn05 = document.getElementById("btn05");
				btn05.onclick = function(){
					//获取id为city的节点
					var city = document.getElementById("city");
					//返回#city的所有子节点
					/*
					 * childNodes属性会获取包括文本节点在呢的所有节点
					 * 根据DOM标签标签间空白也会当成文本节点
					 * 注意：在IE8及以下的浏览器中，不会将空白文本当成子节点，
					 * 	所以该属性在IE8中会返回4个子元素而其他浏览器是9个
					 */
					var cns = city.childNodes;
					
					//alert(cns.length);
					
					/*for(var i=0 ; i<cns.length ; i++){
						alert(cns[i]);
					}*/
					
					/*
					 * children属性可以获取当前元素的所有子元素
					 */
					var cns2 = city.children;
					alert(cns2.length);
				};
```

## 5.4 firstChild 和lastChild



```javascript
	//为id为btn06的按钮绑定一个单击响应函数
				var btn06 = document.getElementById("btn06");
				btn06.onclick = function(){
					//获取id为phone的元素
					var phone = document.getElementById("phone");
					//返回#phone的第一个子节点
					//phone.childNodes[0];
					//firstChild可以获取到当前元素的第一个子节点（包括空白文本节点）
					var fir = phone.firstChild;
					var las = phone.lastChild;
					//firstElementChild获取当前元素的第一个子元素
					/*
					 * firstElementChild不支持IE8及以下的浏览器，
					 * 	如果需要兼容他们尽量不要使用
					 */
					//fir = phone.firstElementChild;
					
					alert(fir);
				};
```



# 六、Dom操作-获取父节点和兄弟节点

## 6.1获取方法

```javascript
通过具体的节点调用
1. parentNode
– 属性，表示当前节点的父节点
2. previousSibling
– 属性，表示当前节点的前一个兄弟节点
3. nextSibling
– 属性，表示当前节点的后一个兄弟节点
```



## 6.2 parentNode父节点



```javascript
	/*
			 * 定义一个函数，专门用来为指定元素绑定单击响应函数
			 * 	参数：
			 * 		idStr 要绑定单击响应函数的对象的id属性值
			 * 		fun 事件的回调函数，当单击元素时，该函数将会被触发
			 */
			function myClick(idStr , fun){
				var btn = document.getElementById(idStr);
				btn.onclick = fun;
			}
			
			//为id为btn07的按钮绑定一个单击响应函数
				myClick("btn07",function(){
					
					//获取id为bj的节点
					var bj = document.getElementById("bj");
					
					//返回#bj的父节点
					var pn = bj.parentNode;
					
					alert(pn.innerHTML);
					
					/* innerHTML 获取元素内部的html
					 * innerText
					 * 	- 该属性可以获取到元素内部的文本内容
					 * 	- 它和innerHTML类似，不同的是它会自动将html去除
					 */
					//alert(pn.innerText);
					
					
				});
				
```



## 6.3 previousSibling前一个兄弟节点



## 6.4nextSibling后一个兄弟节点





```javascript
//为id为btn08的按钮绑定一个单击响应函数
				myClick("btn08",function(){
					
					//获取id为android的元素
					var and = document.getElementById("android");
					
					//返回#android的前一个兄弟节点（也可能获取到空白的文本）
					var ps = and.previousSibling;
					
					//previousElementSibling获取前一个兄弟元素，IE8及以下不支持
					//var pe = and.previousElementSibling;
					
					alert(ps);
					
				});
```

补充

```javascript
//读取#username的value属性值
				myClick("btn09",function(){
					//获取id为username的元素
					var um = document.getElementById("username");
					//读取um的value属性值
					//文本框的value属性值，就是文本框中填写的内容
					alert(um.value);
				});
				
				
				//设置#username的value属性值
				myClick("btn10",function(){
					//获取id为username的元素
					var um = document.getElementById("username");
					
					um.value = "今天天气真不错~~~";
				});
				
				
				//返回#bj的文本值
				myClick("btn11",function(){
					
					//获取id为bj的元素
					var bj = document.getElementById("bj");
					
					//alert(bj.innerHTML);
					//alert(bj.innerText);
					
					//获取bj中的文本节点
					/*var fc = bj.firstChild;
					alert(fc.nodeValue);*/
					
					alert(bj.firstChild.nodeValue);
```

## 6.5案例 全选非全选

```javascript
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
<title>全选练习</title>
<script type="text/javascript">

	window.onload = function(){
		
		
		//获取四个多选框items
		var items = document.getElementsByName("items");
		//获取全选/全不选的多选框
		var checkedAllBox = document.getElementById("checkedAllBox");
		
		/*
		 * 全选按钮
		 * 	- 点击按钮以后，四个多选框全都被选中
		 */
		
		//1.#checkedAllBtn
		//为id为checkedAllBtn的按钮绑定一个单击响应函数
		var checkedAllBtn = document.getElementById("checkedAllBtn");
		checkedAllBtn.onclick = function(){
			
			
			//遍历items
			for(var i=0 ; i<items.length ; i++){
				
				//通过多选框的checked属性可以来获取或设置多选框的选中状态
				//alert(items[i].checked);
				
				//设置四个多选框变成选中状态
				items[i].checked = true;
			}
			
			//将全选/全不选设置为选中
			checkedAllBox.checked = true;
			
			
		};
		
		/*
		 * 全不选按钮
		 * 	- 点击按钮以后，四个多选框都变成没选中的状态
		 */
		//2.#checkedNoBtn
		//为id为checkedNoBtn的按钮绑定一个单击响应函数
		var checkedNoBtn = document.getElementById("checkedNoBtn");
		checkedNoBtn.onclick = function(){
			
			for(var i=0; i<items.length ; i++){
				//将四个多选框设置为没选中的状态
				items[i].checked = false;
			}
			
			//将全选/全不选设置为不选中
			checkedAllBox.checked = false;
			
		};
		
		/*
		 * 反选按钮
		 * 	- 点击按钮以后，选中的变成没选中，没选中的变成选中
		 */
		//3.#checkedRevBtn
		var checkedRevBtn = document.getElementById("checkedRevBtn");
		checkedRevBtn.onclick = function(){
			
			//将checkedAllBox设置为选中状态
			checkedAllBox.checked = true;
			
			for(var i=0; i<items.length ; i++){
				
				//判断多选框状态
				/*if(items[i].checked){
					//证明多选框已选中，则设置为没选中状态
					items[i].checked = false;
				}else{
					//证明多选框没选中，则设置为选中状态
					items[i].checked = true;
				}*/
				
				items[i].checked = !items[i].checked;
				
				//判断四个多选框是否全选
				//只要有一个没选中则就不是全选
				if(!items[i].checked){
					//一旦进入判断，则证明不是全选状态
					//将checkedAllBox设置为没选中状态
					checkedAllBox.checked = false;
				}
			}
			
			//在反选时也需要判断四个多选框是否全都选中
			
			
			
		};
		
		/*
		 * 提交按钮：
		 * 	- 点击按钮以后，将所有选中的多选框的value属性值弹出
		 */
		//4.#sendBtn
		//为sendBtn绑定单击响应函数
		var sendBtn = document.getElementById("sendBtn");
		sendBtn.onclick = function(){
			//遍历items
			for(var i=0 ; i<items.length ; i++){
				//判断多选框是否选中
				if(items[i].checked){
					alert(items[i].value);
				}
			}
		};
		
		
		//5.#checkedAllBox
		/*
		 * 全选/全不选 多选框
		 * 	- 当它选中时，其余的也选中，当它取消时其余的也取消
		 * 
		 * 在事件的响应函数中，响应函数是给谁绑定的this就是谁
		 */
		//为checkedAllBox绑定单击响应函数
		checkedAllBox.onclick = function(){
			
			//alert(this === checkedAllBox);
			
			//设置多选框的选中状态
			for(var i=0; i <items.length ; i++){
				items[i].checked = this.checked;
			}
			
		};
		
		//6.items
		/*
		 * 如果四个多选框全都选中，则checkedAllBox也应该选中
		 * 如果四个多选框没都选中，则checkedAllBox也不应该选中
		 */
		
		//为四个多选框分别绑定点击响应函数
		for(var i=0 ; i<items.length ; i++){
			items[i].onclick = function(){
				
				//将checkedAllBox设置为选中状态
				checkedAllBox.checked = true;
				
				for(var j=0 ; j<items.length ; j++){
					//判断四个多选框是否全选
					//只要有一个没选中则就不是全选
					if(!items[j].checked){
						//一旦进入判断，则证明不是全选状态
						//将checkedAllBox设置为没选中状态
						checkedAllBox.checked = false;
						//一旦进入判断，则已经得出结果，不用再继续执行循环
						break;
					}
					
				}
				
				
				
			};
		}
		
		
	};
	
</script>
</head>
<body>

	<form method="post" action="">
		你爱好的运动是？<input type="checkbox" id="checkedAllBox" />全选/全不选 
		
		<br />
		<input type="checkbox" name="items" value="足球" />足球
		<input type="checkbox" name="items" value="篮球" />篮球
		<input type="checkbox" name="items" value="羽毛球" />羽毛球
		<input type="checkbox" name="items" value="乒乓球" />乒乓球
		<br />
		<input type="button" id="checkedAllBtn" value="全　选" />
		<input type="button" id="checkedNoBtn" value="全不选" />
		<input type="button" id="checkedRevBtn" value="反　选" />
		<input type="button" id="sendBtn" value="提　交" />
	</form>
</body>
</html>
```



# 七、Dom操作-元素节点的属性

```javascript
获取，元素对象.属性名
例：element.value
element.id
element.className
• 设置，元素对象.属性名=新的值
例：element.value = “hello”
element.id = “id01”
element.className = “newClass”
```



# 八、Dom操作-其他属性

```javascript
 nodeValue
– 文本节点可以通过nodeValue属性获取和设置
文本节点的内容
• innerHTML
– 元素节点通过该属性获取和设置标签内部的
html代码
```

代码

```javascript
//返回#bj的文本值
				myClick("btn11",function(){
					
					//获取id为bj的元素
					var bj = document.getElementById("bj");
					
					//alert(bj.innerHTML);
					//alert(bj.innerText);
					
					//获取bj中的文本节点
					/*var fc = bj.firstChild;
					alert(fc.nodeValue);*/
					
					alert(bj.firstChild.nodeValue);
```



# 九、Dom操作-使用CSS选择器进行查询

```javascript
使用CSS选择器进行查询
querySelector()
• querySelectorAll()
• 这两个方法都是用document对象来调用，两个方法使用相同，
都是传递一个选择器字符串作为参数，方法会自动根据选择器
字符串去网页中查找元素。
• 不同的地方是querySelector()只会返回找到的第一个元素，而
querySelectorAll()会返回所有符合条件的元素。
```

案例：

```javascript
//获取class为box1中的所有的div
				//.box1 div
				/*
				 * document.querySelector()
				 * 	- 需要一个选择器的字符串作为参数，可以根据一个CSS选择器来查询一个元素节点对象
				 * 	- 虽然IE8中没有getElementsByClassName()但是可以使用querySelector()代替
				 * 	- 使用该方法总会返回唯一的一个元素，如果满足条件的元素有多个，那么它只会返回第一个
				 */
				var div = document.querySelector(".box1 div");
				
				var box1 = document.querySelector(".box1")
				
				//console.log(div.innerHTML);
				//console.log(box1.innerHTML);
/*
				 * document.querySelectorAll()
				 * 	- 该方法和querySelector()用法类似，不同的是它会将符合条件的元素封装到一个数组中返回
				 * 	- 即使符合条件的元素只有一个，它也会返回数组
				 */
				box1 = document.querySelectorAll(".box1");
				box1 = document.querySelectorAll("#box2");
				console.log(box1);
```



# 十、Dom操作-节点的修改

```javascript
节点的修改
创建节点
– document.createElement(标签名)
• 删除节点
– 父节点.removeChild(子节点)
• 替换节点
– 父节点.replaceChild(新节点 , 旧节点)
• 插入节点
– 父节点.appendChild(子节点)
– 父节点.insertBefore(新节点 , 旧节点)
```

案例代码

```javascript
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<html>
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
		<title>Untitled Document</title>
		<link rel="stylesheet" type="text/css" href="style/css.css" />
		<script type="text/javascript">
		
			window.onload = function() {
				
				//创建一个"广州"节点,添加到#city下
				myClick("btn01",function(){
					//创建广州节点 <li>广州</li>
					//创建li元素节点
					/*
					 * document.createElement()
					 * 	可以用于创建一个元素节点对象，
					 * 	它需要一个标签名作为参数，将会根据该标签名创建元素节点对象，
					 * 	并将创建好的对象作为返回值返回
					 */
					var li = document.createElement("li");
					
					//创建广州文本节点
					/*
					 * document.createTextNode()
					 * 	可以用来创建一个文本节点对象
					 *  需要一个文本内容作为参数，将会根据该内容创建文本节点，并将新的节点返回
					 */
					var gzText = document.createTextNode("广州");
					
					//将gzText设置li的子节点
					/*
					 * appendChild()
					 * 	 - 向一个父节点中添加一个新的子节点
					 * 	 - 用法：父节点.appendChild(子节点);
					 */
					li.appendChild(gzText);
					
					//获取id为city的节点
					var city = document.getElementById("city");
					
					//将广州添加到city下
					city.appendChild(li);
					
					
				});
				
				//将"广州"节点插入到#bj前面
				myClick("btn02",function(){
					//创建一个广州
					var li = document.createElement("li");
					var gzText = document.createTextNode("广州");
					li.appendChild(gzText);
					
					//获取id为bj的节点
					var bj = document.getElementById("bj");
					
					//获取city
					var city = document.getElementById("city");
					
					/*
					 * insertBefore()
					 * 	- 可以在指定的子节点前插入新的子节点
					 *  - 语法：
					 * 		父节点.insertBefore(新节点,旧节点);
					 */
					city.insertBefore(li , bj);
					
					
				});
				
				
				//使用"广州"节点替换#bj节点
				myClick("btn03",function(){
					//创建一个广州
					var li = document.createElement("li");
					var gzText = document.createTextNode("广州");
					li.appendChild(gzText);
					
					//获取id为bj的节点
					var bj = document.getElementById("bj");
					
					//获取city
					var city = document.getElementById("city");
					
					/*
					 * replaceChild()
					 * 	- 可以使用指定的子节点替换已有的子节点
					 * 	- 语法：父节点.replaceChild(新节点,旧节点);
					 */
					city.replaceChild(li , bj);
					
					
				});
				
				//删除#bj节点
				myClick("btn04",function(){
					//获取id为bj的节点
					var bj = document.getElementById("bj");
					//获取city
					var city = document.getElementById("city");
					
					/*
					 * removeChild()
					 * 	- 可以删除一个子节点
					 * 	- 语法：父节点.removeChild(子节点);
					 * 		
					 * 		子节点.parentNode.removeChild(子节点);
					 */
					//city.removeChild(bj);
					
					bj.parentNode.removeChild(bj);
				});
				
				
				//读取#city内的HTML代码
				myClick("btn05",function(){
					//获取city
					var city = document.getElementById("city");
					
					alert(city.innerHTML);
				});
				
				//设置#bj内的HTML代码
				myClick("btn06" , function(){
					//获取bj
					var bj = document.getElementById("bj");
					bj.innerHTML = "昌平";
				});
				
				myClick("btn07",function(){
					
					//向city中添加广州
					var city = document.getElementById("city");
					
					/*
					 * 使用innerHTML也可以完成DOM的增删改的相关操作
					 * 一般我们会两种方式结合使用
					 */
					//city.innerHTML += "<li>广州</li>";
					
					//创建一个li
					var li = document.createElement("li");
					//向li中设置文本
					li.innerHTML = "广州";
					//将li添加到city中
					city.appendChild(li);
					
				});
				
				
			};
			
			function myClick(idStr, fun) {
				var btn = document.getElementById(idStr);
				btn.onclick = fun;
			}
			
		
		</script>
		
	</head>
	<body>
		<div id="total">
			<div class="inner">
				<p>
					你喜欢哪个城市?
				</p>

				<ul id="city">
					<li id="bj">北京</li>
					<li>上海</li>
					<li>东京</li>
					<li>首尔</li>
				</ul>
				
			</div>
		</div>
		<div id="btnList">
			<div><button id="btn01">创建一个"广州"节点,添加到#city下</button></div>
			<div><button id="btn02">将"广州"节点插入到#bj前面</button></div>
			<div><button id="btn03">使用"广州"节点替换#bj节点</button></div>
			<div><button id="btn04">删除#bj节点</button></div>
			<div><button id="btn05">读取#city内的HTML代码</button></div>
			<div><button id="btn06">设置#bj内的HTML代码</button></div>
			<div><button id="btn07">创建一个"广州"节点,添加到#city下</button></div>
		</div>
	</body>
</html>

```



# 十一、Dom增删改查

```javascript
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
<title>添加删除记录练习</title>
<link rel="stylesheet" type="text/css" href="ex_2_style/css.css" />
<script type="text/javascript">
	
	window.onload = function(){
		
		/*
		 * 点击超链接以后，删除一个员工的信息
		 */
		
		//获取所有额超链接
		var allA = document.getElementsByTagName("a");
		
		//为每个超链接都绑定一个单击响应函数
		for(var i=0 ; i < allA.length ; i++){
			allA[i].onclick = function(){
				
				//点击超链接以后需要删除超链接所在的那行
				//这里我们点击那个超链接this就是谁
				//获取当前tr
				var tr = this.parentNode.parentNode;
				
				//获取要删除的员工的名字
				//var name = tr.getElementsByTagName("td")[0].innerHTML;
				var name = tr.children[0].innerHTML;
				
				//删除之前弹出一个提示框
				/*
				 * confirm()用于弹出一个带有确认和取消按钮的提示框
				 * 	需要一个字符串作为参数，该字符串将会作为提示文字显示出来
				 * 如果用户点击确认则会返回true，如果点击取消则返回false
				 */
				var flag = confirm("确认删除"+name+"吗?");
				
				//如果用户点击确认
				if(flag){
					//删除tr
					tr.parentNode.removeChild(tr);
				}
				
				/*
				 * 点击超链接以后，超链接会跳转页面，这个是超链接的默认行为，
				 * 	但是此时我们不希望出现默认行为，可以通过在响应函数的最后return false来取消默认行为
				 */
				return false;
			};
		}
		
	};

	
</script>
</head>
<body>

	<table id="employeeTable">
		<tr>
			<th>Name</th>
			<th>Email</th>
			<th>Salary</th>
			<th>&nbsp;</th>
		</tr>
		<tr>
			<td>Tom</td>
			<td>tom@tom.com</td>
			<td>5000</td>
			<td><a href="javascript:;">Delete</a></td>
		</tr>
		<tr>
			<td>Jerry</td>
			<td>jerry@sohu.com</td>
			<td>8000</td>
			<td><a href="deleteEmp?id=002">Delete</a></td>
		</tr>
		<tr>
			<td>Bob</td>
			<td>bob@tom.com</td>
			<td>10000</td>
			<td><a href="deleteEmp?id=003">Delete</a></td>
		</tr>
	</table>

	<div id="formDiv">
	
		<h4>添加新员工</h4>

		<table>
			<tr>
				<td class="word">name: </td>
				<td class="inp">
					<input type="text" name="empName" id="empName" />
				</td>
			</tr>
			<tr>
				<td class="word">email: </td>
				<td class="inp">
					<input type="text" name="email" id="email" />
				</td>
			</tr>
			<tr>
				<td class="word">salary: </td>
				<td class="inp">
					<input type="text" name="salary" id="salary" />
				</td>
			</tr>
			<tr>
				<td colspan="2" align="center">
					<button id="addEmpButton" value="abc">
						Submit
					</button>
				</td>
			</tr>
		</table>

	</div>

</body>
</html>

===2
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<html>

	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
		<title>添加删除记录练习</title>
		<link rel="stylesheet" type="text/css" href="ex_2_style/css.css" />
		<script type="text/javascript">
		
			/*
			 * 删除tr的响应函数
			 */
			function delA() {

				//点击超链接以后需要删除超链接所在的那行
				//这里我们点击那个超链接this就是谁
				//获取当前tr
				var tr = this.parentNode.parentNode;

				//获取要删除的员工的名字
				//var name = tr.getElementsByTagName("td")[0].innerHTML;
				var name = tr.children[0].innerHTML;

				//删除之前弹出一个提示框
				/*
				 * confirm()用于弹出一个带有确认和取消按钮的提示框
				 * 	需要一个字符串作为参数，该字符串将会作为提示文字显示出来
				 * 如果用户点击确认则会返回true，如果点击取消则返回false
				 */
				var flag = confirm("确认删除" + name + "吗?");

				//如果用户点击确认
				if(flag) {
					//删除tr
					tr.parentNode.removeChild(tr);
				}

				/*
				 * 点击超链接以后，超链接会跳转页面，这个是超链接的默认行为，
				 * 	但是此时我们不希望出现默认行为，可以通过在响应函数的最后return false来取消默认行为
				 */
				return false;
			};

			window.onload = function() {

				/*
				 * 点击超链接以后，删除一个员工的信息
				 */

				//获取所有额超链接
				var allA = document.getElementsByTagName("a");

				//为每个超链接都绑定一个单击响应函数
				for(var i = 0; i < allA.length; i++) {
					allA[i].onclick = delA;
				}

				/*
				 * 添加员工的功能
				 * 	- 点击按钮以后，将员工的信息添加到表格中
				 */

				//为提交按钮绑定一个单击响应函数
				var addEmpButton = document.getElementById("addEmpButton");
				addEmpButton.onclick = function() {

					//获取用户添加的员工信息
					//获取员工的名字
					var name = document.getElementById("empName").value;
					//获取员工的email和salary
					var email = document.getElementById("email").value;
					var salary = document.getElementById("salary").value;

					//alert(name+","+email+","+salary);
					/*
					 *  <tr>
							<td>Tom</td>
							<td>tom@tom.com</td>
							<td>5000</td>
							<td><a href="javascript:;">Delete</a></td>
						</tr>
						需要将获取到的信息保存到tr中
					 */

					//创建一个tr
					var tr = document.createElement("tr");

					//创建四个td
					var nameTd = document.createElement("td");
					var emailTd = document.createElement("td");
					var salaryTd = document.createElement("td");
					var aTd = document.createElement("td");

					//创建一个a元素
					var a = document.createElement("a");

					//创建文本节点
					var nameText = document.createTextNode(name);
					var emailText = document.createTextNode(email);
					var salaryText = document.createTextNode(salary);
					var delText = document.createTextNode("Delete");

					//将文本条件到td中
					nameTd.appendChild(nameText);
					emailTd.appendChild(emailText);
					salaryTd.appendChild(salaryText);

					//向a中添加文本
					a.appendChild(delText);
					//将a添加到td中
					aTd.appendChild(a);

					//将td添加到tr中
					tr.appendChild(nameTd);
					tr.appendChild(emailTd);
					tr.appendChild(salaryTd);
					tr.appendChild(aTd);

					//向a中添加href属性
					a.href = "javascript:;";

					//为新添加的a再绑定一次单击响应函数
					a.onclick = delA;

					//获取table
					var employeeTable = document.getElementById("employeeTable");
					//获取employeeTable中的tbody
					var tbody = employeeTable.getElementsByTagName("tbody")[0];
					//将tr添加到tbodye中
					tbody.appendChild(tr);

				};

			};
		</script>
	</head>

	<body>

		<table id="employeeTable">
			<tr>
				<th>Name</th>
				<th>Email</th>
				<th>Salary</th>
				<th>&nbsp;</th>
			</tr>
			<tr>
				<td>Tom</td>
				<td>tom@tom.com</td>
				<td>5000</td>
				<td>
					<a href="javascript:;">Delete</a>
				</td>
			</tr>
			<tr>
				<td>Jerry</td>
				<td>jerry@sohu.com</td>
				<td>8000</td>
				<td>
					<a href="deleteEmp?id=002">Delete</a>
				</td>
			</tr>
			<tr>
				<td>Bob</td>
				<td>bob@tom.com</td>
				<td>10000</td>
				<td>
					<a href="deleteEmp?id=003">Delete</a>
				</td>
			</tr>
		</table>

		<div id="formDiv">

			<h4>添加新员工</h4>

			<table>
				<tr>
					<td class="word">name: </td>
					<td class="inp">
						<input type="text" name="empName" id="empName" />
					</td>
				</tr>
				<tr>
					<td class="word">email: </td>
					<td class="inp">
						<input type="text" name="email" id="email" />
					</td>
				</tr>
				<tr>
					<td class="word">salary: </td>
					<td class="inp">
						<input type="text" name="salary" id="salary" />
					</td>
				</tr>
				<tr>
					<td colspan="2" align="center">
						<button id="addEmpButton">
						Submit
					</button>
					</td>
				</tr>
			</table>

		</div>

	</body>

</html>

===3
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<html>

	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
		<title>添加删除记录练习</title>
		<link rel="stylesheet" type="text/css" href="ex_2_style/css.css" />
		<script type="text/javascript">
		
			/*
			 * 删除tr的响应函数
			 */
			function delA() {

				//点击超链接以后需要删除超链接所在的那行
				//这里我们点击那个超链接this就是谁
				//获取当前tr
				var tr = this.parentNode.parentNode;

				//获取要删除的员工的名字
				//var name = tr.getElementsByTagName("td")[0].innerHTML;
				var name = tr.children[0].innerHTML;

				//删除之前弹出一个提示框
				/*
				 * confirm()用于弹出一个带有确认和取消按钮的提示框
				 * 	需要一个字符串作为参数，该字符串将会作为提示文字显示出来
				 * 如果用户点击确认则会返回true，如果点击取消则返回false
				 */
				var flag = confirm("确认删除" + name + "吗?");

				//如果用户点击确认
				if(flag) {
					//删除tr
					tr.parentNode.removeChild(tr);
				}

				/*
				 * 点击超链接以后，超链接会跳转页面，这个是超链接的默认行为，
				 * 	但是此时我们不希望出现默认行为，可以通过在响应函数的最后return false来取消默认行为
				 */
				return false;
			};

			window.onload = function() {

				/*
				 * 点击超链接以后，删除一个员工的信息
				 */

				//获取所有额超链接
				var allA = document.getElementsByTagName("a");

				//为每个超链接都绑定一个单击响应函数
				for(var i = 0; i < allA.length; i++) {
					allA[i].onclick = delA;
				}

				/*
				 * 添加员工的功能
				 * 	- 点击按钮以后，将员工的信息添加到表格中
				 */

				//为提交按钮绑定一个单击响应函数
				var addEmpButton = document.getElementById("addEmpButton");
				addEmpButton.onclick = function() {

					//获取用户添加的员工信息
					//获取员工的名字
					var name = document.getElementById("empName").value;
					//获取员工的email和salary
					var email = document.getElementById("email").value;
					var salary = document.getElementById("salary").value;

					//alert(name+","+email+","+salary);
					/*
					 *  <tr>
							<td>Tom</td>
							<td>tom@tom.com</td>
							<td>5000</td>
							<td><a href="javascript:;">Delete</a></td>
						</tr>
						需要将获取到的信息保存到tr中
					 */

					//创建一个tr
					var tr = document.createElement("tr");

					//设置tr中的内容
					tr.innerHTML = "<td>"+name+"</td>"+
									"<td>"+email+"</td>"+
									"<td>"+salary+"</td>"+
									"<td><a href='javascript:;'>Delete</a></td>";
									
					//获取刚刚添加的a元素，并为其绑定单击响应函数				
					var a = tr.getElementsByTagName("a")[0];
					a.onclick = delA;
					
					//获取table
					var employeeTable = document.getElementById("employeeTable");
					//获取employeeTable中的tbody
					var tbody = employeeTable.getElementsByTagName("tbody")[0];
					//将tr添加到tbodye中
					tbody.appendChild(tr);
					/*tbody.innerHTML += "<tr>"+
					
					"<td>"+name+"</td>"+
									"<td>"+email+"</td>"+
									"<td>"+salary+"</td>"+
									"<td><a href='javascript:;'>Delete</a></td>"
					
					+"</tr>";*/

				};

			};
		</script>
	</head>

	<body>

		<table id="employeeTable">
			<tr>
				<th>Name</th>
				<th>Email</th>
				<th>Salary</th>
				<th>&nbsp;</th>
			</tr>
			<tr>
				<td>Tom</td>
				<td>tom@tom.com</td>
				<td>5000</td>
				<td>
					<a href="javascript:;">Delete</a>
				</td>
			</tr>
			<tr>
				<td>Jerry</td>
				<td>jerry@sohu.com</td>
				<td>8000</td>
				<td>
					<a href="deleteEmp?id=002">Delete</a>
				</td>
			</tr>
			<tr>
				<td>Bob</td>
				<td>bob@tom.com</td>
				<td>10000</td>
				<td>
					<a href="deleteEmp?id=003">Delete</a>
				</td>
			</tr>
		</table>

		<div id="formDiv">

			<h4>添加新员工</h4>

			<table>
				<tr>
					<td class="word">name: </td>
					<td class="inp">
						<input type="text" name="empName" id="empName" />
					</td>
				</tr>
				<tr>
					<td class="word">email: </td>
					<td class="inp">
						<input type="text" name="email" id="email" />
					</td>
				</tr>
				<tr>
					<td class="word">salary: </td>
					<td class="inp">
						<input type="text" name="salary" id="salary" />
					</td>
				</tr>
				<tr>
					<td colspan="2" align="center">
						<button id="addEmpButton">
						Submit
					</button>
					</td>
				</tr>
			</table>

		</div>

	</body>

</html>


===4
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
<title>添加删除记录练习</title>
<link rel="stylesheet" type="text/css" href="ex_2_style/css.css" />
<script type="text/javascript">
	
	window.onload = function(){
		
		/*
		 * 点击超链接以后，删除一个员工的信息
		 */
		
		//获取所有额超链接
		var allA = document.getElementsByTagName("a");
		
		//为每个超链接都绑定一个单击响应函数
		for(var i=0 ; i < allA.length ; i++){
			/*
			 * for循环会在页面加载完成之后立即执行，
			 * 	而响应函数会在超链接被点击时才执行
			 * 当响应函数执行时，for循环早已执行完毕
			 */
			
			alert("for循环正在执行"+i);
			
			allA[i].onclick = function(){
				
				alert("响应函数正在执行"+i);
				
				//alert(allA[i]);
				
				return false;
			};
			
		}
		
	};

	
</script>
</head>
<body>

	<table id="employeeTable">
		<tr>
			<th>Name</th>
			<th>Email</th>
			<th>Salary</th>
			<th>&nbsp;</th>
		</tr>
		<tr>
			<td>Tom</td>
			<td>tom@tom.com</td>
			<td>5000</td>
			<td><a href="javascript:;">Delete</a></td>
		</tr>
		<tr>
			<td>Jerry</td>
			<td>jerry@sohu.com</td>
			<td>8000</td>
			<td><a href="deleteEmp?id=002">Delete</a></td>
		</tr>
		<tr>
			<td>Bob</td>
			<td>bob@tom.com</td>
			<td>10000</td>
			<td><a href="deleteEmp?id=003">Delete</a></td>
		</tr>
	</table>

	<div id="formDiv">
	
		<h4>添加新员工</h4>

		<table>
			<tr>
				<td class="word">name: </td>
				<td class="inp">
					<input type="text" name="empName" id="empName" />
				</td>
			</tr>
			<tr>
				<td class="word">email: </td>
				<td class="inp">
					<input type="text" name="email" id="email" />
				</td>
			</tr>
			<tr>
				<td class="word">salary: </td>
				<td class="inp">
					<input type="text" name="salary" id="salary" />
				</td>
			</tr>
			<tr>
				<td colspan="2" align="center">
					<button id="addEmpButton" value="abc">
						Submit
					</button>
				</td>
			</tr>
		</table>

	</div>

</body>
</html>



```



dom增删改极度简洁版本

dom操作js 系列已经完结

# 十二、Dom操作css系列

