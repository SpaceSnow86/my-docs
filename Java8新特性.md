# 接口的默认方法

在jdk8后，接口中可以写**多个**default方法。此方法在接口被实现后无需重写即可使用。

```java
package priv.ihch17.LambdaDemo;

public interface TestInterface {

    //默认方法
    default void defaultMethod1(){
        System.out.println("defaultMethod1");
    }

    default void defaultMethod2(String str){
        System.out.println("defaultMethod2");
    }

    default String defaultMethod3(){
        return "defaultMethod1";
    }

    String method1();  
    String method2();
}
```



# Lambda表达式

## 函数式接口

仅仅只含有1个抽象方法，默认方法可以为多个的方法，使用`@FunctrionalInterface`注解检查是否符合函数式接口规范。

```java
@FunctionalInterface
public interface TestInterface {

    //默认方法
    default void defaultMethod1(){
        System.out.println("defaultMethod1");
    }

    default void defaultMethod2(String str){
        System.out.println("defaultMethod2");
    }

    default String defaultMethod3(){
        return "defaultMethod1";
    }

    //函数式接口：接口中的有且只有1个抽象方法
    String method();
}
```

## Lambda

**Lanbda表达式需要函数式接口的支持**

### Demo

```Java
TestInterface test = str -> {};
//（）内为参数列表
//{}内为Lambda体
```

> 个人理解：
>
> Lambda表达式其实就是一种父类引用指向子类对象，例如List list = new ArrayList();
>
> 只是子类对接口的实现过程由Lambda表达式直接完成，无需再显式的进行接口实现。
>
> 由于函数式接口中已经定义了唯一抽象方法的参数列表和返回值类型，所以在Lambda中，无需再对变量名称进行类型声明！

其中：

1. Interface为函数式接口

2. ()内写参数

   - 如果()内就一个参数，()可以不写

     ```
     TestInterface test = str -> {};
     ```

     

3. {}内写方法体

   - 若{}内就一句代码，{}可以不写

     ```java
     TestInterface test = ()-> System.out.println("无返回值，方法体就一句代码");
     ```

     

   - 若()内就一句代码，而且为return，return可以不写

     ```java
     TestInterface test = ()->"test";
     ```

# 四大内置函数式接口

`因为再使用Lambda表达式过程中需要大量使用函数式接口，每次使用就创建一个函数式来说太过于麻烦。Java8便内置了4大常用函数式接口方便使用。`