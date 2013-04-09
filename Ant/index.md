# Learning Apache Ant
## 目录

* [Ant 简介](#ach1)
* [Ant 构建文件](#ach2)
* [Ant 命令参数](#ach3)
* [Ant 开发](#ach4)
	* [project](#ach4_1)
	* [target](#ach4_2)
	* [tasks](#ach4_3)

## <a id="ach1"></a>Ant 简介
* [Apache Ant 官方网站](http://ant.apache.org/)
* Apache Ant,是一个将软件编译、测试、部署等步骤联系在一起加以自动化的一个工具，大多用于Java环境中的软件开发。
* 参考文档：[ant 中文手册](ant.pdf)

## <a id="ach2"></a>Ant 构建文件
构建文件，即开发者需要编写的 xml 配置文件，Ant 工具对构建文件进行解析完成开发者定义的自动化步骤。默认的构建文件为 build.xml。

## <a id="ach3"></a>Ant 命令参数
* ant 命令格式：ant [script options] [options] [target [target2 [target3] ..]]  
* 可以使用 ant -help 查看具体的参数说明。常用 options 参数：
	* _**-q**_ 简略输出的 log。
	* _**-d**_ 输出 debug 信息。
	* _**-buildfile**_ _**-file**_ _**-f**_ 指定构建文件。

## <a id="ach4"></a>Ant 开发
主要工作就是构建文件的编写，主要的组成部分以及说明：

### <a id="ach4_1"></a>project  
每个构建文件对应一个项目。各个属性的含义分别如下：

* _**default**_ 表示默认的运行目标，即指定默认的target（即任务）。这个属性是必须的。  
* _**basedir**_ 表示项目的基准目录。  
* _**name**_ 表示项目名。  

### <a id="ach4_2"></a>target  
一个项目下可以有一个或多个target。一个target标签可以依赖其他的target标签。Target的主要属性如下：  

* _**name**_ 表示target的名称，这个属性是必须的。
* _**depends**_ 表示依赖的target。
* _**if**_ 表示仅当属性设置时才执行。
* _**unless**_ 表示当属性没有设置时才执行。
* _**description**_ 表示target的描述。

**Ant会依照depends属性中target出现顺序依次执行每个target。在执行之前，首先需要执行它所依赖的target。一个target只能被执行一次，即使有多个target依赖于它。**  

### <a id="ach4_3"></a>tasks  
1. property  
	可以理解为常量，值不可变。定义 properties 的方式有两种：  
	* `<property name="sampleName" value="sampleValue" />`  
	* 使用 Property 文件定义 properties，然后在构建文件中加载 Property 文件。  
	`<property file="ant.properties" />` 或者 `<loadproperties srcFile="project.properties" />`  

	通过 ${property name} 使用 property。
2. import  
	引入其他的 xml 构建文件。主要属性：  
	* _**file**_ 需要引入的 xml 文件。**必要属性**
	* _**optional**_ 是否可选的 import，默认值为 false。
	
3. exec  
	调用系统命令。主要属性：
	* _**command**_ 执行的命令行以及参数。
	* _**executable**_ 执行的命令，不包含参数。参数使用 \<arg> 子标签指定。
	* _**failonerror**_ 命令执行报错时是否认为 ant 执行失败，默认为 false。
4. [更多的 tasks](http://ant.apache.org/manual/tasklist.html)  
5. 可以自定义 task。[点击查看](http://ant.apache.org/manual/develop.html#writingowntask)