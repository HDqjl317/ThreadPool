# ThreadPool
##A simple C++11 Thread Pool implementation
这是一个简单的C++11实现的线程池，代码很简单。
原理就是管理一个任务队列和一个工作线程队列。
工作线程不断的从任务队列取任务，然后执行。如果没有任务就等待新任务的到来。添加新任务的时候先添加到任务队列，然后通知任意(条件变量notify_one)一个线程有新的任务来了。


## create thread pool with 4 worker threads
```c++
ThreadPool pool(4);
```

## enqueue and store future
```c++
auto result = pool.enqueue([](int answer) { return answer; }, 42);
```
## get result from future
```c++
std::cout << result.get() << std::endl;
```
