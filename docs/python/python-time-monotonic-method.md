# Python | time .单调()方法

> 原文:[https://www.geeksforgeeks.org/python-time-monotonic-method/](https://www.geeksforgeeks.org/python-time-monotonic-method/)

**Python time.monotonic()** 方法用于获取单调时钟的值。单调的时钟是不能倒退的时钟。由于单调时钟返回值的参考点未定义，因此只有连续调用结果之间的差异才有效。

### **Python time .单调()**方法语法:

> **语法:**时间.单调()
> 
> **参数:**不需要参数。
> 
> **返回类型:**该方法返回一个浮点值，该值以分数秒为单位表示单调时钟的值。

## **Python 时间单调()示例**

### **示例 1:** 使用**时间单调()**方法获取单调时钟的值

## 蟒蛇 3

```
# Python program to explain time.monotonic() method

# importing time module
import time

# Get the value of
# a monotonic clock using
# time.monotonic() method
value = time.monotonic()

# print the value of
# the monotonic clock
print("Value of the monotonic clock (in fractional seconds):", value)
```

**输出:**

```
Value of the monotonic clock (in fractional seconds): 216444.515
```

### **示例 2:** 使用**时间单调()**方法测量长时间运行过程中经过的时间

## 蟒蛇 3

```
# Python program to explain time.monotonic() method

# importing time module
import time

# Get the value of
# a monotonic clock at the
# beginning of the process
# using time.monotonic() method
start = time.monotonic()

# print the value of
# the monotonic clock
print("At the beginning of the process")
print("Value of the monotonic clock (in fractional seconds):", start)

i = 0
arr = [0] * 10
while i < 10:
    # Take input from the user
    arr[i] = int(input())
    i = i + 1

# Print the user input
print(arr)

# Get the value of
# monotonic clock
# using time.monotonic() method
end = time.monotonic()

# print the value of
# the monotonic clock
print("\nAt the end of the process")
print("Value of the monotonic clock (in fractional seconds):", end)
print("Time elapsed during the process:", end - start)
```

**输出:**

```
At the beginning of the process
Value of the monotonic clock (in fractional seconds): 216491.25
1
2
3
4
5
6
7
8
9
10
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

At the end of the process
Value of the monotonic clock (in fractional seconds): 216516.875
Time elapsed during the process: 25.625
```