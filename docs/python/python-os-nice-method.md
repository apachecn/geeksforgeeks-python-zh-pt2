# Python | os.nice()方法

> 原文:[https://www.geeksforgeeks.org/python-os-nice-method/](https://www.geeksforgeeks.org/python-os-nice-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

os 模块中的所有函数在文件名和路径无效或不可访问的情况下都会引发 **OSError** ，或者其他具有正确类型但不被操作系统接受的参数。

Python 中的`***os.nice()***`方法用于将进程的精确性增加指定的值。

*精确值*或*精确值*是一组指导方针，当一个进程想要获得 CPU 时间来执行它的工作时，供 CPU 遵循。工艺的*精度*在-20 到 19 之间(包括两者)。具有较低*精度*或*优良值*的进程被赋予较高的优先级和较多的 CPU 时间，而具有较高*优良值*的进程被赋予较低的优先级和较少的 CPU 时间。

**注意:** `***os.nice()***`方法只在 UNIX 平台上可用。任何用户都可以提高进程的精确性，但是只有超级用户才能降低进程的精确性。
超级用户是指拥有运行或执行操作系统中任何程序的所有权限的根用户或管理用户。

> ***语法:*** os.nice(值)
> 
> ***参数:***
> **值**:整数值。
> 工艺的新精度计算为**新精度=以前的精度+规定值**
> 
> ***返回类型:*** 该方法返回一个整数值，代表流程的新细节。

**Code #1:** Use of os.nice() method to increase the process’s niceness

```
# Python program to explain os.nice() method 

# importing os module 
import os

# Get the current nice value
# of the process
niceValue = os.nice(0)

# Print the current nice value 
# of the process
print("Current nice value of the process:", niceValue)

# Increase the niceness 
# of the process
value = 5
niceValue = os.nice(value)
print("\nNiceness of the process increased")

# Print the current nice value 
# of the process
print("\nCurrent nice value of the process:", niceValue)

# Increase the niceness 
# of the process
value = 10
niceValue = os.nice(value)
print("\nNiceness of the process increased")

# Print the current nice value 
# of the process
print("\nCurrent nice value of the process:", niceValue)

# Increase the niceness 
# of the process
value = 10
niceValue = os.nice(value)
print("\nNiceness of the process increased")

# Print the current nice value 
# of the process
print("\nCurrent nice value of the process:", niceValue)

# The maximum possible niceness of a process
# can be 19 so if niceness to be set exceeds
# the maximum limit then it will set to 
# the maximum possible niceness i.e 19 
```

**Output:**

```
Current nice value of the process: 0

Niceness of the process increased

Current nice value of the process: 5

Niceness of the process increased

Current nice value of the process: 15

Niceness of the process increased

Current nice value of the process: 19

```

**Code #2:** Use of os.nice() method to decrease the process’s niceness

```
# Python program to explain os.nice() method 

# importing os module 
import os

# Note : Only a superuser can
# decrease a process's niceness
# so run the program as superuser
# to avoid permission related error

# Get the current nice value
# of the process
niceValue = os.nice(0)

# Print the Current nice value 
# of the process
print("Current nice value of the process:", niceValue)

# Decrease the niceness 
# of the process
value = -5
niceValue = os.nice(value)
print("\nNiceness of the process decreased")

# Print the current nice value 
# of the process
print("\nCurrent nice value of the process:", niceValue)

# Decrease the niceness 
# of the current process
value = -10
niceValue = os.nice(value)
print("\nNiceness of the process decreased")

# Print the current nice value 
# of the process
print("\nCurrent nice value of the process:", niceValue)

# Decrease the niceness 
# of the current process
value = -15
niceValue = os.nice(value)
print("\nNiceness of the process decreased")

# Print the current nice value 
# of the process
print("\nCurrent nice value of the process:", niceValue)

# The minimum possible niceness of a process
# can be -20 so if niceness to be set is 
# lower than the minimum limit then
# it will set to the minimum possible
# niceness i.e -20
```

**Output:**

```
Current nice value of the process: 0

Niceness of the process decreased

Current nice value of the process: -5

Niceness of the process decreased

Current nice value of the process: -15

Niceness of the process decreased

Current nice value of the process: -20

```