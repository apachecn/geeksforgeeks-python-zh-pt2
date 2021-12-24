# Python | os.makedev()方法

> 原文:[https://www.geeksforgeeks.org/python-os-makedev-method/](https://www.geeksforgeeks.org/python-os-makedev-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.makedev()***`方法用于从给定的 *>主*和*次*设备号中合成一个原始设备号。

在 Unix 中，一切都是文件，有些是普通文件，有些是特殊文件。特殊文件可以在 */dev* 目录下找到。这些特殊文件称为设备文件。字符和块设备是最常见的设备文件类型。这些设备文件由内核表示为一对数字(主设备号和次设备号)。
主要设备号表示哪个驱动程序用于访问硬件。系统中的每个驱动程序都有一个唯一的主设备号，所有主设备号相同的设备文件都由同一个驱动程序控制。
驱动程序使用次要设备号来区分其控制的各种硬件。次要设备号告诉内核要访问的设备的特殊特征。
原始设备是一种特殊的逻辑设备，与字符设备文件相关联。它允许直接访问存储设备。

**注意:**此方法仅在 UNIX 平台上可用。

> ***语法:*** os.makedev(大调，小调)
> 
> ***参数:***
> **主**:代表设备主编号的整数值
> **次**:代表设备次编号的整数值
> 
> ***返回类型:*** 该方法返回一个代表原始设备号的整数值。

**Code:** Use of os.makedev() method to create a raw device number using major and minor device numbers

```py
# Python program to explain os.makedev() method  

# importing os module 
import os

# Device major number
major = 8

# Device minor
minor = 8

# Compose raw device number from
# the above minor and major device number
# using os.makedev() method
raw_device = os.makedev(major, minor)

# Print the raw device number
print("Composed raw device number(major = % d, minor = % d):"\
%(major, minor), raw_device)

# Device major number
major = 103

# Device minor
minor = 0

# Compose raw device number from
# the above minor and major device number
# using os.makedev() method
raw_device = os.makedev(major, minor)

# Print the raw device number
print("Composed raw device number(major = % d, minor = % d):"\
%(major, minor), raw_device)
```

**Output:**

```py
Composed raw device number(major = 8, minor = 8): 2056
Composed raw device number(major = 103, minor = 0): 26368

```