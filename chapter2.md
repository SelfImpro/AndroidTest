# 创建本地单元测试
[原文请点击这里](http://developer.android.com/intl/zh-cn/training/testing/unit-testing/local-unit-tests.html)

If your unit test has no dependencies or only has simple dependencies on Android, you should run your test on a local development machine. This testing approach is efficient because it helps you avoid the overhead of loading the target app and unit test code onto a physical device or emulator every time your test is run. Consequently, the execution time for running your unit test is greatly reduced. With this approach, you normally use a mocking framework, like Mockito, to fulfill any dependency relationships.

如果你的单元测试没有任何相关性或者只是Android上的简单依赖，你应该在本地开发机器上面运行你的测试。这种测试方式是高效的，因为他帮助你避免了从头开始加载庞大的应用，以及单元测试代码在

##安装测试环境