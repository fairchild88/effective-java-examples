## 使用静态工厂方法代替构造器

### 有名称

对比如下的两种写法：

``` java 
BigInteger(int, int, Random) //constructor
BigInteger.probablePrime() //static method
``` 

相比第一种写法，第二种写法对返回值做出了更清晰的描述。

对于具有相同签名的构造函数，静态方法避免了签名限制，且通过不同名称表达更明确，对使用者也更友好。示例如下：

``` java
Circle(float radius, float centerx, float centery) //circle define in cartesian coordinates(笛卡尔坐标系)
Circle(float a, float centerx, float centery) //circle defined in polar coordinates(极坐标)

//use static method 
Circle.generateCircleInCartesian(float radius, float centerx, float centery)
Circle.generateCircleInPolar(float a, float centerx, float centery)
```

### 不必每次调用的时候都创建新对象

如果经常请求创建相同的对象，并且创建的成本有点高，使用这项技术可以极大的提高性能。

``` java
Boolean.valueOf()
```
 
### 可以返回原返回类型的任何子类型的对象

这项技术适合基于接口的框架，接口为静态工厂方法提供了自然返回类型。接口不能有静态方法，所以把静态方法放在一个不可实例化的类里面。如：Java Collection Framework 。另外一个示例为java.util.EnumSet
### 在创建参数化类型时，代码更加简洁

``` java
Map<String, List<String>> instance = new HashMap<String, List<String>>();
public static <K, V> HashMap<K, V> newInstance() {
  return new HashMap(K, V)
}
```

### 缺点

#### 不包含公有或受保护的构造器，不能被子类化

但关于这一点，也正符合了鼓励程序使用复合，而不是继承的特点

#### 和其他静态方法没有任何区别
