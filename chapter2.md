# 创建本地单元测试
[原文请点击这里](http://developer.android.com/intl/zh-cn/training/testing/unit-testing/local-unit-tests.html)

如果你的单元测试没有任何相关性或者只是Android上的简单依赖，你应该在本地开发机器上面运行你的测试。这种测试方式是有效的，因为它可以帮助你避免目标应用程序和单元测试代码加载到物理设备或者模拟器时，每一次运行测试的开销。因此，运行单元测试的执行时间大大减少。通过这种方式，你常用的mocking framework，如Mockito，以满足任何依赖关系。

##安装测试环境



##