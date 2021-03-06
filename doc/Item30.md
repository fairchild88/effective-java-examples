## 用Enum代替int常量
int 枚举模式 ( int enum pattern ) 在类型安全性和使用方便性方面没有任何帮助. 没有便利的方法将 int 枚举常量翻译为可打印的字符串.

String 枚举模式 依赖于字符串比较, 导致性能问题.

Java 的枚举类型功能十分齐全, 比其他语言中的对等物都要强大的多. Java 的枚举本质上是int 值. 枚举类型还允许添加任意的方法和域, 并实现任意的接口. 枚举类型可以先作为枚举常量的一个简单集合, 随着时间的推移再演变为全功能的抽象.

### 枚举使用方法
1. 在枚举中增加成员变量和方法
1. 使用特定于常量的方法实线
    * 枚举类型自动产生 valueOf( String ), 将常量的名字转变成常量本身.
    * 如果枚举中覆盖了 toString(), 要考虑实现 fromString 方法, 将特定的字符串表示法变回枚举. 
1. 策略枚举
    * 策略常量类型
    * 策略抽象方法
    * 策略常量实线
    * 接口方法

### 枚举使用场景
需要一组固定常量的时候 
