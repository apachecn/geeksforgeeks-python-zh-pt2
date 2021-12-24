# Python | os.major()方法

> 原文:[https://www.geeksforgeeks.org/python-os-major-method/](https://www.geeksforgeeks.org/python-os-major-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.major()***`方法用于从指定的原始设备号中提取设备主号(通常是 [os.stat()](https://www.geeksforgeeks.org/python-os-stat-method/) 方法返回的‘OS . stat _ result’对象的 *st_dev* 或 *st_rdev* 属性的值)。。

在 Linux 中，一切都是文件，有些是普通文件，有些是特殊文件。特殊文件可以在 */dev* 目录下找到。这些特殊文件称为设备文件。字符和块设备是最常见的设备文件类型。Linux 内核将这些设备文件表示为一对数字(主设备号和次设备号)。
主要设备号表示哪个驱动程序用于访问硬件。系统中的每个驱动程序都有一个唯一的主设备号，所有主设备号相同的设备文件都由同一个驱动程序控制。
驱动程序使用次要设备号来区分其控制的各种硬件。次要设备号告诉内核要访问的设备的特殊特征。

> ***语法:*** os.major(设备)
> 
> ***参数:***
> **设备**:代表原始设备号的整数值
> 
> ***返回类型:*** 该方法返回一个代表设备主编号的整数值。

**Code:** Use of os.major() method to extract the device major number from a raw device number

```py
# Python program to explain os.major() method  

# importing os module 
import os

# Get the raw device number
# of a file
device = os.stat("file.txt").st_dev

# Print the raw device number
print("Raw device number:", device)

# Extract the device major number
# from the above raw device number
major = os.major(device)

# Print the device major number  
print("Device major number:", major)
```

**Output:**

```py
Raw device number: 2056
Device major number: 8

```

**参考:**T2】https://docs.python.org/3/library/os.html#os.major