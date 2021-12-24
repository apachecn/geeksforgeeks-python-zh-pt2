# Python | time.clock()方法

> 原文:[https://www.geeksforgeeks.org/python-time-clock-method/](https://www.geeksforgeeks.org/python-time-clock-method/)

**Python 中的时间模块**提供了各种与时间相关的功能。

Python 中**时间模块**的`***time.clock()***`方法用于获取当前处理器时间，以秒为单位的浮点数。
作为，时间模块中定义的大部分函数都调用相应的 C 库函数。`***time.clock()***`方法也调用同名的 C 库函数得到结果。返回的浮点值的精度取决于被调用的 C 库函数。

**注意:**这个方法从 Python 3.3 版本开始就被弃用了，在 Python 3.8 版本中将被移除。这种方法的行为依赖于平台。

> **语法:** time.clock()
> 
> **参数:**不需要参数。
> 
> **返回类型:**该方法返回一个浮点值，代表当前处理器时间(以秒为单位)。

**代码#1:** 使用`***time.clock()***`方法获取当前处理器时间

```py
# Python program to explain time.clock() method

# importing time module
import time

# Get the current processor
# time in seconds
pro_time = time.clock()

# print the current 
# processor time
print("Current processor time (in seconds):", pro_time)
```

**Output:**

```py
Current processor time (in seconds): 0.042379

```

**代码#2:** 使用`***time.clock()***`方法获取当前处理器时间

```py
# Python program to explain time.clock() method 

# importing time module 
import time 

# Function to calculate factorial 
# of the given number 
def factorial(n): 
    f = 1
    for i in range(n, 1, -1): 
        f = f * i 

    return f 

# Get the current processor time
# in seconds at the 
# beginning of the calculation 
# using time.clock() method 
start = time.clock() 

# print the processor time in seconds 
print("At the beginning of the calculation") 
print("Processor time (in seconds):", start, "\n") 

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

# Get the processor time
# in seconds at the end 
# of the calculation 
# using time.clock() method 
end = time.clock() 

print("\nAt the end of the calculation") 
print("Processor time (in seconds):", end) 
print("Time elapsed during the calculation:", end - start)     
```

**Output:**

```py
At the beginning of the calculation
Processor time (in seconds): 0.03451 

Factorial of  0: 1
Factorial of  1: 1
Factorial of  2: 2
Factorial of  3: 6
Factorial of  4: 24
Factorial of  5: 120
Factorial of  6: 720
Factorial of  7: 5040
Factorial of  8: 40320
Factorial of  9: 362880

At the end of the calculation
Processor time (in seconds): 0.034715
Time elapsed during the calculation: 0.0002050000000000038

```

**参考:**T2】https://docs.python.org/3/library/time.html#time.clock