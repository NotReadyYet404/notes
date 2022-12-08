## 单例设计模式
单例设计模式旨在某个类永远只有一个实例，即一个类永远只能创建一个对象。

也就是说，有两点是要作为基本保证的：
1. 类的构造器是不能被应用程序员使用的，否则程序员可以随意生成对象就违反了唯一实例的原则了；
2. 实例会作为类的静态成员变量，coder不能创建，只能通过类来调用实例，这样就保证了单例的原则；
### 饿汉单例
在用类获取对象的时候，对象已经提前为你创建好了。

设计步骤：
- 定义一个类，把构造器私有。
	私有了构造器，使用者就不能构造实例了。
- 定义一个静态变量存储一个对象。

```java
public class SingleInstance {
    /*
    * 2. 饿汉单例在获取前，对象已经提前准备好了，
    * 这个对象只能是一个所以要定义为static，这点一定要切记。
    * */
    public static SingleInstance instance = new SingleInstance();
    public static int age = 21;

    /*
    * 1. 私有化构造器
    * */
    private SingleInstance() {

    }
}
```
### 懒汉单例
在真正需要该对象的时候，才会去加载一个对象(延迟加载)，其实就是单例模式的懒加载形式。

设计步骤：
- 定义一个类并把构造器私有化。
- 定义一个静态成员变量**但不对其初始化**。
- 定义一个静态成员函数，在这个函数内部对静态成员变量初始化并作为返回结果。

对比饿汉单例，懒汉单例有几点需要注意，具体再下方示例代码中体现：

```java
/*
* 懒汉单例
* */
public class SingleInstance {

    /*
    * 2. 定义一个static成员变量来存储一个成员变量，但不对其初始化
    * ⚠需要注意的是：懒汉单例需要通过静态成员来初始化并获取，所以对外不直接暴露实例对象。
    * 因此，static成员变量定义为private
    * */
    private static SingleInstance singleInstance;

    /*
    * 3. 提供一个方法，对外返回单例对象
    * */
    public static SingleInstance getInstance() {
       /*
       * 判断是否是第一次获取单例对象，如果是就先初始化然后再返回。
       * ⚠若没有这个判断的话，每次调用就会new一个实例，这样违反了单例原则。
       * */ 
        if(singleInstance == null) {
            singleInstance = new SingleInstance();
        }
        return singleInstance;
    }

    /*
    * 1. 私有化构造器
    * */
    private SingleInstance() {

    }

}
```

