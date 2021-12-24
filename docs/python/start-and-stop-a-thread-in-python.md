# Python 中线程的启动和停止

> 原文:[https://www . geesforgeks . org/start-and-stop-a-thread-in-python/](https://www.geeksforgeeks.org/start-and-stop-a-thread-in-python/)

**线程库**可以用来执行任何可以在自己线程中调用的 Python。为此，创建一个线程实例并提供您希望作为目标执行的可调用，如下面给出的代码所示–

**Code #1 :**

```py
# Code to execute in an independent thread
import time

def countdown(n):
    while n > 0:
        print('T-minus', n)
        n -= 1
        time.sleep(5)

# Create and launch a thread
from threading import Thread
t = Thread(target = countdown, args =(10, ))
t.start() 
```

创建线程实例时，直到调用其`start()`方法(使用您提供的参数调用目标函数)时，它才开始执行。线程在它们自己的完全由主机操作系统管理的系统级线程(例如，POSIX 线程或窗口线程)中执行。一旦启动，线程独立运行，直到目标函数返回。

**代码#2:查询一个线程实例，看看它是否还在运行。**

```py
if t.is_alive():
    print('Still running')
else:
    print('Completed')
```

也可以请求加入一个线程，等待它终止。

```py
t.join()
```

解释器保持运行，直到所有线程终止。对于长时间运行的线程或永远运行的后台任务，考虑让线程变得混乱。

**代码#3 :**

```py
t = Thread(target = countdown, args =(10, ), daemon = True)
t.start()
```

无法连接后台线程。但是，当主线程终止时，它们会自动销毁。除了所示的两个操作之外，线程没有太多其他事情可做。例如，没有终止线程、向线程发送信号、调整其调度或执行任何其他高级操作的操作。要拥有这些功能，请自行构建。为了能够终止线程，线程必须被编程为在选定的点轮询
退出。例如，将你的线程放在一个类中，比如下面代码中提到的那个–

**代码#4:将线程放入类中。**

```py
class CountdownTask:

    def __init__(self):
    self._running = True

def terminate(self):
    self._running = False

def run(self, n):
    while self._running and n > 0:
        print('T-minus', n)
        n -= 1
        time.sleep(5)

c = CountdownTask()
t = Thread(target = c.run, args =(10, ))
t.start()
...
# Signal termination
c.terminate() 

# Wait for actual termination (if needed) 
t.join() 
```

如果线程执行阻塞操作(如输入/输出)，线程终止轮询可能很难协调。例如，在输入/输出操作上无限期阻塞的线程可能永远不会返回来检查它是否已被终止。为了正确处理这种情况，线程需要仔细编程，以利用超时循环，如下面给出的代码所示。

**代码#5 :**

```py
class IOTask:
    def terminate(self):
        self._running = False

        def run(self, sock):
            # sock is a socket

            # Set timeout period
            sock.settimeout(5) 
            while self._running:

                # Perform a blocking I/O operation w/timeout
                try:
                    data = sock.recv(8192)
                    break
                except socket.timeout:
                    continue
                # Continued processing
                ...
        # Terminated
        return
```

由于全局解释器锁(GIL)，Python 线程被限制在一个执行模型中，该模型在任何给定时间只允许一个线程在解释器中执行。因此，Python 线程通常不应该用于计算密集型任务，因为这些任务需要在多个 CPU 上实现并行。它们更适合于输入/输出处理和处理执行阻塞操作的代码中的并发执行(例如，等待输入/输出、等待数据库的结果等)。).

**代码#6:通过继承线程类**定义的线程

```py
from threading import Thread

class CountdownThread(Thread):
    def __init__(self, n):
        super().__init__()
        self.n = 0

    def run(self):
        while self.n > 0:       
    print('T-minus', self.n)
    self.n -= 1
    time.sleep(5)

c = CountdownThread(5)
c.start()
```

尽管这种方法可行，但它在代码和线程库之间引入了额外的依赖性。也就是说，只有生成的代码可以在线程的上下文中使用，而前面显示的技术涉及编写不明确依赖线程的代码。通过将您的代码从这种依赖关系中释放出来，它可以在其他可能涉及或不涉及线程的上下文中使用。例如，可以使用下面给出的代码，使用多处理模块在单独的进程中执行代码

**代码#7 :**

```py
import multiprocessing
c = CountdownTask(5)
p = multiprocessing.Process(target = c.run)
p.start()
...
```

同样，这仅在`CountdownTask class`以对实际并发方式(线程、进程等)中立的方式编写时有效。