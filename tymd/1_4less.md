[toc]



# less教程

## 1.less 简介

简介

```javascript
	less是一种动态样式语言，
    #属于css预处理器（预编译）的范畴，
    它扩展了 CSS 语言，
	增加了变量、Mixin、函数等特性，使 CSS 更易维护和扩展
	LESS 既可以在 客户端 上运行 ，也可以借助Node.js在服务端运行。
```

例子：

```less
@base: #f938ab;

.box-shadow(@style, @c) when (iscolor(@c)) {
  -webkit-box-shadow: @style @c;
  box-shadow:         @style @c;
}
.box-shadow(@style, @alpha: 50%) when (isnumber(@alpha)) {
  .box-shadow(@style, rgba(0, 0, 0, @alpha));
}
.box {
  color: saturate(@base, 5%);
  border-color: lighten(@base, 30%);
  div { .box-shadow(0 0 5px, 30%) }
}
```

输出：

```css
.box {
  color: #fe33ac;
  border-color: #fdcdea;
}
.box div {
  -webkit-box-shadow: 0 0 5px rgba(0, 0, 0, 0.3);
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.3);
}
```

## 2.安装

### 方式1	下载less 编译js 文件

创建styles.less 代码 文件

```
<style type="text/less">
		*{
			margin: 0;
			padding: 0;
		}
		#wrap{
			position: relative;
			width: 300px;
			height: 400px;
			border: 1px solid;
			margin: 0 auto;
			.inner{
				position: absolute;
				left: 0;
				right: 0;
				top: 0;
				bottom: 0;
				margin: auto;
				background: pink;
				height: 100px;
				width: 100px;
			}
		}
	</style>
```

2.引入所需文件

```
 <link rel="stylesheet/less" type="text/css" href="styles.less" />
<script src="//cdnjs.cloudflare.com/ajax/libs/less.js/2.5.3/less.min.js"></script>

```

完整代码 



```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<style type="text/less">
			*{
				margin: 0;
				padding: 0;
			}
			#wrap{
				position: relative;
				width: 300px;
				height: 400px;
				border: 1px solid;
				margin: 0 auto;
				.inner{
					position: absolute;
					left: 0;
					right: 0;
					top: 0;
					bottom: 0;
					margin: auto;
					background: pink;
					height: 100px;
					width: 100px;
				}
			}
		</style>
	</head>
	<body>
		<div id="wrap">
			<div class="inner">
				
			</div>
		</div>
	</body>
	<script src="less/less.min.js"></script>
</html>


```



### 方式2 	在nodejs 上安装less

#### 1.安装命令

全局安装

```
npm install  less -g
```

#### 2.结果提示 

```
G:\GG_Save\GG_web\demo\4less\less>npm install  less -g
C:\Users\Show\AppData\Roaming\npm\lessc -> C:\Users\Show\AppData\Roaming\npm\node_modules\less\bin\lessc
+ less@4.1.1
added 20 packages from 54 contributors in 91.409s

G:\GG_Save\GG_web\demo\4less\less>

```

#### 3.然后打开需要编译的less 文件的文件夹位置通过cmd 命令进入



```
G:\GG_Save\GG_web\demo\4less\less
```



#### 4.输入编译命令



```
编译语法  ： lessc 源文件地址.less 编译后的文件地址.css
```



```javascript
G:\GG_Save\GG_web\demo\4less\less>lessc G:\GG_Save\GG_web\demo\4less\less\02.less G:\GG_Save\GG_web\demo\4less\less\02.css
# 上面命令在一行执行
G:\GG_Save\GG_web\demo\4less\less>
```

#### 5.在指定的文件位置就会出现编译后的css 文件

#### 6.这样编译工作就完成了





### 简单使用 

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<link rel="stylesheet" type="text/css" href="css/02.css"/>
	</head>
	<body>
		<div id="wrap">
			<div class="inner">
				
			</div>
		</div>
	</body>
	<script src="less/less.min.js"></script>
</html>


```

## 3.网址教程编译工具



```javascript
 less的中文官网：http://lesscss.cn/
```



```javascript
 bootstrap中less教程：http://www.bootcss.com/p/lesscss/
```



```javascript
koala 官网:www.koala-app.com 
```





	

## 4.注释



```javascript
 以//开头的注释，不会被编译到css文件中
 以/**/包裹的注释会被编译到css文件中  
```



## 5.使用

### 	1.less中的变量

#### 	1.作为普通属性值只来使用：直接使用@pink

```javascript
 以//开头的注释，不会被编译到css文件中
 以/**/包裹的注释会被编译到css文件中  
```



### 	2.less中的变量

```javascript
 以//开头的注释，不会被编译到css文件中
 以/**/包裹的注释会被编译到css文件中  
```

