# 入门测试

[原文请点击这里](http://developer.android.com/intl/zh-cn/training/testing/start/index.html)

编写和运行测试在开Android发周期中是一个重要组成部分。精心编写的测试能够帮助你在开发的早期抓住Bug以及让你对自己的代码充满信息。使用AS(Android Studio)，你能够在各种物理或者虚拟Android设备上面运行本地的单元测试或者[仪器测试][1]。然后可以分析测试结果，在开发环境中修改你的代码。

本地单元测试是运行在本地机器上的测试，不需要访问Android framework或者Android设备。学习开发本地单元测试，可以查阅[创建本地单元测试](http://developer.android.com/intl/zh-cn/training/testing/unit-testing/local-unit-tests.html)

Instrumented tests are tests that run on an Android device or emulator. These tests have access to Instrumentation information, such as the Context for the app under test. Instrumented tests can be used for unit, user interface (UI), or app component integration testing. To learn how to develop instrumented tests for your specific needs, see these additional topics:

仪器测试运行在Android设备或者模拟器上面运行测试。这些测试能够获得仪器信息，像应用的Context。







[1]:instrumented tests, 对于仪器测试暂时还不是很懂