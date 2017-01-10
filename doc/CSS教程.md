#CSS w3school教程

>**CSS的基本功：布局、盒子模型、选择器优先级及使用、CSS hack技巧、CSS浏览器兼容性问题、position相关问题、containing block、BFC等**

##CSS基础教程
###css基础语法
####语法构成
css规则由两个主要部分构成：选择器和一条以上的样式声明组成。
`selector {declaration1; declaration2; ... declarationN }`
==每条声明==是一个键值对，一个属性名和一个属性值组成，他们用冒号分割。属性名为需要设置的样式属性`selector {property: value}`
>**提示：**如果要定义不止一个声明，则需要用分号将每个声明分开

假如将 h1 元素内的文字颜色定义为红色，同时将字体大小设置为 14 像素。`h1 {color:red; font-size:14px;}`
因为一个样式表可能不止一条CSS规则，每个CSS规则有多行声明，那么最好将每条声明放在一行，键值对之间的空格的使用使得样式表更容易被编辑，提高可读性：
```
p {
  text-align: center;
  color: black;
  font-family: arial;
}
```
####CSS高级语法
**选择器分组**的目的是让多个选择器共享同一个样式声明，逗号分割选择器。
```
h1,h2,h3,h4,h5,h6 {
  color: green;
  }
```
**继承**语法，比如设定了body元素使用的字体，那么body元素下面的所有子元素都是使用body中设定的字体，但是我p元素不想使用从body中继承来的字体样式声明设置。那么只要从新对p元素设定一个css规则即可
```
body  {
     font-family: Verdana, sans-serif;
     }
td, ul, ol, ul, li, dl, dt, dd  {
     font-family: Verdana, sans-serif;
     }
p  {
     font-family: Times, "Times New Roman", serif;
     }
```
**派生选择器**，举个例子比如我想对strong元素加一个斜体样式，但是我只想对li元素下的strong元素使用这个样式。这种实现就是派生选择器
示例：
```
//只对li元素中子元素strong元素有效
li strong {
    font-style: italic;
    font-weight: normal;
  }
```

**id选择器**
id 选择器可以为标有特定 id 的 HTML 元素指定特定的样式。id选择器以"#"字符开始定义
下面的两个 id 选择器，第一个可以定义元素的颜色为红色，第二个定义元素的颜色为绿色：
```
#red {color:red;}
#green {color:green;}
```
选择器单独使用
id 选择器即使不被用来创建派生选择器，它也可以独立发挥作用：
```
#sidebar {
	border: 1px dotted #000;
	padding: 10px;
	}
```
这条规则，id 为 sidebar 的元素将拥有一个像素宽的黑色点状边框，同时其周围会有 10 个像素宽的内边距（padding，内部空白）

**id 选择器和派生选择器**
在现代布局中，id 选择器常常用于建立派生选择器。
```
#sidebar p {
	font-style: italic;
	text-align: right;
	margin-top: 0.5em;
	}
```
这个样式只会用于id是sidebar的元素里面的段落元素样式。这个元素很可能是 div 或者是表格单元，尽管它也可能是一个表格或者其他块级元素

**一个id选择器，多种用法**
id属性标注为 sidebar 的元素只能在文档中定义一次，这个 id 选择器作为派生选择器在CSS中可以使用很多次：
```
#sidebar p {
	font-style: italic;
	text-align: right;
	margin-top: 0.5em;
	}

#sidebar h2 {
	font-size: 1em;
	font-weight: normal;
	font-style: italic;
	margin: 0;
	line-height: 1.5;
	text-align: right;
	}
```
在这里，与页面中的其他 p 元素明显不同的是，sidebar 内的 p 元素得到了特殊的处理，同时，与页面中其他所有 h2 元素明显不同，sidebar 中的 h2 元素也得到了特殊样式处理。

####CSS类选择器
**类选择器**以一个点号显示`.selector{ ....}`，可以对多个html元素class属性设置值达到公用同一个样式规则。

`.center {text-align: center}` 对所有html元素class属性值为center的html元素文字居中。
 HTML 代码中，h1 和 p 元素都有 center 类。这意味着两者都将遵守 ".center" 选择器中的规则
```
<h1 class="center">
This heading will be center-aligned
</h1>

<p class="center">
This paragraph will also be center-aligned.
</p>
```
>**注意**：类名的第一个字符不能使用数字！它无法在 Mozilla 或 Firefox 中起作用。
和 id选择器 一样，**class 类选择器也可被用作派生选择器**：
```
.fancy td {
	color: #f60;
	background: #666;
	}
```
类属性值为fancy块级元素里面的表格数据元素都是灰色背景显示橙色文字，（名为 fancy 的更大的元素可能是一个表格或者一个 div）

html元素也可以对指定class的html元素设置样式规则
对td表格数据元素，class 为fancy的表格元素设置样式
```
td.fancy {
	color: #f60;
	background: #666;
	}
```
类名为 fancy 的表格单元将是带有灰色背景文字橙色。`<td class="fancy">`

你可以将类 fancy 分配给任何一个**表格元素任意多的次数**。那些以 fancy 标注的单元格都会是带有灰色背景的橙色。那些没有被分配名为 fancy 的类的单元格不会受这条规则的影响。还有一点值得注意，class 为 fancy 的段落也不会是带有灰色背景的橙色，当然，任何其他被标注为 fancy 的元素也不会受这条规则的影响。这都是由于我们书写这条规则的方式，这个效果被限制于被标注为 fancy 的表格单元（即使用 td 元素来选择 fancy 类）。



####CSS属性选择器
可以为拥有指定属性的 HTML 元素设置样式，而不仅限于 class 和 id 属性。
**属性选择器**
`[title] { color:red; }` 为html元素有title属性的添加样式
```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html>
<head>
<style type="text/css">
[title]
{
color:red;
}
</style>
</head>

<body>
<h1>可以应用样式：</h1>
<h2 title="Hello world">Hello world</h2>
<a title="W3School" href="http://w3school.com.cn">W3School</a>

<hr />

<h1>无法应用样式：</h1>
<h2>Hello world</h2>
<a href="http://w3school.com.cn">W3School</a>
</body>
</html>

```

**属性和值选择器**
例子为 title="W3School" 的所有元素设置样式
```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html>
<head>
<style type="text/css">
[title=W3School]
{
border:5px solid blue;
}
</style>
</head>

<body>
<h1>可以应用样式：</h1>
<img title="W3School" src="/i/w3school_logo_white.gif" />
<br />
<a title="W3School" href="http://w3school.com.cn">W3School</a>
<hr />

<h1>无法应用样式：</h1>
<p title="greeting">Hi!</p>
<a class="W3School" href="http://w3school.com.cn">W3School</a>
</body>
</html>


```
**属性和值选择器 - 匹配多个属性值**
为title 属性包含指定值的所有元素设置样式。适用于由空格分隔的属性值：
```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html>
<head>
<style type="text/css">
[title~=hello]
{
color:red;
} 
</style>
</head>

<body>
<h1>可以应用样式：</h1>
<h2 title="hello world">Hello world</h2>
<p title="student hello">Hello W3School students!</h1>
<p title="x hello">Hello W3School students!</h1>
<hr />

<h1>无法应用样式：</h1>
<h2 title="world">Hello world</h2>
<p title="student">Hello W3School students!</p>
</body>
</html>

```

**设计表单样式**
属性选择器在为不带有 class 或 id 的表单设置样式时特别有用
```

<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html>
<head>
<style>
input[type="text"]
{
  width:150px;
  display:block;
  margin-bottom:10px;
  background-color:yellow;
  font-family: Verdana, Arial;
}

input[type="button"]
{
color:red;
  width:120px;
  margin-left:35px;
  display:block;
  font-family: Verdana, Arial;
}
</style>
</head>
<body>

<form name="input" action="" method="get">
<input type="text" name="Name" value="Bill" size="20">
<input type="text" name="Name" value="Gates" size="20">
<input type="button" value="Example Button">

</form>
</body>
</html>

```

####插入样式表

三种形式创建样式规则：

+ 外部样式表
+ 内部样式表
+ 内联样式表

**外部样式表**

当样式需要应用于很多页面时，外部样式表将是理想的选择。可以通过改变一个文件来改变整个站点的外观。每个页面使用 link 标签链接到样式表。link标签位于head标签里面：
` <link href="ResponsivePages.css" rel="stylesheet" type="text/css"/>` 插入跟当前html文档处于同一目录下的css样式表文件

**内部样式表**
当前html文档需要该文档下特定的样式资源可以在head元素下面使用style元素定义当前文档中使用的样式规则。

**内联样式表**
对特定html元素需要指定样式资源，就通过html元素的style属性指定改元素的样式规则

**多重设置样式**
如果某些元素属性在不同的样式表中被同样的选择器定义，那么最终的属性值有些继承有些被覆盖。

```
//外部样式表
h3 {
  color: red;
  text-align: left;
  font-size: 8pt;
  }
```

```
//内部样式表
h3 {
  text-align: right; 
  font-size: 20pt;
  }
```

h3元素拥有内部样式表，外部样式表双重设置，那么 h3最终 得到的样式是：

```
color: red; 
text-align: right; 
font-size: 20pt;
```
颜色属性将被继承于外部样式表，而文字排列（text-alignment）和字体尺寸（font-size）会被内部样式表中的规则覆盖











