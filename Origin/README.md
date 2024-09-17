# Origin Version

##### The original version written step by step.
##### And this version is based on easy C++ gramma without variable parameter template feature of C++17. 
##### This also contains an own implementation of the `Any` class.
##### Including three component `Main.cpp`, `threadpool.h` and `threadpool.cpp`


## 1.Main.cpp
##### This is the main file and both a test file connected with threadpool lib.

Before `main` function, you could create a new Task which implement inheritance of `Task` class declared in `threadpool.h`.


In `main` function, Firstly, define a threadpool named pool, set it to the `MODE_CACHED` mode. Then, initialize the thread pool to hold 2 thread at first. Use `pool.start()` member function to activate thread pool. Finally, submit any number tasks to test this thread pool. 


## 2.threadpool.h
##### This is the interface of the thread pool.

### Class `Any`:
###### 6 Special member functions, use template to implement a universal class define. `cast_` member function is declared to implement type casting. 
###### In private member, it use template class to remember datas and use a `Base` smart pointer to point datas.

### Class `Semaphore`:
###### Include 2 member functions and 3 member variables.


### Class `Task`:


### Class `Result`:


### Class `Thread`:


### Class `ThreadPool`:

        



## 3.threadpool.cpp
##### Here is how to achieve the functions.