**ActionScript**

* [示例代码](Flash/Hello.zip)

ActionScript是 Adobe为其Flash产品开发的 ，最初是一种简单的脚本语言，现在最新版本3.0，是一种完全的面向对象的编程语言，功能强大，类库丰富，语法类似JavaScript，多用于Flash互动性、娱乐性、实用性开发，网页制作和RIA应用程序开发。
ActionScript 是一种基于ECMAScript的脚本语言，可用于编写Adobe Flash动画和应用程序。 由于ActionScript和JavaScript都是基于ECMAScript语法的，理论上它们互相可以很流畅地从一种语言翻译到另一种。不过JavaScript的文档对象模型是以浏览器窗口，文档和表单为主的，ActionScript的文档对象模型则以SWF格式动画为主，可包括动画，音频，文字和事件处理。
ActionScript 在 Flash、Flex 和 AIR 内容和应用程序中实现交互性、数据处理以及其它许多功能。

ActionScript 是由 Flash Player 和 AIR 中的 ActionScript 虚拟机 (AVM) 执行的。ActionScript 代码通常由编译器（如 Adobe® Flash® CS4 Professional 或 Adobe® Flex™ Builder™ 的内置编译器或 Adobe® Flex™ SDK 中提供的编辑器）编译为“字节代码格式”（一种由计算机编写并且计算机能够理解的编程语言）。字节码嵌入在 SWF 文件中，SWF 文件由 Flash Player 和 AIR 执行。

**历史**

ActionScript第一次以它目前的语法出现是Flash 5版本，这也是第一个完全可对Flash编程的版本。这个版本被命名为ActionScript1.0。Flash 6通过增加大量的内置函数和对动画元素更好的编程控制更进一步增强了编程环境的功能。Flash 7(MX 2004)引进了ActionScript2.0，它增加了强类型（strong typing）和面向对象特征，如显式类声明， 继承，接口和严格数据类型。ActionScript1.0和2.0使用相同的编译形式编译成Flash SWF文件（即Shockwave Flash files，或 'Small Web Format'）.

**ActionScript 3.0**

ActionScript 3.0 相对于早期 ActionScript 版本改进的一些重要功能包括：

<pre>
ActionScript 3中的新特性：
1.运行时排错：错误会运行时抛出以帮助你调试你的影片。
2.运行时变量类型检测：在回放时会检测变量的类型是否合法。
3.类封装：静态定义的类以增强性能。
4.方法封装：方法现在与它们相关的类实例绑定因此在方法中的’this’将不会改变。
5.E4X ：一个新的，更易于操作的xml 
6.正则表达式：支持本地化正规表达式。
7.命名空间：不但在xml中支持命名空间而且在类的定义中也同样支持。
8.int和uint数据类型：新的数据变量类型允许ActionScript使用更快的整型数据来进行计算。
9.新的显示列表模式：一个新的，自由度较大的管理屏幕上显示对象的方法。
10.新的事件类型模式：一个新的基于侦听器事件的模式。
</pre>
ActionScript 3.0 的脚本编写功能超越了 ActionScript 的早期版本。它旨在方便创建拥有大型数据集和面向对象的可重用代码库的高度复杂应用程序。虽然 ActionScript 3.0 对于在 Adobe Flash Player 中运行的内容并不是必需的，但它使用新型的虚拟机 AVM2 实现了性能的改善。ActionScript 3.0 代码的执行速度可以比旧式 ActionScript 代码快 10 倍。

**数据类型**

在 ActionScript 3中所有数据都是对象。其中的某些数据类型可以看作是“简单”或“基本”数据类型：
<pre>
Boolean：一个 true 或 false 值，例如开关是否开启或两个值是否相等
int:有符号的32位整数型，数值范围：-231︿+(231-1)
uint:没有符号的32位整数型，数值范围：0︿ 232-1
Number：64位浮点值，数值范围1.79769313486231e+308 ︿4.960656458412467e-324
String：一个文本值，字符串
</pre>
简单数据类型表示单条信息：例如，单个数字或单个文本序列。然而，ActionScript 中定义的大部分数据类型都可以被描述为复杂数据类型，因为它们表示组合在一起的一组值。例如，数据类型为 Date 的变量表示一个值 — 某个时间时刻。然而，该日期值实际上表示为几个值：年、月、日、时、分、秒等等，它们都是单独的数字。所以，虽然我们认为日期是单个值（可以通过创建一个 Date 变量将日期作为单个值来对待），而在计算机内部却认为日期是组合在一起、共同定义单个日期的一组值。

大部分内置数据类型以及程序员定义的数据类型都是复杂数据类型。您可能认识下面的一些复杂数据类型：
<pre>
Array:数组
Date：有关时间中的某个片刻的信息（日期和时间）
MovieClip：影片剪辑元件
TextField：动态文本字段或输入文本字段
SimpleButton：按钮元件
自己定义的类</pre>
经常用作数据类型的同义词的两个词是类和对象。类仅仅是数据类型的定义 — 好比用于该数据类型的所有对象的模板，例如“所有 Example 数据类型的变量都拥有这些特性：A、B 和 C”。相反，对象仅仅是类的一个实际的实例；可将一个数据类型为 MovieClip 的变量描述为一个 MovieClip 对象。下面几条陈述虽然表达的方式不同，但意思是相同的：
<pre>
变量 myVariable 的数据类型是 Number。
变量 myVariable 是一个 Number 实例。
变量 myVariable 是一个 Number 对象。
变量 myVariable 是 Number 类的一个实例。
</pre>
数组
<pre>
定义一个数组
var a:Array=[]
var b:Array=new Array()
var c:Array=[1,2,3,4]
var d:Array=new Array(1,2,3,4)
</pre>
Object
<pre>
1.使用构造函数
var foo:Object=new Object()
2.使用空的大括号作为new Object()
函数的语法快捷方式
var foo:Object={k1:v1,k2:v2,k3:v3}
使用空的大括号构造Object时，还可将属性写进去
</pre>

**运算符**

“运算符”是用于执行计算的特殊符号（有时候是词）。这些运算符主要用于数学运算，有时也用于值的比较。通常，运算符使用一个或多个值并“算出”一个结果。例如：
<pre>
算数运算符：+，-，*，/，%，!
算数赋值运算符：+=，-=，*=，/=，%=
关系运算符（判断相等关系）：==，!=，===，!==
关系运算符（判断大小关系）：>=,<=,>,<
逻辑运算符：&&,||,!
三元if-else运算符：?:
typeof（用字符串形式返回对象的类型）
is（判断一个对象是否属于一种类型，返回布尔值）
as（如果一个对象属于一种类型，则返回这个对象，否则返回null）
优先级顺序：使用括号代替记忆

</pre>

**注释**

单行注释：在一行中的任意位置放置两个斜杠来指定单行注释。计算机将忽略斜杠后直到该行末尾的所有内容：
<pre>// This is a comment; it's ignored by the computer. 
var age:Number = 10; // Set the age to 10 by default.
</pre>
多行注释：多行注释包括一个开始注释标记 (/*)、注释内容和一个结束注释标记 (*/)。无论注释跨多少行，计算机都将忽略开始标记与结束标记之间的所有内容：
<pre>/* 
This might be a really long description, perhaps describing what 
a particular function is used for or explaining a section of code. 
 
In any case, these lines are all ignored by the computer. 
*/
var num:Number = 0.1;	//define
</pre>

