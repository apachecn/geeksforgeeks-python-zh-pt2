# Python 中的计时器对象

> 原文:[https://www.geeksforgeeks.org/timer-objects-python/](https://www.geeksforgeeks.org/timer-objects-python/)

计时器对象用于表示需要被安排在某个时刻之后运行的动作。这些对象被安排在执行操作的单独线程上运行。然而，定时器初始化的时间间隔可能不是解释器实际执行动作的实际时刻，因为实际调度对应于定时器对象的线程是线程调度器的责任。

定时器是 python 中定义的 Thread 类的一个子类。通过显式调用定时器对应的 start()函数来启动。

**创建计时器对象**

**语法:**

```py
threading.Timer(interval, function, args = None, kwargs = None) 
```

创建一个计时器，它将在间隔秒后运行带有参数 args 和关键字 args 的函数。如果参数为无(默认值)，则将使用空列表。如果 kwargs 为无(默认值)，则将使用空字典。

```py
# Program to demonstrate
# timer objects in python

import threading
def gfg():
    print("GeeksforGeeks\n")

timer = threading.Timer(2.0, gfg)
timer.start()
print("Exit\n")
```

**输出:**

```py
Exit
GeeksforGeeks
```

**说明:**上面的程序，调度 gfg()函数在 start()函数调用后 5 秒间隔后运行。

**取消定时器**

**语法:**

```py
timer.cancel()
```

停止计时器，并取消计时器动作的执行。这只有在计时器仍处于等待阶段时才会起作用。

```py
# Program to cancel the timer
import threading

def gfg():
    print("GeeksforGeeks\n")

timer = threading.Timer(5.0, gfg)
timer.start()
print("Cancelling timer\n")
timer.cancel()
print("Exit\n")
```

输出:

```py
Cancelling timer
Exit
```

本文由 [**Mayank Kumar**](https://www.linkedin.com/in/mayank-kumar-a9058b137/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。