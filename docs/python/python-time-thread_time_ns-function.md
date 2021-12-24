# Python time.thread_time_ns()函数

> 原文:[https://www . geesforgeks . org/python-time-thread _ time _ ns-function/](https://www.geeksforgeeks.org/python-time-thread_time_ns-function/)

**Python time.thread_time_ns()函数**用于返回当前线程的系统和用户 CPU 时间之和的值。它类似于 time.thread_time()函数。不同的是 thread_time()函数返回的是 CPU 的秒数(计算机时间)，而 thread_time_ns()函数返回的是 CPU 的纳秒数(计算机时间)

**语法:**

```
time.thread_time_ns()
```

**返回:**

计算机时间的纳秒

**示例 1:** 使用 thread_time_ns()函数的 Python 程序

## 蟒蛇 3

```
# import time module
import time

# thread_time_ns() demo
print(time.thread_time_ns())
```

**输出**:

```
3633875824
```

**示例 2** : Python 程序，通过休眠几秒钟来演示 thread_time_ns()函数

## 蟒蛇 3

```
# import time module
import time

# thread_time_ns() demo
print(time.thread_time_ns())

# sleep for 10 seconds
time.sleep(10)

# thread_time_ns() demo
print(time.thread_time_ns())

# sleep for 2 seconds
time.sleep(2)

# thread_time_ns() demo
print(time.thread_time_ns())
# sleep for 2 seconds
time.sleep(2)

# thread_time_ns() demo
print(time.thread_time_ns())
```

**输出:**

```
3616352715
3616782418
3617173584
3617551725
```