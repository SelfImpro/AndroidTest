# 构建本地单元测试

如何你的单元测试没有依赖或者非常少的依赖Android，你可以在本地开发设备上面运行测试代码。这种测试时有效的，因为它可以帮助你避免每一次你的测试运行加载目标APP和单元测试代码到物理设备或者模拟器的开销。所以，运行单元测试的执行时间会大大缩减。使用这种方法，你会用到mocking框架，如[Mockito](https://github.com/mockito/mockito)，来满足任何依赖关系。

##搭建你的测试环境
在你的AS项目中，你应该保存你的测试代码在module-name/src/test/java/目录下。这个目录当你创建项目时就已经存在。

当然你需要为你的项目配置测试依赖以便使用JUnit4框架提供的标准API。如果你的测试需要与Android依赖交互，导入Mockito库来简化你的单元测试。学习更多关于在本地单元测试中使用mock对象，请移步[Mocking Android dependencies](https://developer.android.com/training/testing/unit-testing/local-unit-tests.html#mocking-dependencies)。

在你的应用顶级目录的`build.gradle`文件中，你需要指定这些测试依赖库：
```
dependencies {
    // Required -- JUnit 4 framework
    testCompile 'junit:junit:4.12'
    // Optional -- Mockito framework
    testCompile 'org.mockito:mockito-core:1.10.19'
}
```

##创建本地单元测试类
你的本地单元测试类要像JUnit4测试类一样写。[Junit](http://junit.org/)是一个非常有名的并且广泛被使用的一个java单元测试框架。最新的版本库，JUnit4，允许你编写比以前任何版本更加纯净以及更加灵活的测试类。不同于之前基于JUnit3实现android测试的方法，JUnit4，你不需要继承`junit.framework.TestCase`类。你也不需要在你的测试方法前加上一个关键字`test`的前缀，以及使用一些位于`junit.framework`和`junit.extensions`包下的类。

创建一个简单JUnit4的测试类，创建一个包含了一个或者多个测试方法的java类。测试方法始于`@Test`注解和包含执行代码并验证要测试组件的单一功能。

这些例子都展示了如何实现一个本地单元测试类。测试方法`eamilValidator_CorrectEamilSimple_ReturnsTrue`验证应用中`isValidEmail()`方法在测试中返回正确的结果。

```
import org.junit.Test;
import java.util.regex.Pattern;
import static org.junit.Assert.assertFalse;
import static org.junit.Assert.assertTrue;

public class EmailValidatorTest {

    @Test
    public void emailValidator_CorrectEmailSimple_ReturnsTrue() {
        assertThat(EmailValidator.isValidEmail("name@email.com"), is(true));
    }
    ...
}

```
要测试你的应用中的组件返回预期的结果，争对一些预期值使用`junit.Assert`方法进行验证检查（或断言）与测试下的组件状态进行对比。为了使测试可读性更高，你可以使用[Hamcrest matchers](https://github.com/hamcrest)（例如`is()`和`equalTo()`方法）来匹配返回的结果对比预期的结果。

##模拟Android依赖
默认情况下，[Android Plug-in for Gradle](https://developer.android.com/tools/building/plugin-for-gradle.html)执行本地单元测试针对的是`android.jar`库修改版本，里面不包含任何实际代码。相反，通过单元测试调用的Android类方法抛出异常。

  你可以使用`mocking framework`在代码存根出外部依赖(to stub out external dependencies)，轻松的按照预期测试你的组件与依赖的交互。通过mock对象替换android依赖，你可以从Android系统的其余部分，同时验证这些依赖关系的正确方法被称为隔离单元测试。java的`Mockito`模拟框架（1.9.5版本或更高）提供了兼容的Android单元测试。通过`Mockito`，你配置mock对象调用时返回指定的值























