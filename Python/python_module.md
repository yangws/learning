# **python常用模块** #


****

**1. setuptools**

- setuptools是Python的distutilsde工具的缯强工具，它可以让程序员更方便的创建、发布、安装Python包，还有管理这些包跟Python的依赖性。
- setuptools的安装非常简单，只需要通过一个8k大小的ez_setup.py（在python的官方网站可以下载到这个脚本），就能自动的为用户安装setuptools（如果是windows的用户，还需要把在python中的Script文件目录，加入到环境变量中）。
- setuptools的查找，安装许多第三方库也很简单，只需要我们通过"easy_install packageName"命令，就可以调用setuptools来自动的查找，并安装我们所需要的包，并且解决他们的依赖关系。
- 更多setuptools的使用方法：[http://www.ibm.com/developerworks/cn/linux/l-cppeak3.html](http://www.ibm.com/developerworks/cn/linux/l-cppeak3.html)



**2. GUI**

**2.1 wxPython**

wxPython是Python语言的一套优秀的GUI图形库，允许Python程序员很方 便的创建完整的、功能键全的GUI用户界面。wxPython是作为优秀的跨平台GUI库wxWidgets的Python封装和Python模块的方式提供给用户的。

**2.1.1 一个简单的wxPython程序：**

    #! /usr/bin/env python
	#coding=utf-8

	import wx
	class App(wx.App):
    
	    def OnInit(self):
	        frame = wx.Frame(parent = None, title = 'helloWx')
			frame.Show()
			return True

	if __name__ == '__main__':
	    app = App()
	    app.MainLoop()

**2.1.2 wxPython相关链接：**

wxPython主页：[http://www.wxpython.org](http://www.wxpython.org)

wxPython相关教程：[http://www.czug.org/python/wxpythoninaction/](http://www.czug.org/python/wxpythoninaction/)

**2.2 PyQt**

pyQt是python语言和Qt库的融合。它是一个多平台的工具包，可以运行在所有主要操作系统上，包括UNIX，Windows和Mac。pyQt是一个模块集合，包含了许多的内容，其中可以分成几个模块集：

- **QtCore:** 模块包含核心的非GUI功能。该模块用于时间、文件和目录、各种数据类型、流、网址、MIME类型、线程或进程。

- **QtGui:** 模块包含图形组件和相关的类，例如按钮、窗体、状态栏、工具栏、滚动条、位图、颜色、字体等。

- **QtNetwork:** 模块包含了网络编程的类，这些类允许编写TCP/IP和UDP的客户端和服务器，他们使网络编程更简单，更轻便。

- **QtXml:** 包含使用XML文件的类，这个模块提供了SAX和DOM API的实现。

- **QtSvg:** 模块提供显示的SVG文件的类。可缩放矢量图形（SVG）是一种用于描述二维图形和图形应用程序的XML语言。

- **QtOpenGL:** 模块使用OpenGL库渲染3D和2D图形，该模块能够无缝集成Qt的GUI库和OpenGL库。
	
- **QtSql:** 模块提供用于数据库的类。

**2.2.1 一个简单的PyQt程序：**

	#!/usr/bin/python
	#filename : helloPyQt.py

	import sys
	from PyQt4 import QtGui

	app = QtGui.QApplication(sys.argv)

	widget = QtGui.QWidget()
	widget.resize(250, 150)
	widget.setWindowTitle('helloPyQt')
	widget.show()

	sys.exit(app.exec_())

**2.2.2 PyQt的相关链接：**

**PyQt4相关教程：**[http://www.czug.org/python/pyqt4/](http://www.czug.org/python/pyqt4/)


**2.3 其它GUI**

- **Tkinter:** python默认的gui库
- **PyGTK:** python对GIMP工具集的封装库
- **PyKDE:** python对KDE桌面环境的绑定
