# 敏捷开发-编程实践之测试驱动开发
## 背景概述 
软件开发按步骤分为：需求分析、概要设计、详细设计、编码、测试、软件交付、验收、软件维护。需求是千变万化的，人们总结出了各种不同的软件开发过程；不同的开发过程有与其相适应软件开发模型，比如教科书上了瀑布开发模型、螺旋开发模型等等（[参考](http://baike.baidu.com/view/8300.htm)）。

软件开发过程是在某种需求背景下的价值观和方法论，像IBM总结并实践的统一开发过程（[RUP](http://zh.wikipedia.org/wiki/IBM-Rational%E7%BB%9F%E4%B8%80%E8%BF%87%E7%A8%8B)）是一种重量级的大型商业软件开发过程。对于小型的软件开发团队，现在流行一种被称之为敏捷开发的软件开发过程，下面要说的就是此过程中对软件开发的编码和测试步骤的一种实践方法——TDD。

## 名词解释
* TDD(Test Driven Development): 测试驱动开发

## 什么是测试驱动开发
一般来说，程序开发都是先编码完成功能开发，然后再写测试代码。这样可能存在这样的问题：

* 先开发功能，开发者很可能对功能进行过度设计，把时间浪费在可能不需要的功能上
* 设计出的接口可能不完善，可能出现功能都实现，但使用起来比较别扭，使的软件质量降低
* 很可能完成功能后，因为种种理由放弃编写测试代码，导致功能实现中留下太他的隐患
* 功能完成一段时间以后，发现功能上有不足，想动手重构时发现有太多的代码依赖此模块，怕重构导致太多的问题而放弃重构

测试驱动开发是从另外一个角度进行程序开发：

* 简单来说，它要求在编写某个功能的代码之前先编写测试代码，然后只编写使测试通过的功能代码，通过测试来推动整个开发的进行
* 从原理上来说，在开发功能代码之前，先编写测试代码，开发人员站在使用者的角度对功能模块的接口进行思考，在写测试例的同时明确功能需求并完善接口设计；之后开发功能代码的时候可以做到要做的事情心中有数
* 从效率上来说，在写测试的时候同时明确功能需求，可以省去详细设计的文档要求；另外，因为一开始就对功能需求比较明确，有效的减少了开发时反复的次数
* 从维护上来说，因为有测试例存在，对功能模块的各种修改都不会存在隐患，在需要的时候可以对整个功能模块进行大胆的重构来进行优化和改进

### 参考资料
* [浅谈测试驱动开发（TDD）](http://www.ibm.com/developerworks/cn/linux/l-tdd/)
* [测试驱动开发](http://baike.baidu.com/view/184088.htm)
* [测试驱动开发TDD简介入门](http://www.360doc.com/content/07/0516/17/15822_503491.shtml)

### 适用场景
人员有变动的小型团队开发中小型项目，需要持续开发并维护来响应需求变更。

* [拒绝测试驱动开发（TDD）的10个理由](http://www.csdn.net/article/2011-12-27/309713)

### 优缺点
* [敏捷开发-测试驱动开发优缺点](http://liweibird.blog.51cto.com/631764/568391)

### 实践要点
* 项目适合吗
* 改变开发者的思维
* 理论只是理论，要和具体项目相结合
* 只是说说是改变不了任何东西，要具体去做

## C++项目开发TDD实践的助推器——C++单元测试框架

### 单元测试框架
是用来辅助开发者快速编写测试例并进行测试的功能库，每种不同的语言都有适合自己开发语言的测试框架，对于C++来说也不例外，且有很多测试框架可选，比如：CppUnit，UnitCpp, CxxTest，Boost.Test等等（[已知列表](http://en.wikipedia.org/wiki/List_of_unit_testing_frameworks#C.2B.2B)）,下面要说的是GoogleTest，简称gtest.

### 概念介绍
* Test Case: 测试例，测试员具体编写的东西，包含对被测试对象的一个或一组相关的功能接口的测试代码段
* Test Suite: 测试包/组， 是test Case的一种组织结构，一个Test Suite包含一组相关的测试例，可能是一个被测试对象所有功能接口的测试
* Test Framework: 对编写好的测试例根据某种策略挨个执行测试例并输出测试结果的功能框架

### 参考资料
* [googletest](https://code.google.com/p/googletest/)
* [玩转Google开源C++单元测试框架Google Test系列(gtest)之一 - 初识gtest](http://www.cnblogs.com/coderzh/archive/2009/03/31/1426758.html)
* [玩转Google开源C++单元测试框架Google Test系列(gtest)之二 - 断言](http://www.cnblogs.com/coderzh/archive/2009/04/06/1430364.html)
* [玩转Google开源C++单元测试框架Google Test系列(gtest)之三 - 事件机制](http://www.cnblogs.com/coderzh/archive/2009/04/06/1430396.html)
* [玩转Google开源C++单元测试框架Google Test系列(gtest)之四 - 参数化](http://www.cnblogs.com/coderzh/archive/2009/04/08/1431297.html)
* [玩转Google开源C++单元测试框架Google Test系列(gtest)之五 - 死亡测试](http://www.cnblogs.com/coderzh/archive/2009/04/08/1432043.html)
* [玩转Google开源C++单元测试框架Google Test系列(gtest)之六 - 运行参数](http://www.cnblogs.com/coderzh/archive/2009/04/10/1432789.html)
* [玩转Google开源C++单元测试框架Google Test系列(gtest)之七 - 深入解析gtest](http://www.cnblogs.com/coderzh/archive/2009/04/11/1433744.html)
* [玩转Google开源C++单元测试框架Google Test系列(gtest)之八 - 打造自己的单元测试框架](http://www.cnblogs.com/coderzh/archive/2009/04/12/1434155.html)
* [gtest中如何跳出当前测试案例](http://www.cnblogs.com/coderzh/archive/2009/08/02/1536901.html)
* [编写优美的GTest测试案例](http://www.cnblogs.com/coderzh/archive/2010/01/09/beautiful-testcase.html)
