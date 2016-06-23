# 入门测试

[原文请点击这里](http://developer.android.com/intl/zh-cn/training/testing/start/index.html)

编写和运行测试在开Android发周期中是一个重要组成部分。精心编写的测试能够帮助你在开发的早期抓住Bug以及让你对自己的代码充满信息。使用AS(Android Studio)，你能够在各种物理或者虚拟Android设备上面运行本地的单元测试或者[仪器测试][1]。然后可以分析测试结果，在开发环境中修改你的代码。

本地单元测试是运行在本地机器上的测试，不需要访问Android framework或者Android设备。学习开发本地单元测试，可以查阅[创建本地单元测试](http://developer.android.com/intl/zh-cn/training/testing/unit-testing/local-unit-tests.html)

仪器测试运行在Android设备或者模拟器上面运行测试。这些测试能够获得仪器信息，像在测试应用中的Context。仪器测试可以被用于单元，用户界面，或者应用组件集成测试。要了解如何开发特定需求的仪器化测试，请看如下附加的建议：

* 创建仪器化单元测试 - 建立有Android依赖但不能简单的通过使用模拟对象轻易地填充更复杂的单元测试
* 用户界面自动化测试 - 创建测试去验证用户界面行为正确响应单个应用程序或者跨多个应用的程序交互
* 应用组件集成测试 - 验证用户不直接交互组件的行为，例如Service或者Content Provider

这一课教我们使用AS如何创建和运行你的测试。如果你没有用AS，你可以学习[如何通过命令行运行你的测试](http://developer.android.com/tools/testing/testing_otheride.html)。

Configure Your Project for Local Unit Tests

##配置本地单元测试
在你的AS项目中，你必须将用来本地测试的测试代码存放在指定的资源路径下(src/test/java)。这样通过整合所有的单元测试到一个单一的资源集合中来提高整体的组织结构。

结合项目代码，你可以创建一个特定的[flavor和build type](https://developer.android.com/studio/build/build-variants.html#workBuildVariants)的本地测试。保证你的单元测试代码树位置对应你的生产源代码树
如下:



[1]:instrumented tests, 对于仪器测试暂时还不是很懂