# 什么是 Python 全局解释器锁(GIL)

> 原文:[https://www . geesforgeks . org/什么是 python-全局-解释器-lock-gil/](https://www.geeksforgeeks.org/what-is-the-python-global-interpreter-lock-gil/)

Python 全局解释器锁(GIL)是一种进程锁，python 在处理进程时会用到它。一般来说，Python 只使用一个线程来执行一组书面语句。这意味着在 python 中一次只执行一个线程。单线程进程和多线程进程的性能在 python 中是相同的，这是因为 python 中的 GIL。我们无法在 python 中实现多线程，因为我们有全局解释器锁，它限制线程并作为单线程工作。

**GIL 为 Python 解决了什么问题:**

Python 有其他语言没有的东西，那就是引用计数器。在引用计数器的帮助下，我们可以计算 python 内部为数据对象赋值的引用总数。由于这个计数器，我们可以计数引用，当这个计数达到零时，变量或数据对象将自动释放。例如

```py
# Python program showing
# use of reference counter
import sys

geek_var = "Geek"
print(sys.getrefcount(geek_var))

string_gfg = geek_var
print(sys.getrefcount(string_gfg))
```

**输出:**

```py
4
5

```

这个引用计数器变量需要保护，因为有时两个线程同时增加或减少它的值，这样做可能会导致内存泄漏，所以为了保护线程，我们向所有跨线程共享的数据结构添加锁，但有时通过添加锁，存在多个锁，这导致另一个问题，即死锁。为了避免内存泄露和死锁问题，我们在解释器上使用了单锁，即全局解释器锁(GIL)。

**为什么选择 GIL 作为解决方案:**
Python 在后端支持 C 语言，Python 拥有的所有相关库大部分都是用 C 和 C++编写的。由于 GIL，Python 提供了一种更好的方法来处理线程安全的内存管理。全局解释器锁在 python 中很容易实现，因为它只需要为一个线程提供一个锁，以便在 python 中处理。GIL 易于实现，并且很容易添加到 Python 中。它提高了单线程程序的性能，因为只需要管理一个锁。

**对多线程 Python 程序的影响:**
当用户编写 Python 程序或任何计算机程序时，那些性能受 CPU 限制的程序和那些受 I/O 限制的程序是有区别的。中央处理器通过同时执行许多操作将程序推到极限，而输入/输出程序必须花时间等待输入/输出。例如
**代码 1:执行简单倒计时的 CPU 绑定程序**

```py
# Python program showing
# CPU bound program

import time
from threading import Thread

COUNT = 50000000

def countdown(n):
    while n>0:
        n -= 1

start = time.time()
countdown(COUNT)
end = time.time()

print('Time taken in seconds -', end - start)
```

**输出:**

```py
Time taken in seconds - 2.5236213207244873

```

**代码 2:两个线程并行运行**

```py
# Python program showing
# two threads running parallel

import time
from threading import Thread

COUNT = 50000000

def countdown(n):
    while n>0:
        n -= 1

t1 = Thread(target = countdown, args =(COUNT//2, ))
t2 = Thread(target = countdown, args =(COUNT//2, ))

start = time.time()
t1.start()
t2.start()
t1.join()
t2.join()
end = time.time()

print('Time taken in seconds -', end - start)
```

**输出:**

```py
Time taken in seconds - 2.183610439300537

```

如您所见，在上面的代码中，两个代码中的中央处理器绑定进程和多线程进程具有相同的性能，因为在中央处理器绑定程序中，因为 GIL 限制中央处理器只能与单线程一起工作。CPU 绑定线程和多线程的影响在 python 中会是一样的。

**为什么 GIL 还没拆:**

GIL 到目前为止还没有改进，因为 python 2 有 GIL 实现，如果我们在 python 3 中改变这一点，那么它将会给我们带来一个问题。因此，我们没有删除 GIL，而是改进了 GIL 的概念。目前没有删除 GIL 的原因之一是 python 在后端严重依赖于 C，C 扩展严重依赖于 GIL 的实现方法。虽然有更多的方法来解决 GIL 解决的问题，但大多数都难以实施，并且会降低系统的速度。

**如何应对 Python 的 GIL :**

大多数时候，我们使用多重处理来防止程序来自 GIL。在这个实现中，python 为每个要运行的进程提供了不同的解释器，因此在这种情况下，单个线程被提供给多处理中的每个进程。

```py
# Python program showing 
# multiprocessing

import multiprocessing 
import time

COUNT = 50000000

def countdown(n):
    while n>0:
        n -= 1

if __name__ == "__main__":
    # creating processes 
    start = time.time()
    p1 = multiprocessing.Process(target = countdown, args =(COUNT//2, ))
    p2 = multiprocessing.Process(target = countdown, args =(COUNT//2, ))

    # starting process 1 
    p1.start()
    # starting process 2 
    p2.start() 

    # wait until process 1 is finished 
    p1.join() 
    # wait until process 2 is finished 
    p2.join()
    end = time.time()
    print('Time taken in seconds -', end - start)
```

**输出:**

```py
Time taken in seconds - 2.5148496627807617

```

正如您所看到的，多线程系统和多处理系统花费的时间没有区别。这是因为多处理系统有自己要解决的问题。所以这不会解决问题，但是它提供了 GIL 允许 python 执行的解决方案。