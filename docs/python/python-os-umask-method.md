# Python | os.umask()方法

> 原文:[https://www.geeksforgeeks.org/python-os-umask-method/](https://www.geeksforgeeks.org/python-os-umask-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.umask()***`方法用于设置当前数值 *umask* 值并获取之前的 *umask* 值。

***umask*** 代表*用户文件创建模式掩码*。这用于确定新创建的文件或目录的文件权限。

> ***语法:*** os.umask(掩码)
> 
> ***参数:***
> **掩码**:表示有效 umask 值的整数值。
> 
> ***返回类型:*** 该方法设置当前的 umask 值，返回一个代表前一个 umask 值的整数值。

**代码#1:** 使用 os.umask()方法

```
# Python program to explain os.umask() method 

# importing os module 
import os

# mask
# 18 in decimal is
# equal to 0o022 in octal
mask = 18

# Set the current umask value
# and get the previous
# umask value
umask = os.umask(mask)

# Print the 
# current and previous 
# umask value
print("Current umask:", mask)
print("Previous umask:", umask) 
```

**Output:**

```
Current umask: 18
Previous umask: 54

```

**代码#2:** 在 os.umask()方法中将八进制值作为参数传递

```
# Python program to explain os.umask() method 

# importing os module 
import os

# Octal value for umask
# octal value 0o777 is 
# 511 in decimal
mask = 0o777

# Set the current umask value
# and get the previous
# umask value
umask = os.umask(mask)

# Print the 
# current and previous 
# umask value
print("Current umask:", mask)
print("Previous umask:", umask) 
```

**Output:**

```
Current umask: 511
Previous umask: 18

```