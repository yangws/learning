Cocosbuilder3.0使用分享
=======================

在CPP工程中如何使用Cocosbuilder
-------------------------------
* 创建一个Cocobuilder工程
	* resources-auto为publish时能够自动缩放的资源目录，所以资源只需要最大的那一套，
    比如iOS上使用ipad-hd(4x)，android上使用xlarge(4x),
    需要注意的是，在publish setting里面需要选择`Automatic scaling from: 4x`
    * 在Appdelegate.cpp中添加searchPaths和resourceOrders
    * 创建出来的layer默认是js controlled，需要取消js controlled，即转换为cpp controlled, 方法如下
    	* 选中对应的ccb
        * 点击Document，去掉js controlled前的勾
    * 填写对应的Custom class名称，用于自定义layer的加载，具体见registerCCNodeLoader
    * 如何添加Menu，CCControlButton事件响应
* 编写对应的Loader和Layer文件
* 修改编辑ccb的分辨率，默认为iphone，演示如何改为ipad: Document -> Resolution

多分辨率适配
------------
* 选择资源，以大套资源为准
* 五种相对坐标布局(_topleft_, _rightleft_, _bottomleft_, _bottomright_, _percent_)
* 如何使用设置Design Resolution使游戏全屏
* 如何导出不同分辨率的资源

如何编辑动画Timeline
------------------------


在动画中添加回调和音效支持
--------------------------



在JSB工程中如何使用Cocosbuilder
-------------------------------

如何为CocosBuilder添加plugin
----------------------------
