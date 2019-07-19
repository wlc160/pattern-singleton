# pattern-singleton

设计模式之单例模式：

1、定义：
确保一个类在任何情况下都绝对只有一个实例，并提供一个全局访问点（创建型模式），例如在javaEE中：ServletContext、ServletConfig、ApplicationContext等；在现实生活中：国家主席、公司CEO、部门经理等；

（1）优点：在内存中只有一个实例，减少内存开销；可以避免对资源的多重引用；设置全局访问点，严格控制访问

（2）缺点：没有接口，扩展困难；若要扩展对象，只有修改代码，没有代码途径

2、分类：

（1）饿汉式单例（在单例类首次加载时就创建实例，缺点就是浪费内存空间，优点就是没有加任何的锁、执行效率比较高，在用户体验上比懒汉式好 ）

（2）懒汉式单例（被外部类调用时才创建实例，可以减少内存开销，但是线程不安全，可用双重检查锁方式适中解决该问题）

（3）注册式单例（将每个实例都缓存到统一的容器中，用唯一标识获取实例，其中有两种写法：枚举登记和容器缓存）

（4）ThreadLocal单例（保证单个线程的全局唯一，且天生线程安全，但是不能保证创建的对象全局唯一）

3、破坏单例模式的方式：

 通过反射、克隆、反序列化的方式来获取新的对象，主要是体现在对象存储的内存地址

4、实现方式特点总结：

（1）私有化构造器  

（2）保证线程安全  

（3）延迟加载  

（4）防止序列化和反序列化破坏单例  

（5）防御反射破坏单例



