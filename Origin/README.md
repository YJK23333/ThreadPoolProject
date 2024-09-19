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
###### Include 2 member functions `wait()` notice the `mtx_` lock it and wait for its over, `post()` notify all thread this task is locked.

###### The 3 member variables include `resLimit_` memory the most biggest number it could have. `mutex mtx_` define the lock make sure it won't have a deadlock or make more than one thread work for the same task. `condition_variable` is a could give other thread a notice about wait and post.


### Class `Task`:
###### Include two member functions, `exec()` for use task which user need and `setResult()` gives `Result` class a interface to construct its own `Task` member. It also have a virtual member function `run()` gives user a interface to achieve own task through polymorphic.

###### A `Result` class member variable to memory task's result.


### Class `Result`:
###### Constructor receive a `Task` object pointer and a `atomic_bool` variable. Member function `setVal()` updates result data and use semaphore to post the information. Last member function `get()` gives `Any` class's `cast_` function a interface.

###### Four private member including `Any` object to memory data, `Semaphore` to post informations about status, `Task` pointer to point this result's task, besides pointer avoid the situation that two class both include the other one which could case a deadlock, `atomic_bool` to memory it could be use or not.


### Class `Thread`:
###### 


### Class `ThreadPool`:
######
        



## 3.threadpool.cpp
##### Here is how to achieve the functions.