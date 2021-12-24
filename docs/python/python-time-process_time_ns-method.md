# Python | time.process_time_ns()方法

> 原文:[https://www . geesforgeks . org/python-time-process _ time _ ns-method/](https://www.geeksforgeeks.org/python-time-process_time_ns-method/)

Python 中的时间模块提供了各种与时间相关的功能。该模块属于 Python 的标准实用程序模块。

使用 Python 中**时间模块**的`***time.process_time_ns()***`方法得到当前进程的系统和用户 CPU 时间之和，单位为纳秒。此方法不包括睡眠期间经过的时间。这个方法类似于 [`***time.process_time()***`](https://www.geeksforgeeks.org/time-process_time-function-in-python/) 方法，返回当前进程的系统和用户 CPU 时间之和，以分数秒为单位。

由于单调时钟返回值的参考点未定义，因此只有连续调用结果之间的差异才有效。

> **语法:** time.process_time_ns()
> 
> **参数:**不需要参数。
> 
> **返回类型:**该方法返回一个整数值，代表当前进程的系统和用户 CPU 时间之和，单位为纳秒。

**代码#1:** 使用`***time.process_time_ns()***`方法

```py
# Python program to explain time.process_time_ns() method

# importing time module
import time

# assigning n = 100  
n = 100 

# Get the sum of the system 
# and user CPU time of
# the current process in nanoseconds
# using time.process_time_ns() method
start = time.process_time_ns()  

print("At the beginning of the process")
print("Process Time (in nanoseconds):", start, "\n")
# Here process time means sum of the system
# and user CPU time of the current process

# Print all natural numbers
# from 1 to 100

for i in range(1, n + 1): 
    print(i, end =' ') 

print()  

end = time.process_time_ns() 

print("\nAt the end of the process")
print("Process time (in nanoseconds):", end)     
print("Elapsed time during the process (in nanoseconds):", end - start)  
```

**输出:**

```py
At the beginning of the process
Process Time (in nanoseconds): 31873819

1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20
21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40
41 42 43 44 45 46 47 48 49 50 51 52 53 54 55 56 57 58 59 60
61 62 63 64 65 66 67 68 69 70 71 72 73 74 75 76 77 78 79 80
81 82 83 84 85 86 87 88 89 90 91 92 93 94 95 96 97 98 99 100 

At the end of the process
Process time (in nanoseconds): 32271699
Elapsed time during the whole process (in nanoseconds): 397880

```

**代码#2:** 显示`***time.process_time_ns()***`方法不包括睡眠期间经过的时间

```py
# Python program to explain time.process_time_ns() method

# importing time module
import time

# Get the sum of the system 
# and user CPU time of
# the current process in nanoseconds
# using time.process_time_ns() method
start = time.process_time_ns()  

print("At the beginning of first example")
print("Process Time (in nanoseconds):", start, "\n")
# Here process time means sum of the system
# and user CPU time of the current process

# Print all natural numbers
# from 1 to 50

# assigning n = 50  
n = 50

for i in range(1, n + 1): 
    print(i, end =' ') 

print()  

end = time.process_time_ns()

print("\nAt the end of the first example")
print("Process time (in nanoseconds):", end)    
print("Elapsed time during the first example (in nanoseconds):", end-start) 

# Get the sum of the system 
# and user CPU time of
# the current process in nanoseconds
# using time.process_time_ns() method
start = time.process_time_ns()  

print("\nAt the beginning of second example")
print("Process Time (in nanoseconds):", start, "\n")
# Here process time means sum of the system
# and user CPU time of the current process

# Print all natural numbers
# from 1 to 50

# assigning n = 100  
n = 50

for i in range(1, n + 1): 
    print(i, end =' ') 

print()  

# suspend the execution of the current
# process for 10 seconds
time.sleep(10)

end = time.process_time_ns()
print("\nAt the end of the second example")
print("Process time (in nanoseconds):", end)    
print("Elapsed time during the second example (in nanoseconds):", end-start) 

# In both the examples 
# we can see (in the output below)
# that elapsed time 
# is more or less the same 
# so, the suspension of process for
# 10 seconds is not included
```

**输出:**

```py
At the beginning of first example
Process Time (in nanoseconds): 26901160

1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20
21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40
41 42 43 44 45 46 47 48 49 50 

At the end of the first example
Process time (in nanoseconds): 27091390
Elapsed time during the first example (in nanoseconds): 190230

At the beginning of second example
Process Time (in nanoseconds): 27186972

1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20
21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40
41 42 43 44 45 46 47 48 49 50 

At the end of the second example
Process time (in nanoseconds): 27377123
Elapsed time during the second example (in nanoseconds): 190151

```

**参考:**[https://docs . python . org/3/library/time . html # time . process _ time _ ns](https://docs.python.org/3/library/time.html#time.process_time_ns)