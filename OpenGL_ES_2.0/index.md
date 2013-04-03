# Learning OpenGL ES 2.0 Overview
## 相关资源

1. 示例代码使用Eclipse环境为Android平台编写，其中使用了PVRTools的源码，需要Android4.1以上版本的SDK来编译。
	* 示例代码仓库：__https://github.com/IdVincentYang/OpenGL_ES2_Samples.git__
    	* 使用__File->Import...->Android->Import Android Project From existing Source...__
        * 设置__SampleFundation__为库工程，每个示例工程需要依赖SampleFundation
        * 工程C++代码默认指定__x86__ABI，如要在ARM架构上运行，请在__每个工程的jni/Applicaion.mk__中指定ABI为__armeabi__
2. 参考的文档资料[点此下载](http://www.kuaipan.cn/file/id_120512221070491937.htm)
    * [点此进入官方网站](http://www.khronos.org/registry/gles/)
    * [点此打开官方OpenGL ES 2.0在线API文档](http://www.khronos.org/opengles/sdk/docs/man/)

## 目录
0. [初识OpenGL ES 2.0](00_OpenGLES2.pdf)
1. [HelloOpenGLES2](01_HelloOpenGLES2.pdf)
2. [Primitive Assembly(图元组装)](02_PrimitiveAssembly.pdf)
3. [Texturing(纹理贴图)](03_Texturing.pdf)

## 附录
1. [用Eclipse为Android开发C++程序](http://yangws.github.com/yong-eclipsewei-androidkai-fa-ccheng-xu.html)
