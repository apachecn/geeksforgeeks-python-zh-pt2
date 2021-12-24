# Python time.thread_time()函数

> 原文:[https://www . geesforgeks . org/python-time-thread _ time-function/](https://www.geeksforgeeks.org/python-time-thread_time-function/)

计时器对象用于表示需要被安排在某个时刻之后运行的动作。这些对象被安排在执行操作的单独线程上运行。然而，定时器初始化的时间间隔可能不是解释器实际执行动作的实际时刻，因为实际调度对应于定时器对象的线程是线程调度器的责任。计时器是 python 中定义的线程类的子类。通过显式调用定时器对应的 start()函数来启动。它用于返回时间的秒数

> **语法**:
> 
> time.thread_time()
> 
> **返回**:
> 
> 秒

### **示例**:使用 thread_time()函数的 Python 程序

在本例中，我们将使用 python 编程语言获取 thread_time 来获取系统的当前时间。

## 蟒蛇 3

```py
# import time module
import time

# thread_time() demo
time.thread_time()
```

**输出:**

```py
3.394032268
```

### **示例 2:** 通过停止几秒钟并发执行的 Python 程序

因此，在本例中，我们将使用 time.sleep()方法在 thread_time()函数中间等待一段时间。首先，我们停止 10 秒，然后 2 秒，再 2 秒。

## 蟒蛇 3

```py
# import time module
import time

# thread_time() demo
print(time.thread_time())

# sleep for 10 seconds
time.sleep(10)

# thread_time() demo
print(time.thread_time())

# sleep for 2 seconds
time.sleep(2)

# thread_time() demo
print(time.thread_time())
# sleep for 2 seconds
time.sleep(2)

# thread_time() demo
print(time.thread_time())
```

**输出:**

```py
3.53465852
3.535156974
3.535567409
3.535961336
```