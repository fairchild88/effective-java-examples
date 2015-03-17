## 用接口模拟可伸缩的枚举

枚举类型无法扩展, 但可以通过编写接口以及实现该接口的枚举类型, 对它进行模拟.

```` java
private static <T Extends Enum <T> & Operation> void test( Class<T> opSet) {

}
````

确保Class对象既表示枚举又表示Operation的子类型.
