## Chapter 1 <a id="chapter-1"></a>
#第一个标题
你好**Markdown**
***
#开始示例
##图片
插入图片内联形式，格式`![任何文本或者空](图片链接 title)`
![pic](/home/vincent/图片/123.png  "插入本地绝对路径图片")
![pic](beauty.png "插入跟当前md文档同一目录下的图片")
![pic](../img/dev.jpg "插入跟当前md文档不同一目录下本地图片相对路径")
![sdf](/home/vincent/PythonDataCourse/prblog.github.com/img/addstage.JPG  "绝对路径下的图片")
插入图片引用形式，在remarkable上不行
引用形式图片：![pictures][1]
[1]:  /home/vincent/图片/123.png  "插入跟当前md文档不同一目录下的图片"

![after](/home/vincent/PythonDataCourse/prblog.github.com/img/afteradd.JPG  "after")


***

##链接

插入链接内联方式
[百度一下](http://www.baidu.com "") 
[css](CSS教程.md  "CSS")
插入链接引用方式，类似于论文的参考文献，只要提供一个id然后后面在写具体的引用资源
这是一个引用的链接[淘宝][1] 到达 [天猫][2]
[1]: http://www.taobao.com "淘宝"
[2]: http://www.tmall.com "tmall"
链接锚，链接到本文档的其他标题

* [Chapter 1](#chapter-1)
* [Chapter 2](#chapter-2)
* [Chapter 3](#chapter-3)



类似于html中hr元素，横线

***

---

___

##标题
###第一种形式

#一级标题，带下横线
##二级标题，带下横线
###三级标题
####四级标题
####实力的
#####五级标题
######六级标题

###标题第二种形式
第一级标题
=======================
第二级标题
-------------------------------

###引用中加标题
>##引用标题

***

## Chapter 2 <a id="chapter-2"></a>

##短语增强

**加粗**
__加粗的另一种形式__
*斜体*
_斜体_

***加粗并斜体***
___加粗并斜体另一种形式___
~~删除线~~

加入反斜杠用于输入一些转义后的字符
下面这个使得*号不是作为斜体的标记而是作为文本的一部分
\*literal asterisks\*

Markdown 支持以下这些符号前面加上反斜杠来帮助插入普通的符号：

\   反斜线
`   反引号
*   星号
_   底线
{}  花括号
[]  方括号
()  括弧
\#   井字号
+   加号
-   减号
.   英文句点
!   惊叹号

***
##List
这是无序列表，文字开头添加(*, +,-)但是要注意在(*, +, and -)和文字之间需要添加空格

+ 中国
+ 美国
+ 日本

+ 我是广东工业大学学生计算机学院计算机学院计算机学院计算机学院计算机学院计算机学院计算机学院计算机学院计算机学院计算机学院计算机学院计算机学院计算机学院计算机学院计算机学院计算机学院计算机学院计算机学院
计算机学院计算机学院计算机学院计算机学院计算机学院计算机学院计算机学院计算机学院计算机学院
计算机学院计算机学院计算机学院
+ 中国中国
中国中国中国中国中国中国中国中国中国中国中国中国中国中国中国中国中国中国中国中国中国中国中国中国中国中国中国中国
中国中国中国中国
中国中国中国
+ 广州市



这是有序列表,使用数字后面跟上句号。（数字点号和正文之间有空格）


1. XXX
2. YYY
3. ZZZ
4. 666


==高亮==
==JAVA  C==
~下标字~
~~上标字~~
>块级引用，的实力开发空间里都是靠家里都是空房间数量多客服即可实力的开发经理速度快解放了山东会计法律考试的解放了空间看收到了快放假了山东快放假了圣诞节饭老师的咖啡机拉斯卡登记法拉克的解放了开机费啦；时间；大奖哦诶接哦我看实力的飞机来说都放假了圣诞节福利刷卡的缴费。
收到了疯狂送到家里疯狂的世界里看见对方。
卢萨卡多俊福绿索多阔府君率扩多菌率扩缩君奥率扩军多副卡所虑多扩军法率索多扩军法率索多阔佬而吴我肉肉IE具法律都是
来说都几点上课积分
实力的开发交流大神发空间

> 这是一个块级引用,xiam
上的浪费空间的

简单数学表达式：$x^2+y^2=z^2$
复杂数学表达式：$$\sum_{i=0}^n i^2 = \frac{(n^2+n)(2n+1)}{6}$$

***

## Chapter 3 <a id="chapter-3"></a>

##代码
代码，通过一个tab或者四个space键

	public class Demo{
		public static void main(String[] args){
			System.out.println("Hello World");
		}
	}
	//java代码



 单行代码通过符号`
 
 `单行的代码示例: int a=89;`

多行代码(块代码)通过符号```

```
多行代码
public class Demo{
		public static void main(String[] args){
			System.out.println("Hello World");
		}
	}
	//java代码
```

多行代码同时语法高亮,语法形式```js

```java

public  class Demo{

	public static void main(String[] args){
		System.out.println("sdfsdf");
	}
}
```

python代码
```python

def fun():
	i=5
	j=7
	z=i+j
	return z
fun() 
```

使用tab键输入code

	#include<stdio.h>
	int main(char* argv, int argc){
		println("Hello World");
	}

代码示例：
>代码示例
	
	int main(char * argv, int argc){
		println("sdflsdkjflsdjk");
	}


---
##脚注

脚注
hello[^hello]

[^hello]:hl


***
##表格
###表格左对齐
|手机厂商| 市场排名|
|----|---|
|huawei| 35%|
|xiaomi | 25%|
|vivo| 15%|
|Apple| 2%|

###表格右对齐
|手机厂商| 市场排名|
|------- :|--- :|
|huawei| 35%|
|xiaomi | 25%|
|vivo| 15%|
|Apple| 2%|


***

##引用标签blockquote

 <blockquote>
        <p>For example.</p>
    </blockquote>
 
 <table>
    <tr>
        <td>Foo</td>
        <td> 表格元素</td>
    </tr>
</table>


***
##直接使用html标签

使用html的a标签，实验是直接使用a标签不行的

<a href="http://www.baidu.com">baidu
</a>

<div id="090">
</div>


***

参考文献：
[Markdown syntax][1]
[知乎][2]
[Markdown 语法说明][3]
[Markdown office website][4]

[1]: https://learn.getgrav.org/content/markdown "Markdown syntax"
[2]: https://www.zhihu.com/question/21065229 "zhihu"
[3]: http://wowubuntu.com/markdown/#overview "Markdown 语法简体说明"
[4]: http://daringfireball.net/projects/markdown/syntax "Markdown 官方文档"
星期一, 09. 一月 2017 09:46下午 