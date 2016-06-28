# 构建本地单元测试

如何你的单元测试没有依赖或者非常少的依赖Android，你可以在本地开发设备上面运行测试代码。这种测试时有效的，因为它可以帮助你避免每一次你的测试运行加载目标APP和单元测试代码到物理设备或者模拟器的开销。所以，运行单元测试的执行时间会大大缩减。使用这种方法，你会用到mocking框架，如[Mockito](https://github.com/mockito/mockito)，来满足任何依赖关系。

##搭建你的测试环境
在你的AS项目中，你应该保存你的测试代码在module-name/src/test/java/目录下。这个目录当你创建项目时就已经存在。

当然你需要为你的项目配置测试依赖以便使用JUnit4框架提供的标准API。如果你的测试需要与Android依赖交互，导入Mockito库来简化你的单元测试。学习更多关于在本地单元测试中使用mock对象，请移步[Mocking Android dependencies](https://developer.android.com/training/testing/unit-testing/local-unit-tests.html#mocking-dependencies)。