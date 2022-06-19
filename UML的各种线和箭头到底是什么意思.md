## UML的各种线和箭头到底是什么意思

1 ==泛化==
泛化表示⼀个更泛化的元素和⼀个更具体的元素之间的关系。即继承extends

 ⽤实线空⼼三角形箭头表⽰。箭头方向从==子类到父类==。

<img src="C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220613103358127.png" alt="image-20220613103358127" style="zoom: 50%;" />

2==实现==

实现是⼀种类和接口的关系，类实现接口

虚线空心三角形箭头，类指向接口

<img src="C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220613103507486.png" alt="image-20220613103507486" style="zoom:50%;" />

3==依赖==

是⼀种==使用==的关系，即⼀个类的实现需要另⼀个类的协助。在Java中，⽅法参数需要传⼊另⼀个类的对象，就表⽰依赖这个类。

==虚线箭头==    A类依赖B类  A指向B

<img src="C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220613103729506.png" alt="image-20220613103729506" style="zoom: 50%;" />

4==关联==

表⽰类与类之间的联接,它使⼀个类知道另⼀个类的属性和⽅法，这种关系⽐依赖更强关系⼀般是长期性的。在Java中，⼀个类的全局变量引⽤了另⼀个类，就表⽰关联了这个类

==实线箭头== A类rep中保存B类对象，A指向B

<img src="C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220613104003906.png" alt="image-20220613104003906" style="zoom:50%;" />

5==聚合==

聚合是关联关系的⼀种特例，是强的关联关系。聚合是整体和个体之间的关系，即has-a的关系，整体与个体可以具有各⾃的⽣命周期，部分可以属于多个整体对象，也可以为多个整体对象共享。程序中聚合和关联关系是⼀致的，只能从语义级别来区分

==表⽰⽅式： 尾部为空⼼菱形的实线箭头==，也可没箭头

<img src="C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220613104454429.png" alt="image-20220613104454429" style="zoom:50%;" />



6==组合==

组合也是关联关系的⼀种特例。组合是⼀种整体与部分的关系，即contains-a的关系，⽐聚合更强。部分与整体的⽣命周期⼀
致，整体的⽣命周期结束也就意味着部分的⽣命周期结束，组合关系不能共享。程序中组合和关联关系是⼀致的，只能从语义级别来区分。

==尾部为实⼼菱形的实线箭头==

<img src="C:\Users\王多鱼\AppData\Roaming\Typora\typora-user-images\image-20220613104432969.png" alt="image-20220613104432969" style="zoom:50%;" />