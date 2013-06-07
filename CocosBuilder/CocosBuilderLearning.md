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
    * 初始化成员变量和自定义属性，CCBMemberVariableAssigner
    * 如何添加Menu，CCControlButton事件响应, 实现CCBSelectorResolver
* 编写对应的Loader和Layer文件
	* Loader的作用:
    <pre>
        CCNodeLoader *ccNodeLoader = this->mCCNodeLoaderLibrary->getCCNodeLoader(className.c_str());
        CCNode *node = ccNodeLoader->loadCCNode(pParent, this);
    </pre>
* 修改编辑ccb的分辨率，默认为iphone，演示如何改为ipad: Document -> Resolution

多分辨率适配
------------
* 选择资源，以大套资源为准
* 五种相对坐标布局(_topleft_, _rightleft_, _bottomleft_, _bottomright_, _percent_)
* 如何使用设置Design Resolution使游戏全屏
* 如何导出不同分辨率的资源

如何编辑动画Timeline
------------------------
* Animation -> Insert Keyframe
* EditTimeline -> 选择是否autoplay

在动画中添加回调和音效支持
--------------------------
* Alt键按住才能编辑Sound Effects和Callbacks
* Cocosbuilder会把音频格式自动转换为平台最合适的格式
	* iOS wav -> caf,
	* Android wav -> ogg,
    * fileUtils->loadFilenameLookupDictionaryFromFile("fileLookup.plist");



在JSB工程中如何使用Cocosbuilder
-------------------------------
* 添加文件名称转换查找表

	cc.FileUtils.getInstance().loadFilenameLookup("fileLookup.plist");

* 在JS中加载一个ccbi

	var myScene = cc.BuilderReader.loadAsScene("MainScene.ccbi");


如何为CocosBuilder添加plugin
----------------------------
* 编译Cocosbuilder工程，确认在build目录下有CocosBuilder.app文件
* 复制CocosBuilder/PlugIn Nodes/CCRotatingSprite Demo工程并重命名为新plugin的名称
* 运行工程即可以将plugin拷贝到build/CocosBuilder.app中
* 参考https://github.com/wolfand11/CocosBuilder-CustomWidget/blob/master/Document/2-1-%E5%AE%9E%E7%8E%B0CocosBuilder%E6%8E%A7%E4%BB%B6%E6%8F%92%E4%BB%B6.org
