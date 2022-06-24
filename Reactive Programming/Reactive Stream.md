



# Reactive Streams

> Reactive Streams is an initiative to provide a standard for asynchronous stream processing with non-blocking back pressure.
>
> —— http://www.reactive-streams.org/

**Reactive Streams** (响应式流/反应流) 是JDK9引入的一套标准，是一套基于发布/订阅模式的数据处理规范。响应式流从2013年开始，作为提供非阻塞背压的异步流处理标准的倡议。 它旨在解决处理元素流的问题——如何将元素流从发布者传递到订阅者，而不需要发布者阻塞，或订阅者有无限制的缓冲区或丢弃。更确切地说，Reactive流目的是“找到最小的一组接口，方法和协议，用来描述必要的操作和实体以实现这样的目标：以非阻塞背压方式实现数据的异步流”。



**Reactive Streams** 定义了如下四个接口：

* **Subscription** 接口定义了连接发布者和订阅者的方法
* **Publisher<T>** 接口定义了发布者的方法
* **Subscriber<T>** 接口定义了订阅者的方法
* **Processor<T,R>** 接口定义了处理器



背压（Black Pressure）

如果生产者发出的信息比消费者能够处理消息最大量还要多，消费者可能会被迫一直在抓消息，耗费越来越多的资源，埋下潜在的崩溃风险。为了防止这一点，需要一种机制使消费者可以通知生产者，降低消息的生成速度。生产者可以采用多种策略来实现这一要求，这一机制称为**背压**。



参考文献

* [Reactive Streams](http://www.reactive-streams.org/)
* [Reactive-Java](https://liuyazong.github.io/reactive-java/)
* [JDK9 新特性 Reactive Stream 响应式流](https://blog.csdn.net/qq_34285557/article/details/104569122)

