# **JAVA NOTE**
**静态方法为什么不能调用非静态成员?**
这个需要结合 JVM 的相关知识，**主要原因如下**：

1.静态方法是属于类的，在类加载的时候就会分配内存，可以通过类名直接访问。而非静态成员属于实例对象，只有在对象实例化之后才存在，需要通过类的实例对象去访问。
2.在类的非静态成员不存在的时候静态成员就已经存在了，此时调用在内存中还不存在的非静态成员，属于非法操作。

**Java和C++的区别**
1.Java 不提供指针来直接访问**内存**，程序内存更加安全
2.Java 的类是**单继承**的，C++ 支持**多重继承**；虽然 Java 的类不可以多继承，但是接口可以多继承。
3.Java **有自动内存管理垃圾回收机制(GC)**，不需要程序员手动释放无用内存。
4.C ++同时支持**方法重载和操作符重载**，但是 Java 只支持**方法重载**（操作符重载增加了**复杂性**，这与 Java 最初的设计思想不符）。