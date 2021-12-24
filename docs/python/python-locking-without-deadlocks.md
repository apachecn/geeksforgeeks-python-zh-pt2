# Python |无死锁锁定

> 原文:[https://www . geesforgeks . org/python-无死锁锁定/](https://www.geeksforgeeks.org/python-locking-without-deadlocks/)

本文主要讨论如果给定一个多线程程序，如何一次获得多个锁，同时避免死锁。

**多线程程序–**由于不断尝试一次获取多个锁的线程，这些线程非常容易出现死锁。用一个例子来理解它——一个线程已经获取了一个锁，然后该块尝试第二个锁，那么在这种情况下，程序可能会冻结，因为该线程可能会阻止其他线程的进程。

**解决方案:**

*   订购规则的实施
*   以唯一的方式将每个锁分配给程序。
*   只允许以升序获取多个锁。

**代码#1:使用上下文管理器实现解决方案。**

## 蟒蛇 3

```py
# importing libraries
import threading
from contextlib import contextmanager

# threading to stored information
_local = threading.local()

@contextmanager
def acquire(*lock_state_state):

    # Object identifier to sort the lock
    lock_state_state = sorted(lock_state_state, key=lambda a: id(a))

    # checking the validity of previous locks
    acquired = getattr(_local, 'acquired', [])
    if acquired and max(id(lock_state) for
                        lock_state in acquired) >= id(lock_state_state[0]):
        raise RuntimeError('lock_state Order Violation')

    # Collecting all the lock state.
    acquired.extend(lock_state_state)
    _local.acquired = acquired

    try:
    for lock_state in lock_state_state:
        lock.acquire()
    yield
    finally:

        # locks are released in reverse order.
        for lock_state in reversed(lock_state_state):
            lock_state.release()
        del acquired[-len(lock_state_state):]
```

使用上下文管理器以正常方式获取锁，并且为了执行该任务，使用 acquire()函数，因为有多个锁，如下代码所示:

**代码#2 :**

## 蟒蛇 3

```py
# threads
import threading

# creating locks
lock_state_1 = threading.Lock()
lock_state_2 = threading.Lock()

# using acquire as there are more than one lock

def thread_1():
    while True:
        with acquire(lock_state_1, lock_state_2):
            print('Thread-1')

def thread_2():
    while True:
        with acquire(lock_state_2, lock_state_1):
            print('Thread-2')

t1 = threading.Thread(target=thread_1)

# daemon thread runs without blocking
# the main program from exiting
t1.daemon = True
t1.start()

t2 = threading.Thread(target=thread_2)
t2.daemon = True
t2.start()
```

*   即使在每个函数中以不同的顺序获得锁规范之后，程序也将永远运行而不会出现死锁。
*   根据对象标识符对锁进行排序起着重要的作用，因为锁在被排序后会以一致的方式获得，而不管用户如何提供它们来获得()。
*   如果多个线程被嵌套，如下面的代码所示，为了解决检测潜在死锁的微妙问题，使用线程本地存储。

**代码#3 :**

## 蟒蛇 3

```py
# threads
import threading

# creating locks
lock_state_1 = threading.Lock()
lock_state_2 = threading.Lock()

def thread_1():
    while True:
        with acquire(lock_state_1):
            with acquire(lock_state_2):
                print('Thread-1')

def thread_2():
    while True:
        with acquire(lock_state_2):
            with acquire(lock_state_1):
                print('Thread-2')

t1 = threading.Thread(target=thread_1)

# daemon thread runs without blocking
# the main program from exiting
t1.daemon = True
t1.start()

t2 = threading.Thread(target=thread_2)
t2.daemon = True
t2.start()
```

运行此版本的程序时，其中一个线程将崩溃，并出现异常，例如:

```py
Exception in thread Thread-1:
Traceback (most recent call last):
    File "/usr/HP/lib/python3.3/threading.py", line 639, in _bootstrap_inner
        self.run()
    File "/usr/HP/lib/python3.3/threading.py", line 596, in run
        self._target(*self._args, **self._kwargs)
    File "deadlock.py", line 49, in thread_1
        with acquire(y_lock):
    File "/usr/HP/lib/python3.3/contextlib.py", line 48, in __enter__
        return next(self.gen)
    File "deadlock.py", line 17, in acquire
        raise RuntimeError("Lock Order Violation")
RuntimeError: Lock Order Violation
```

每个线程都记得锁已经被获取，这就是为什么它一直显示这个错误。获取锁的排序约束也被强制执行，并且通过 acquire()方法检查先前获取的锁的列表。