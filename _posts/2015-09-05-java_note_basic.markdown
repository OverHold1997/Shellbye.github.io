---
author: shellbye
comments: true
date: 2015-09-05 11:27:08+00:00
layout: post
slug: java_note_basic
title: Java note basic
categories:
- tech_world
tags:
- java
- job
---

### 语言基础
1. java支持四种类型：接口，类，数组和基本类型。

1. 面向对象基本概念  
封装  
封装给对象提供了隐藏内部特性和行为的能力。对象提供一些能被其他对象访问的方法来改变它内部的数据。
在Java当中，有3种修饰符：public，private和protected。
每一种修饰符给其他的位于同一个包或者不同包下面对象赋予了不同的访问权限。下面列出了使用封装的一些好处：  
1.通过隐藏对象的属性来保护对象内部的状态。  
2.提高了代码的可用性和可维护性，因为对象的行为可以被单独的改变或者是扩展。  
3.禁止对象之间的不良交互提高模块化。  
多态  
多态是编程语言给不同的底层数据类型做相同的接口展示的一种能力。一个多态类型上的操作可以应用到其他类型的值上面。  
继承  
继承给对象提供了从基类获取字段和方法的能力。继承提供了代码的重用行，也可以在不修改类的情况下给现存的类添加新特性。  
抽象  
抽象是把想法从具体的实例中分离出来的步骤，因此，要根据他们的功能而不是实现细节来创建类。
Java支持创建只暴漏接口而不包含方法实现的抽象的类。这种抽象技术的主要目的是把类的行为和实现细节分离开。  
抽象和封装的不同点  
抽象和封装是互补的概念。一方面，抽象关注对象的行为。另一方面，封装关注对象行为的细节。
一般是通过隐藏对象内部状态信息做到封装，因此，封装可以看成是用来提供抽象的一种策略。  

1. 什么是Java虚拟机？为什么Java被称作是“平台无关的编程语言”？
Java虚拟机是一个可以执行Java字节码的虚拟机进程。Java源文件被编译成能被Java虚拟机执行的字节码文件。
Java被设计成允许应用程序可以运行在任意的平台，而不需要程序员为每一个平台单独重写或者是重新编译。
Java虚拟机让这个变为可能，因为它知道底层硬件平台的指令长度和其他特性。

1. 抽象类和接口有什么区别  
0.抽象类和接口都不能够实例化，但可以定义抽象类和接口类型的引用。
一个类如果继承了某个抽象类或者实现了某个接口都需要对其中的抽象方法全部进行实现，
否则该类仍然需要被声明为抽象类。接口比抽象类更加抽象，因为抽象类中可以定义构造器，
可以有抽象方法和具体方法，而接口中不能定义构造器而且其中的方法全部都是抽象方法。
抽象类中的成员可以是private、默认、protected、public的，而接口中的成员全都是public的。
抽象类中可以定义成员变量，而接口中定义的成员变量实际上都是常量。
有抽象方法的类必须被声明为抽象类，而抽象类未必要有抽象方法。  
1.abstract class 在 Java 语言中表示的是一种继承关系，一个类只能使用一次继承关系。
但是，一个类却可以实现多个interface。  
2.在abstract class 中可以有自己的数据成员，也可以有非abstarct的成员方法，
而在interface中，只能够有静态的不能被修改的数据成员（也就是必须是static final的，
不过在 interface中一般不定义数据成员），所有的成员方法都是abstract的。  
3.abstract class和interface所反映出的设计理念不同。
其实abstract class表示的是"is-a"关系，interface表示的是"like-a"关系。  
4.实现抽象类和接口的类必须实现其中的所有方法。抽象类中可以有非抽象方法。接口中则不能有实现方法。  
5.接口中定义的变量默认是public static final 型，且必须给其初值，所以实现类中不能重新定义，也不能改变其值。  
6.抽象类中的变量默认是 friendly 型，其值可以在子类中重新定义，也可以重新赋值。  
7.接口中的方法默认都是 public abstract 类型的。  
8.抽象类可以有构造方法，接口中不能有构造方法  
9.接口更多的是在系统架构设计方法发挥作用，主要用于定义模块之间的通信契约。
而抽象类在代码实现方面发挥作用，可以实现代码的重用  

1. 类的初始化顺序  
对于静态变量、静态初始化块、变量、初始化块、构造器，它们的初始化顺序依次是（静态变量、静态初始化块）>（变量、初始化块）> 构造器  
父类--静态变量  
父类--静态初始化块  
子类--静态变量  
子类--静态初始化块  
父类--变量  
父类--初始化块  
父类--构造器  
子类--变量  
子类--初始化块  
子类--构造器  
[原图](http://www.cnblogs.com/miniwiki/archive/2011/03/25/1995615.html){:target="_blank"}  
![init_order.png](/assets/init_order.png)
参考：[1](http://blog.sina.com.cn/s/blog_4cc16fc50100bjjp.html){:target="_blank"}  
参考：[2](http://len-len.iteye.com/blog/1412463){:target="_blank"}  

1. 请说一下final，finally和finalize的区别？  
final 用于声明属性，方法和类，分别表示属性不可变，方法不可覆盖，类不可继承，
若指向引用，则表明该引用不能指向堆上其他对象。  
final变量初始可以无值，此时成为空白final变量，其赋值操作必须在构造函数进行。  
final变量也可以是static的，所以也可以在静态初始化块中赋值。    
finally是异常处理语句结构的一部分，表示总是执行。  
finalize是Object类的一个方法，在垃圾收集器执行的时候会调用被回收对象的此方法，可以覆盖此方法提供垃圾收集时的其他资源回收，例如关闭文件等。  

1. Math  
Math.round() 四舍五入  

1. Java为什么使用字符串字面量的概念（string literal）?  
使得java的内存利用率更加高效。如果字符串已经在常量池中存在，那么它就不需要被重复创建。  

1. 有没有什么情况下，finally 里面的代码不会被执行?  
当程序通过调用`System.exit()`或者因为致命错误导致进程奔溃时。  

1. 局部变量的初始值是多少?
局部变量没有初始值  

1. 如何防止内存泄露?  
1.注意 Collection 类, 比如 HashMap, ArrayList, 等, 
这些类是常常发生内存泄露的地方。当他们被声明为静态时，他们的生命周期就和应用是一样的  
2.注意 event listeners 和 callbacks. 当 listener 注册了但是没有取消注册，那么就可能导致内存泄露。  

1. java中的null?  
null不是一个合法的实例，它并没有分配到任何内存。它只是一个指示符，表明当前的引用并没有指向任何对象  

1. 序列化  
类通过实现 java.io.Serializable 接口以启用其序列化功能。未实现此接口的类将无法使其任何状态序列化或反序列化。
序列化接口Serializable没有方法或字段，仅用于标识可序列化的语义  
1.什么是串行化 
对象的寿命通常随着生成该对象的程序的终止而终止。有时候，可能需要将对象的状态保存下来，在需要时再将对象恢复。
我们把对象的这种能记录自己的状态以便将来再生的能力。叫作对象的持续性(persistence)。
对象通过写出描述自己状态的数值来记录自己 ，这个过程叫对象的串行化(Serialization) 。
串行化的主要任务是写出对象实例变量的数值。如果变量是另一对象的引用，则引用的对象也要串行化。
这个过程是递归的，串行化可能要涉及一个复杂树结构的单行化，包括原有对象、对象的对象、对象的对象的对象等等。
对象所有权的层次结构称为图表(graph)。   
2.串行化的注意事项  
2.1.串行化能保存的元素  
串行化只能保存对象的非静态成员交量，不能保存任何的成员方法和静态的成员变量，
而且串行化保存的只是变量的值，对于变量的任何修饰符都不能保存。   
2.2.transient关键字  
对于某些类型的对象，其状态是瞬时的，这样的对象是无法保存其状态的。
例如一个Thread对象或一个FileInputStream对象 ，对于这些字段，我们必须用transient关键字标明，否则编译器将报措。 
另外 ，串行化可能涉及将对象存放到磁盘上或在网络上发达数据，这时候就会产生安全问题。
因为数据位于Java运行环境之外，不在Java安全机制的控制之中。对于这些需要保密的字段，不应保存在永久介质中 ，
或者不应简单地不加处理地保存下来 ，为了保证安全性。应该在这些字段前加上transient关键字。  
下面是java规范中对transient关键字的解释：   
The transient marker is not fully specified by The Java Language Specification but is used 
in object serialization to mark member variables that should not be serialized.  
参考：  
[http://www.cnblogs.com/vicenteforever/articles/1471775.html](http://www.cnblogs.com/vicenteforever/articles/1471775.html){:target="_blank"}  [http://blog.csdn.net/zdwzzu2006/article/details/5146335](http://blog.csdn.net/zdwzzu2006/article/details/5146335){:target="_blank"}  

1. Set, List 和 Map Collection classes的区别   
java.util.Set, java.util.List 和 java.util.Map 定义了java中最流行的三个数据结构。
Set 提供唯一性保证，但是是无序的；List 是有序的，但是允许重复； 
Map 是基于哈希的存储结构，它用entry的数组保存键和值；它提供O(1) 时间复杂度的查找操作get（key已知，且无冲突）. 
Set 的常用实现是HashSet, List 的是 ArrayList 和 LinkedList, Map 的是 HashMap, Hashtable 和 ConcurrentHashMap. 
参考： [Set vs List vs Map in Java](http://www.programcreek.com/2009/02/the-interface-and-class-hierarchy-for-collections/){:target="_blank"}  

1. 阻塞队列（BlockingQueue）是什么，它与其他集合类有什么差别？  
BlockingQueue 是一个 Queue 的实现，它位于java.util.concurrent 包中. 与其他类的主要差别，除了存储之外，还有就是阻塞队列提供流控制。
它可以用于线程内部通信，并且根据happens-before原则提供内建的线程安全保证。用阻塞队列可以轻松实现生产者消费者模型。  

1. 什么是不可变对象（Immutable Object）? 如何自定义不可变对象？  
Immutable classes are Java classes whose objects can not be modified once created. 
不可变对象是指创建之后就不能修改的对象。
任何对不可变对象的修改操作都会产生一个新的不可变对象。字符串就是不可变对象。
大多数不可变对象在java也都是final的，这样做是为了防止子类覆盖其方法，这会破坏不可变性。
实现不可变对象时要尤其注意不可以暴露内部的可变对象。赋值等操作一律使用clone等拷贝方法。
从不可变对象获取成员的值时，也不要直接将成员值传出去，而是传递一份拷贝，永远不要传递不可变对象内部的原始引用。
不可变对象必须被正确的构建，也就是不能在构造方法中逸出引用。  
不可变对象的优势：  
1）线程安全的  
2）减少同步操作进而简化开发、提升性能
3）可缓存  
不可变对象的劣势：  
产生大量垃圾，不利于高效的垃圾回收  

1. 枚举Enumeration（since1.0） 和迭代Iterator(since1.2) 的区别?  
迭代（Iterator）允许在遍历的过程中删除元素，枚举（Enumeration）则不行。
枚举（Enumeration）是一个遗留的类，并不是所有的Collection都支持枚举，比如ArrayList就不支持。
迭代（Iterator）更安全，因为它禁止其他线程修改自己正在迭代的集合对象，否则，
它会在hasNext或者next方法中抛出ConcurrentModificationException.   

1. [为什么java中的字符串是final不可变的？](http://javarevisited.blogspot.sg/2010/10/why-string-is-immutable-in-java.html){:target="_blank"}  
1.字符串是在字符串常量池中缓存着的，而且可以被安全共享  
2.因为字符串是不可变的，所以在它创建的时候hashcode就被缓存了，不需要重新计算。
这就使得字符串很适合作为Map中的键，字符串的处理速度要快过其它的键对象。这就是HashMap中的键往往都使用字符串。    

1. StringBuilder与StringBuffer的区别  
类似HashMap和HashTable，HashTable是线程安全的，很多方法都是synchronized方法，而HashMap不是线程安全的，
但其在单线程程序中的性能比HashTable要高。支持线程同步保证线程安全而导致性能下降。
StringBuilder类不是线程安全的，但其在单线程中的性能比StringBuffer高。

1. 字符串（String）  
1)字符串是不可变的  
2)当用双引号代表字符串时，字符串就会在字符串池中创建，我们的引用就指向新创建的字面量的地址。
当我们用==符号来比较字符串字面量时，因为它们是同一个对象，所以会返回true。  
3)“+”是根据字符串重载过的，它内部只用StringBuilder或StringBuffer并结合append方法实现。  
4)字符串内部使用字符数组实现。  
5)字符串覆盖了equals()和hashcode()两个方法。如果两个字符串中的字符数组完全一样，则两个字符串是相等的。  

1. ArrayList 和 LinkedList 的区别  
LinkedList 和 ArrayList 都是接口 List 的实现，但是他们内部的工作原理相差甚远。
主要的差距是ArrayList是通过可以动态调整大小的array实现的，而LinkedList是用双向列表实现的。所以：  
1.ArrayList 获取元素很快.  
2.LinkedList 插入和删除元素很快.  
3.LinkedList 需要更多的内存因为它持有更多的指针。  

1. [如何检查 Array 中的重复元素？](http://javarevisited.blogspot.sg/2012/02/how-to-check-or-detect-duplicate.html){:target="_blank"}  
1.暴力双层for循环  
2.用 Set 结合contains()方法  
3.用 HashSet 结合 add()方法  

1. [Array和ArrayList有何区别？](http://java67.blogspot.sg/2012/12/difference-between-array-vs-arraylist-java.html){:target="_blank"}  
1.Array可以包含基本类型和对象类型，ArrayList只能包含对象类型。  
2.Array大小是固定的，ArrayList的大小是动态变化的。  
3.ArrayList提供了更多的方法和特性，比如：addAll()，removeAll()，iterator()等等。  
4.Array通过length变量获取长度，ArrayList通过size()方法获得。  
对于基本类型数据，集合使用自动装箱来减少编码工作量。但是，当处理固定大小的基本数据类型的时候，这种方式相对比较慢。  

1. [HashMap和Hashtable有什么区别？](http://java67.blogspot.sg/2012/08/5-difference-between-hashtable-hashmap-Java-collection.html){:target="_blank"}  
HashMap和Hashtable都实现了Map接口，因此很多特性非常相似。但是，他们有以下不同点：
1.HashMap允许键和值是null，而Hashtable不允许键或者值是null。  
2.Hashtable是同步的，而HashMap不是。因此，HashMap更适合于单线程环境，而Hashtable适合于多线程环境。  
3.HashMap提供了可供应用迭代的键的集合，因此，HashMap是快速失败的。另一方面，Hashtable提供了对键的列举(Enumeration)。  
4.HashTable比较过时，建议使用ConcurrentHashMap,一般认为Hashtable是一个遗留的类。  
除了上面提到的三个类，[Map](http://docs.oracle.com/javase/7/docs/api/java/util/Map.html){:target="_blank"}接口的常用实现还有：  
1)LinkedHashMap：继承自HashMap，保持了元素的插入顺序，因此遍历时的顺序是可预测的  
2)TreeMap：基于红黑树的键有序的实现，get等操作时间复杂度logN。该实现也不是线程安全的  
3)WeakHashMap:基于弱引用（WeakReference：也是用来描述非必须对象的。但是它的强度比软引用更弱一点，
被弱引用关联的对象只能生存到下一次垃圾收集发生之前。当垃圾收集器工作时，无论当前内存是否足够，
都会回收掉只被弱引用关联的对象）作为键的map，其键只能撑到下一次垃圾回收。  

1. ConcurrentHashMap, Hashtable 和 Synchronized Map 有和异同？  
首先，它们都是线程安全的。但是它们实现线程安全的方式却不一样。
HashTable是一个遗留的类，它使用java内置的synchronized方法保证线程安全，
其内部的所有方法都通过关键字同步，正是因为这个，它的效率非常的低。
Synchronized Map与HashTable的主要差别是它并不是一个遗留的类，
可以通过它来包装任何的Map实现，并通过Collections.synchronizedMap()方法获取其同步的版本。
ConcurrentHashMap是专门为并发定制的一个类，并进行了一些优化。比如它在加锁的时候，
并不是想HashTable一样加锁整个map，而是只加锁其中一部分，进而提高并发性。
但是ConcurrentHashMap并不允许null作为键值，HashMap是允许的。  

1. Comparable 和 Comparator    
Comparable 是在集合内部定义的方法实现的排序，Comparator 是在集合外部实现的排序，
所以，如想实现排序，就需要在集合外定义 Comparator 接口的方法或在集合内实现 Comparable 接口的方法。
Comparable是将元素自身变成可比较的，并且在比较时时自己和别的元素比较。
它像运动员，它的比较方法compareTo接收一个参数，即它的对手，返回两者之间的比较结果。
Comparator是比较别的元素的，它更像裁判，它的比较方法compare接收两个参数，
它返回这两个元素的比较结果。  

1. 用自定义对象作为Collection 类（比如 Map 或者 Set）的键需要覆盖哪些方法?  
覆盖 equals() 和 hashCode() ，因为这是用来判断键是否相同的方法。  
sort还需要compareTo()  

1. HashSet 是如何实现的?  
HashSet内部使用了一个内容都一样只是键值不一样的HashMap，
它的contains等方法是通过其内部的map的containsKey等方法来实现的。  

1. Queue接口的 poll() 和 remove() 有什么差别?  
当队列为空时 remove() 将会抛出异常而 poll() 返回 null.  

1. 如何同步化 ArrayList?  
{% highlight java %}
//Use Collecions.synzhonizedList method
List list = Collections.synchronizedList(new ArrayList());
//If you wanna use iterator on the synchronized list, use it
//like this. It should be in synchronized block.
synchronized (list) {
  Iterator iterator = list.iterator();
  while (iterator.hasNext())
      ...
      iterator.next();
      ...
}
{% endhighlight %}  

1. 迭代时，快速失败（fail-fast）和安全失败（fail-safe）的差别  
当一个线程在遍历集合对象时，如果有其他线程在修改该对象，
那么，快速失败（fail-fast）抛出 ConcurrentModificationException。
安全失败（fail-safe）则是在一个集合对象的副本上进行遍历，所以不会抛出异常。  

1. "=="和 equals 方法究竟有什么区别？  
1.==操作符更像是物理上的比较，专门用来比较两个变量的值是否相等，
也就是用于比较变量所对应的内存中所存储的数值是否相同，要比较两个基本类型的数据或两个引用变量是否相等，
只能用==操作符。"==" 是用来检查两个引用是否指向了堆中一个相同的对象。  
2.equals方法像是逻辑上的比较，是用于比较两个独立对象的内容是否相同，就好比去比较两个人的长相是否相同，
它比较的两个对象是独立的。例如，对于下面的代码：
`String a = new String("foo");
String b = new String("foo");`
两条 new 语句创建了两个对象，然后用 a/b 这两个变量分别指向了其中一个对象，这是两个不同的对象，
它们的首地址是不同的，即 a 和 b 中存储的数值是不相同的，所以，表达式 a==b 将返回 false，
而这两个对象中的内容是相同的，所以，表达式 `a.equals(b)`将返回true。  
3.如果一个变量指向的数据是对象类型的，那么，这时候涉及了两块内存，对象本身占用一块内存（堆内存），
变量也占用一块内存，例如 `Objet obj = new Object();`变量 obj是一个内存，`new Object()`是另一个内存，
此时，变量obj所对应的内存中存储的数值就是对象占用的那块内存的首地址。对于指向对象类型的变量，
如果要比较两个变量是否指向同一个对象，即要看这两个变量所对应的内存中的数值是否相等，这时候就需要用==操作符进行比较。  
4.在实际开发中，我们经常要比较传递进行来的字符串内容是否等，
例如，`String input = "some str";input.equals(“quit”);`，许多人稍不注意就使用==进行比较了，这是错误的。
记住，字符串的比较基本上都是使用 equals 方法。如果一个类没有自己定义 equals 方法，
那么它将继承 Object 类的 equals 方法，Object 类的 equals 方法的实现代码如下：
`
boolean equals(Object o){
	return this==o;
}
`
这说明，如果一个类没有自己定义 equals 方法，它默认的 equals 方法（从 Object 类继承的）就是使用==操作符，
也是在比较两个变量指向的对象是否是同一对象，这时候使用equals 和使用==会得到同样的结果，
如果比较的是两个独立的对象则总返回 false。如果你编写的类希望能够比较该类创建的两个实例对象的内容是否相同，
那么你必须覆盖 equals方法，由你自己写代码来决定在什么情况即可认为两个对象的内容是相同的。  

1. 静态变量和实例变量的区别？  
在语法定义上的区别：静态变量前要加 static 关键字，而实例变量前则不加。  
在程序运行时的区别：实例变量属于某个对象的属性，必须创建了实例对象，其中的实例变量才会被分配空间，才能使用这个实例变量。
静态变量不属于某个实例对象，而是属于类，所以也称为类变量，只要程序加载了类的字节码，不用创建任何实例对象，
静态变量就会被分配空间，静态变量就可以被使用了。  
总之，实例变量必须创建对象后才可以通过这个对象来使用，静态变量则可以直接使用类名来引用。  

1. Overload 和 Override 的区别。Overloaded 的方法是否可以改变返回值的类型?  
重载 Overload 表示同一个类中可以有多个名称相同的方法，但这些方法的参数列表各不相同（即参数个数或类型不同）。  
重写 Override 表示子类中的方法可以与父类中的某个方法的名称和参数完全相同，
通过子类创建的实例对象调用这个方法时，将调用子类中的定义方法，这相当于把父类中定义的那个完全相同的方法给覆盖了，
这也是面向对象编程的多态性的一种表现。  
不可以，因为返回值可以被忽略，容易产生二义性，因为返回值可以被忽略。  

1. 字符串池?  
字符串池是java堆中一个特殊的存储位置，一般都是在永久代，用来存储字符串字面量，比如“abc”等。
当程序用字面量创建新的字符串对象时，JVM首先在字符串池中检查该字面量是否已经存在，
若存在则直接返回，从而避免创建一个新对象。这种检查只在用字面量创建时才使用，
如果是用`new()`方法创建，则一定会创建一个新的字符串对象，不管是否已经存在与字符串池中。
只有使用引号包含文本的方式创建的String对象之间使用“+”连接产生的新对象才会被加入字符串池中。
对于所有包含new方式新建对象（包括null）的“+”连接表达式，它所产生的新对象都不会被加入字符串池中。  
下图来自[这里](http://www.journaldev.com/797/what-is-java-string-pool){:target="_blank"}，
清晰的说明了字符串池和用new创建字符串时的差别。  
![string](/assets/String-Pool-Java1.png) 

### 其他
1. 库（Library）和框架（Framework）的主要差别  
库和框架的主要差别就是控制反转（ Inversion of Control）  
当你调用库中的一个方法时，你处于控制地位，但是在框架内部，却是框架在调用你的细节。  
