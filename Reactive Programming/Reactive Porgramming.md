# Reactive Programming

## 本文内容

* 阻塞架构 / 异步架构
* 反应式（Reactive）编程



> 在微服务架构下，我们把一些核心的业务抽取出来，作为独立的服务。
>
> 服务与服务之间通过RPC或者HTTP进行通信，这意味着**微服务架通常是I/O密集型的**。所以这也决定了**现代互联网架构的性能瓶颈：I/O**。



## 阻塞架构

> 阻塞式系统构建于Servlet框架上（Servert 3.0之前），这样的系统是阻塞的和多线程的，这意味着每个连接使用一个线程来处理请求，I/O操作是通过从线程池中选择一个工作线程来执行I/O，并且阻塞请求线程，直到工作线程完成为止。



**阻塞式系统缺乏弹性**，在高并发场景下，如果应用B延迟增加或由于错误导致应用A重试，那么应用A连接和线程数量就会不断增加。当这种情况发生时，应用A的线程数量激增会导致服务器负载激增并使集群不堪重负。为了解决这种问题，我们需要限制限制创建线程的数量，引入熔断和限流机制（Hystrix、Sentinel）帮助我们在发生了这些事情期间保持阻塞系统的稳定性。

## 异步架构





> There are, broadly, two ways one can improve a program’s performance:
>
> - **parallelize** to use more threads and more hardware resources.
> - **seek more efficiency** in how current resources are used.



并行化的处理方式主要有以下几个问题

1. 线程本身就是比较昂贵的资源，创建过多的线程会占用更多的内存。
2. 线程上下文切换比较耗时并且会增加cpu的负载。
3. 需要解决线程间的同步问题。

## 反应式编程（Reactive Programming）

> In Computing, **reactive programming** is a `declarative programming paradigm` concerned with `data streams` and the propagation of change. With this paradigm, it's possible to express static (e.g., arrays) or dynamic (e.g., event emitters) *data streams* with ease, and also communicate that an inferred dependency within the associated *execution model* exists, which facilitates the automatic propagation of the changed data flow.
>
> — https://en.wikipedia.org/wiki/Reactive_programming
>
> 在计算中，响应式编程或反应式编程（英语：Reactive Programming）是一种面向数据流和变化传播的声明式编程范式。这意味着可以在编程语言中很方便地表达静态或动态的数据流，而相关的计算模型会自动将变化的值通过数据流进行传播
>
> — https://zh.wikipedia.org/wiki/响应式编程

### 反应式库

常见的Java反应式库

* Reactor
* RxJava
* JDK 9+ 的 Flow 静态子类
* Vert.x 、MongoDB 响应式流驱动

反应式库旨在解决JVM上经典异步方法的缺点，同时关注一些额外的方面：

* 可组合性（ **Composability** ）和可读性（ **readability** ）
* 使用丰富的操作符（ **operators** ）表操纵数据流
* 在你订阅（ **subscribe** ）之前什么都不会发生
* 背压能力（ **Backpressure** ）或消费者向生产者发出排放速度过高信号的能力
* 与并发无关（ **Concurrency-agnostic** ）的高级（ **High-Level** ）但高价值（ **High-Value** ）的抽象

> 原文参见: [From Imperative To Reactive Programming](https://projectreactor.io/docs/core/release/reference/index.html#_from_imperative_to_reactive_programming)
>
> 其他语言的Reactive库可参考 https://github.com/ReactiveX





### 反应式编程不是银弹（Silver Bullet）



> **根据Netfix的实践，对于CPU密集型的应用使用异步架构并不会有很大的提升，对于I/O密集型应用使用异步架构降低了网络连接的成本，比阻塞式系统有很好的弹性优势，将会有较大的性能提升，大约25%左右。**
>
> **异步架构的优点看起来很棒，但是上面的优点是以牺牲操作为代价的**。阻塞式系统（命令式编程）很容易理解和调试。

## 参考文献

* [反应式宣言](https://www.reactivemanifesto.org/zh-CN)
* [Spring | Reactive](https://spring.io/reactive)
* [异步架构与反应式编程](https://juejin.cn/post/6914825057604747271)
* [JDK9 新特性 Reactive Stream 响应式流](https://blog.csdn.net/qq_34285557/article/details/104569122)
* [Reactive java规范](https://github.com/reactive-streams/reactive-streams-jvm)