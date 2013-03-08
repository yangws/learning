# 用Eclipse为Android开发C++程序

* [搭建开发环境](#environment)
* [编写一个HelloCpp程序](#hellocpp)
* [小技巧](#tips)

<h2 id="environment"/>
## __搭建开发环境__
1. 从[Andrdoid官方网站下载最新的SDK](http://developer.android.com/sdk/index.html)，解压到指定的目录，注意__目录路径中不要有中文字符和空格，建议不要解压到系统盘__。
2. 从[Android官方网站下载最新的NDK](http://developer.android.com/tools/sdk/ndk/index.html)，解压到指定目录，建议解压到SDK的adt-bundle目录下。
3. 打开Eclipse，在菜单Windows->Preferences界面的Android->NDK设置项中设置正确的NDK路径。![][img_13.1]

<h2 id="hellocpp"/>
## __编写一个HelloCpp程序__
1. 点击_File->New->Android Application Project_新建一个Android工程HelloCpp,只输入application Name为"HelloCpp"一路Next就可以。
![][img_21.1]
2. 在工程右键菜单中选择_Debug As...->Android Application_，在模拟器运行，显示一个"Hello world!"。
![][img_22.1]
3. 接下来用C++代码实现一个函数，返回一个字符串为"Hello cpp!"，并用这个字符串替换"Hello world!"。首先_给工程添加C++代码支持_，在工程右键菜单中选择_Android Tools->Add Native Support..._
![][img_23.1]
![][img_23.2]
![][img_23.3]
4. 在Java代码中添加载入C++代码动态库的代码，并添加一个需要C++实现的naticve函数。
![][img_24.1]
5. 调用JDK的javah工具生成需要C++实现的native函数的头文件，刷新一下工程。
```
    javah -verbose -jni -classpath "${project_loc}/bin/classes;" -d "${project_loc}/jni" "com.example.hellocpp.MainActivity.java"
```
![][img_25.1]
6. 在C++源码文件中实现native函数。
![][img_26.1]
7. 在Java代码中调用Native函数获取字符串并设置到界面上,编译并运行程序。
![][img_27.1]
![][img_27.2]

<h2 id="tips"/>
## __小技巧__
1. 如果在NDK编译时遇到错误： __Android NDK: WARNING: APP_PLATFORM android-14 is larger than android:minSdkVersion 8 in ./AndroidManifest.xml	HelloCpp__，可以在jni目录下新建Application.mk文件，然后添加如下一行代码解决。
```
APP_PLATFORM := android-8
```
2. 在Intel CPU的机器上使用__硬件加速__提高模拟器运行速度。
![用Android SDK Manager安装最新的SDK版本的x86 system Image 和 Intel的硬件加速支持软件][img_a21]
![用AVD建立模拟器时选择x86的ABI][img_a22]

[img_13.1]: images/eclipse_set_ndk_path.jpg             "Eclipse中设置NDK路径"

[img_21.1]: images/eclipse_new_project.jpg              "Eclipse中新建立的Android Application Project"
[img_22.1]: images/eclipse_new_project_run.jpg          "Eclipse新建工程运行结果"
[img_23.1]: images/eclipse_select_add_ndk_support.jpg   "Eclipse工程右键菜单选择add NDK Support..."
[img_23.2]: images/eclipse_name_native_library.jpg      "Eclipse工程添加NDK支持时给将要添加的包含C++代码的动态库命名"
[img_23.3]: images/eclipse_new_project_with_ndk_support.jpg "Eclipse工程添加NDK支持后的空白C++源码文件"
[img_24.1]: images/eclipse_java_add_native_method.jpg   "Eclipsejava代码调用C++动态库，并添加需要C++实现的函数"
[img_25.1]: images/eclipse_javah_gen_header.jpg         "使用Javah工具生成native函数的C++头文件"
[img_26.1]: images/eclipse_impl_native_method.jpg       "用C++代码实现native函数"
[img_27.1]: images/eclipse_java_call_native.jpg         "Java代码调用C++代码获取字符串并设置到界面上"
[img_27.2]: images/eclipse_show_hello_cpp.jpg           "C++函数返回的字符串显示在界面上"

[img_a21]: images/asm_install_x86_emu.jpg
[img_a22]: images/avd_emu_enable_hard_acc.jpg
