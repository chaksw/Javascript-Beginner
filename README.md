# What is Javascript

Javascript is a HIGH-LEVEL, PROTOTYPE-BASE OBJECT-ORIENTED, MULTI-PARADIGM, INTERPRETED OR JUEST-IN-TIME COMPLIED, DYNAMIC, SIGNLE-THRAEDED, GARBAGA-COLLECTED PROGRAMMING LANGUAGE with first-class functions and a non-blocking event loop concurrency model

## 1. HIGH-LEVEL

高级语言意味着 Javascript 不需要像 C/C++那般仔细地通过代码实现硬件/内存资源的管理，而是借助于语言本身的内部内存管理机制自动管理，带来的结果就是 JavaScript 运行时间永远不能比 C/C++快，也无法进行内存优化。

### 1.1 Garbage-collected

其中一个 JavaScirpt 内存管理工具成为垃圾回收，即 JavaScipt 会自动删除旧的和未使用的对象。
PS: JavaScript 中几乎所有的东西（数组，函数）都是对象（Object)，(字符串，数字不是)

### 1.2 Interpreted or Just-In-Time compiled

## 2. Multi-paradigm (多范式)

Paradiugm: An approach and mindset of structuring code, which will direct your coding style and technique
(范式是指代码格式)
JavaScirpt 多种代码范式，一般的范式分为：

1. Procedural Programming (程序化编程)
2. Object-oriented programming (OOP) （面向对象编程）
3. Functional programming （函数式编程，即基于函数的代码编程）

另外一种分类方式为：

1. Imperative (命令式)
2. Declarative （声明式）

## 2. PROTOTYPE-BASE Object-oriented

JavaScript 中几乎所有的东西（数组，函数）都是对象（Object)，(字符串，数字不是), 而对象的创建是通过原型继承（prototype-inheritance)实现的, 原型中包含了对象可调用的方法

<div align="center">
<img src="https://github.com/chaksw/Javascript-Beginner/blob/main/imgs/Prototype-base.png?raw=true" width=80%>
</div>

## 3. First-Class function

函数在 JavaScript 中被视为常规变量，也意味着它们可以被当作另一个函数函数的输入参数，也可以作为函数的返回值

<div align="center">
<img src=https://github.com/chaksw/Javascript-Beginner/blob/main/imgs/first-class-fcuntion.png?raw=true" width=80%>
</div>

## 4. Dynamic

在 JavaScript 的变量为动态变量 （弱类型语言），也就是说变量可以定义为任何变量类型，因此一个变量可以被赋值为整形，浮点型，字符串。而 JavaScript Engine 只有在代码执行阶段才会确认变量类型。
PS：typescript 为强类型语言，即需要在定义变量时声明变量类型

## 5. Single-threaded （单线程）& Non-blocking event loop concurrency model（非阻塞事件循环并发模型）

JavaScript 本身运行在一个单线程中，（一次只能执行一个指令（处理器执行代码）），所以我们需要一个处理多个任务同时出现的场景的手段，这就是 Non-blocking event loop concurrency model（非阻塞事件循环并发模型），简单来说就是将一些任务（如数据处理）放在后台执行，在这些任务执行完毕后。
