# ThreadPool
A simple C++11 Thread Pool implementation

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