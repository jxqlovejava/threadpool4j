# 2.1.0 2015-04-13
新增特性：

1. 线程池初始化时检测是否存在默认的default线程池。

修正BUG：

1. 线程池状态检查开关或者线程状态检查开关任意一个关闭时，在销毁线程池时会报错。


#2.0.0   2014-11-11
新增特性：

1. 支持执行需返回处理结果（实现Callable接口）的异步任务。
2. 并行调用：支持并行执行多个需返回处理结果的异步任务，并设置超时时间。
3. 支持查询指定名称的线程池是否存在。

修订：

1. FailHandler传入参数的类型由Runnable改成Object。

#1.1.0   2014-07-03
新增特性：

1. 增加FailHandler支持，业务可处理提交失败的任务。
  - 当线程池队列满导致任务提交被拒绝时，可以实现FailHandler接口编写处理器，处理被拒绝的任务。
  - 实现了默认的DefaultFailHandler，当任务被拒绝时，通过log4j输出一条ERROR日志。

#1.0.0   2014-06-05
1. 支持多线程池：每个线程池有独立的名称，可配置不同的线程数。
2. 使用简单：只需一行代码就可以执行异步任务。
3. 完善的统计和健康状态信息：每分钟输出一次各个线程池的执行任务数和队列积压情况；每分钟输出一次各个线程池的线程状态信息。
4. 无框架依赖性，适用于所有使用Java语言的应用。