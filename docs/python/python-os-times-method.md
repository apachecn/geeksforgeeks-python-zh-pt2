# Python | os.times()方法

> 原文:[https://www.geeksforgeeks.org/python-os-times-method/](https://www.geeksforgeeks.org/python-os-times-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

`***os.times()***`Python 中的方法用于获取当前全局进程次数。

> ***语法:*** os.times()
> 
> ***参数:*** 不需要参数。
> 
> ***返回类型:*** 该方法返回一个元组状的对象，该对象有五个命名属性，代表当前的全局进程时间。这五个属性如下:
> 
> *   **用户**:代表用户时间。
> *   **系统**:代表系统时间
> *   **children_user** :表示所有子进程的用户时间。
> *   **children_system** :表示所有子进程的系统时间。
> *   **经过的**:表示过去某个固定点以来经过的真实时间。
> 
> **注意**:在 Windows 上，只有用户和系统属性是已知的，其他属性的值为 0。

**代码:**使用 os.times()方法获取当前全局进程次数。

```
# Python program to explain os.times() method 

# importing os module 
import os

# Get the current global
# process times
# using os.times() method
curr_gp_times = os.times()

# Print the current global
# process times
print(curr_gp_times)
```

**Output:**

```
posix.times_result(user=0.03, system=0.01, children_user=0.0, children_system=0.0, elapsed=17370844.95)

```

**参考:**T2】https://docs.python.org/3/library/os.path.html