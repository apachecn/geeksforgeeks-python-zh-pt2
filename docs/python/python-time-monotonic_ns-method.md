# Python | time .单调 _ns()方法

> 原文:[https://www . geesforgeks . org/python-time-monotonic _ ns-method/](https://www.geeksforgeeks.org/python-time-monotonic_ns-method/)

Python 中的时间模块提供了各种与时间相关的功能。该模块属于 Python 的标准实用程序模块。

Python 中**时间模块**的`***time.monotonic_ns()***`方法用于获取以纳秒为单位的单调时钟的值。这个方法类似于 [`***time.monotonic()***`](https://www.geeksforgeeks.org/python-time-monotonic-method/) 方法，以分数秒为单位返回单调时钟值。单调的时钟是不能倒退的时钟。

> **语法:** time .单调 _ns()
> 
> **参数:**不需要参数。
> 
> **返回类型:**该方法返回一个整数值，代表以纳秒为单位的单调时钟的值。

**代码#1:** 使用`***time.monotonic_ns()***`方法获取以纳秒为单位的单调时钟值

```
# Python program to explain time.monotonic_ns() method

# importing time module
import time

# Get the value of
# the monotonic clock in 
# fractional seconds using
# time.monotonic() method
value1 = time.monotonic()

# Get the value of
# the monotonic clock in 
# nanoseconds using
# time.monotonic_ns() method
value2 = time.monotonic_ns()

# print the value of 
# the monotonic clock (in fractional seconds)
print("Value of the monotonic clock (in fractional seconds):", value1)

# print the value of 
# the monotonic clock (in nanoseconds)
print("Value of the monotonic clock (in nanoseconds):", value2)
```

**Output:**

```
Value of the monotonic clock (in fractional seconds): 13486.679399824
Value of the monotonic clock (in nanoseconds): 13486679402777

```

**代码#2:** 使用`***time.monotonic_ns()***`方法测量长时间运行过程中经过的时间。

```
# Python program to explain time.monotonic_ns() method

# importing time module
import time

# Function to calculate factorial 
# of the given number
def factorial(n):
    f = 1
    for i in range(n, 1, -1):
        f = f * i

    return f 

# Get the value of the
# monotonic clock in nanoseconds at the 
# beginning of the process
# using time.monotonic_ns() method
start = time.monotonic_ns()

# print the value of 
# the monotonic clock in nanoseconds
print("At the beginning of the process")
print("Value of the monotonic clock (in nanoseconds):", start, "\n")

# Calculate factorial of all
# numbers form 0 to 9
i = 0
fact = [0] * 10;

while i < 10:
    fact[i] = factorial(i)
    i = i + 1

# Print the calculated factorial
for i in range(0, len(fact)):
    print("Factorial of % d:" % i, fact[i])

# Get the value of
# monotonic clock in nanoseconds
# using time.monotonic_ns() method
end = time.monotonic_ns()

# print the value of 
# the monotonic clock
print("\nAt the end of the process")
print("Value of the monotonic clock (in nanoseconds):", end)
print("Time elapsed during the process:", end - start)    
```

**Output:**

```
At the beginning of the process
Value of the monotonic clock (in nanoseconds): 14671301967243 

Factorial of 0: 1
Factorial of 1: 1
Factorial of 2: 2
Factorial of 3: 6
Factorial of 4: 24
Factorial of 5: 120
Factorial of 6: 720
Factorial of 7: 5040
Factorial of 8: 40320
Factorial of 9: 362880

At the end of the process
Value of the monotonic clock (in nanoseconds): 14671302231487
Time elapsed during the process: 264244

```

**参考:**[https://docs . python . org/3/library/time . html # time .单调 _ns](https://docs.python.org/3/library/time.html#time.monotonic_ns)