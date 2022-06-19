## Liskov替换原则(LSP)

### 子类型多态：客户端可用统一的方式处理不同类型的对象。

```java
Animal a = new Animal();
Animal c1 = new Cat();
Cat c2 = new Cat();
```

编译器在静态类型检查时强制满足的条件:

1.子类型可以增加方法，但不可删除
2.子类型需要实现抽象类型中的所有未实现方法
3.子类型中重写的方法返回值必须与父类相同或符合co-variance(协变)
4.子类型中重写的方法必须使用同样类型的参数或者符合contra-variance(逆变)的参数
5.子类型中重写的方法不能抛出额外的异常

还应该满足的条件

==更强的不变量 (RI)==
==更弱的前置条件==
==更强的后置条件==

### 逆变

关于参数的类型，应该保持不变或者变得更抽象.

```java
class T {
	void c(String s) { … }
}
class S extends T {
	@Override //java语法并不支持逆变，而是当作overload
	void c(Object s) { … }
}

```

### 协变

关于返回值的类型和throw的异常，应该保持不变或者变得更具体

```java
class T {
	Object a() { … }
    void b() throws Throwable {…}
}
class S extends T {
	@Override String a() { … }//返回值更具体
    @Override void b() throws IOException {…}	//抛出的异常更具体甚至可以没有
}

```

### 四种委派方式

1.==Dependency==：依赖关系，临时性的delegation。把被delegation的对象以参数方式传入。只有在需要的时候才建立与被委派类的联系，而当方法结束的时候这种关系也就随之断开了。

2.==Association==：关联关系，永久性的delegation。被delegation的对象保存在rep中，该对象的类型被永久的与此ADT绑定在一起。

3.==Composition==: 更强的association，但难以变化。

4.==Aggregation==: 更弱的association，可动态变化。