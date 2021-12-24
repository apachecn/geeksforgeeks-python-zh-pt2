# Python 中基于线程的并行

> 原文:[https://www . geesforgeks . org/基于线程-并行-python/](https://www.geeksforgeeks.org/thread-based-parallelism-python/)

多线程程序由子程序组成，每个子程序由不同的线程分别处理。多线程允许程序执行中的并行。所有活动线程并发运行，有效地共享 CPU 资源，从而使程序执行更快。多线程通常用于以下情况:

1.  有一些子程序的输出需要由主程序组合。
2.  主程序包含相对独立的代码段。

多线程程序在同一个进程中同时处理不同的任务，不同的线程和主线程共享数据空间。

**开始新螺纹**

python 中的线程模块提供了用于创建新线程的函数调用。__init__ 函数用于初始化与新线程相关联的数据，而 run 函数则在线程开始执行时定义线程的行为。

为了创建一个新线程:

1.  创建线程类的子类。
2.  重写线程类的 __init__ 函数。此方法将初始化特定于线程的日期。
3.  重写 run 方法以定义线程的行为。

```py
# Python program to demonstrate
# initializing a new thread
import threading

class thread(threading.Thread):
    def __init__(self, thread_name, thread_ID):
        threading.Thread.__init__(self)
        self.thread_name = thread_name
        self.thread_ID = thread_ID
    def run(self):
        print(str(self.thread_name) +"  "+ str(self.thread_ID));

thread1 = thread("GFG", 1000)
thread2 = thread("GeeksforGeeks", 2000);

thread1.start()
thread2.start()

print("Exit")
```

**输出:**

```py
GFG 1000
GeeksforGeeks 2000
Exit
```

**穿线模块**

python 中的线程模块为线程提供了强大的高级支持。

线程模块定义了以下用于获取线程相关数据的函数调用。所有这些功能都是自动执行的。

1.  **active_count():** 返回当前活动的线程对象数。返回的计数等于枚举()返回的列表长度。
    **语法:**

    ```py
    threading.active_count()
    ```

2.  **current_thread():** 返回当前 thread 对象，对应调用者的控制线程。如果调用方的控制线程不是通过线程模块创建的，则会返回一个功能有限的伪线程对象。
    **语法:**

```py
threading.current_thread()
```

*   **get_ident():** 返回当前线程的‘线程标识符’。这是一个非零整数。它的价值没有直接意义；它旨在作为一个神奇的 cookie，例如用于索引线程特定数据的字典。当一个线程退出并创建另一个线程时，可以回收线程标识符。
    **语法:**

    ```py
    threading.get_ident()
    ```

    *   **枚举():**返回当前所有线程对象的列表。该列表包括后台线程、由 current_thread()创建的虚拟线程对象和主线程。它不包括已终止的线程和尚未启动的线程。
    **语法:**

    ```py
    threading.enumerate()
    ```

    *   **main_thread():** 返回主 thread 对象。在正常情况下，主线程是启动 Python 解释器的线程。
    **语法:**

    ```py
    threading.main_thread()
    ```

    *   **settrace(func):** 为从线程模块启动的所有线程设置一个跟踪函数。在调用函数的 run()方法之前，该函数将被传递给每个线程的 sys.settrace()。
    **语法:**

    ```py
    threading.settrace(func)
    ```

    *   **设置配置文件(功能):**为从线程模块启动的所有线程设置配置文件功能。在调用其 run()方法之前，该函数将被传递给每个线程的 sys.setprofile()。
    **语法:**

    ```py
    threading.setprofile(func)
    ```

    *   **stack_size([size]):** Return the thread stack size used when creating new threads.
    **Syntax:**

    ```py
    threading.stack_size([size])
    ```

    该模块还包括常数:

    *   **超时 _ 最大值:**阻塞函数(锁定.获取()、锁定.获取()、条件.等待()等超时参数允许的最大值。).指定大于该值的超时将引发 OverflowError。
        **语法:**

        ```py
        threading.TIMEOUT_MAX
        ```

    ```py
    # Python program to demonstrate
    # threading module
    import threading

    def trace_function():
        print("Passing the trace function")
    def profile():
        print("Setting the profile of thread: " + str(threading.current_thread().getName()))

    class thread(threading.Thread):
        def __init__(self, thread_name, thread_ID):
            threading.Thread.__init__(self)
            self.thread_name = thread_name
            self.thread_ID = thread_ID
        def run(self):
            print(str(self.thread_ID));
            print("Number of active threads: "+ str(threading.active_count()))
            print("Name of current thread: " + str(threading.current_thread().getName()))

    thread1 = thread("GFG", 1000)
    thread2 = thread("GeeksforGeeks", 2000);
    print("Name of main thread: " + str(threading.main_thread().getName()))
    print("Identity of main thread: "+ str(threading.get_ident()))
    print("Stack size = " + str(threading.stack_size()))
    print(threading.settrace(trace_function()))
    threading.setprofile(profile())

    thread1.start()
    thread2.start()
    print("Enumeration list: ")
    print(threading.enumerate())
    print("Exit")
    ```

    **输出:**

    ```py
    Name of main thread: MainThread
    Identity of main thread: 139964150720320
    Stack size = 0
    Passing the trace function
    None
    Setting the profile of thread: MainThread
    1000
    Number of active threads: 2
    Name of current thread: Thread-1
    2000
    Number of active threads: 2
    Name of current thread: Thread-2
    Enumeration list: 
    []
    Exit
    ```

    **参考:**

    *   **[Python 文档](https://docs.python.org/3/library/threading.html)**

    本文由 [**Mayank Kumar**](https://www.linkedin.com/in/mayank-kumar-a9058b137/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。