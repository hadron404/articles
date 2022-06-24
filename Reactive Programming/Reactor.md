Reactor是一个支持背压（backpressure）的实现了`Reactive Streams`规范的运行在JVM上的非阻塞反应式编程的类库。



为什么首先需要一个反应式库？

Java提供了两种异步编程模型，如下所示

- **Callbacks** ：异步方法没有返回值，但需要一个额外的 *callback* 参数（lambda或匿名类），当结果可用时，调用该参数
- **Futures** ： 异步方法立即返回一个 *Future<T>*, 异步进程计算一个 *T* 值，但 Future 对象封装了对它的访问。该值不是立即可用的，并且可以轮询对象，直到该值可用为止。
  - Java8 增加了 **CompletableFuture**

这两种技术都有他们的局限性。

- Callbacks 很难组合在一起，很快会使得代码很难阅读和维护（称为 **回调地狱**（Callback Hell））。
- Future 对象比回调要好一点，但它们在组合方面仍然做得不好，尽管 CompletableFuture 将多个对象编排 Future 在一起是可行的，但并不容易。
  - Future 通过调用 get() 方法很容易导致对象的另一种阻塞情况。
  - 不能支持惰性计算（lazy computation）。
  - 对异常的高级处理支持比较弱。





参考文献

* [响应式编程简介](https://juejin.cn/post/6844903574208512013)
* Reactor 开发主力 Stephane
  * https://www.youtube.com/watch?v=Tr04KiJdAXQ
  * https://www.youtube.com/watch?v=zls8ZLry68M 