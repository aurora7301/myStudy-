java中的异常分为两大类：==checked异常和unchecked==异常。其中，unchecked又分为error和runtime异常。

==Unchecked异常不需要try-catch块处理==。出现了RuntimeException，就一定是程序员自身的问题。比如说，数组下标越界和访问空指针异常等等，

调用一个checked异常的方法，例如IOException，如果抛出所有的checked异常时无法通过编译。
程序运行过程中发现错误，利用throw语句抛出一个异常。
对于unchecked异常，无非主要是两种情况要么是可以避免的（Runtime Exception），要么是不可控制的。这些也是需要声明异常的。

Error（错误）:是程序无法处理的错误，表示运行应用程序中较严重问题。大多数错误与代码编写者执行的操作无关，而表示代码运行时 JVM（Java 虚拟机）出现的问题。例如，Java虚拟机运行错误（Virtual MachineError），当 JVM 不再有继续执行操作所需的内存资源时，将出现 OutOfMemoryError。这些异常发生时，Java虚拟机（JVM）一般会选择线程终止。这些错误表示故障发生于虚拟机自身、或者发生在虚拟机试图执行应用时，如Java虚拟机运行错误（Virtual MachineError）、类定义错误（NoClassDefFoundError）等。这些错误是不可查的，因为它们在应用程序的控制和处理能力之 外，而且绝大多数是程序运行时不允许出现的状况。对于设计合理的应用程序来说，即使确实发生了错误，本质上也不应该试图去处理它所引起的异常状况。在 Java中，错误通过Error的子类描述

Java常见异常

1. ==RuntimeException==子类:    

序号    异常名称    异常描述
1   ==java.lang.ArrayIndexOutOfBoundsException==    数组索引越界异常。当对数组的索引值为负数或大于等于数组大小时抛出。
2    java.lang.==ArithmeticException==     算术条件异常。譬如：整数除零等。
3    java.lang.==SecurityException==     安全性异常
4    java.lang.==IllegalArgumentException==    非法参数异常
5    java.lang.ArrayStoreException     数组中包含不兼容的值抛出的异常 
6    java.lang.NegativeArraySizeException    数组长度为负异常 
7    java.lang.==NullPointerException==   空指针异常。当应用试图在要求使用对象的地方使用了null时，抛出该异常。譬如：调用null对象的实例方法、访问null对象的属性、计算null对象的长度、使用throw语句抛出null等等。
      2.IOException

序号    异常名称    异常描述
1    ==IOException==    操作输入流和输出流时可能出现的异常
2    ==EOFException==    文件已结束异常
3    ==FileNotFoundException==    文件未找到异常

序号    异常名称    异常描述
1    ==ClassCastException==    类型转换异常类
2    ==ArrayStoreException==    数组中包含不兼容的值抛出的异常
3   ==SQLException==    操作数据库异常类
4    ==NoSuchFieldException==    字段未找到异常
5    ==NoSuchMethodException==   方法未找到抛出的异常
6    ==NumberFormatException==    字符串转换为数字抛出的异常
7    ==StringIndexOutOfBoundsException==    字符串索引超出范围抛出的异常
8   ==IllegalAccessException==    不允许访问某类异常
9    ==InstantiationException==  当应用程序试图使用Class类中的newInstance()方法创建一个类的实例，而指定的类对象无法被实例化时，抛出该异常

10    ==ClassNotFoundException==    找不到类异常。当应用试图根据字符串形式的类名构造类，而在遍历CLASSPAH之后找不到对应名称的class文件时，抛出该异常
