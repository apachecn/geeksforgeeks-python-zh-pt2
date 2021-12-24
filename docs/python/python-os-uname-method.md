# Python | os.uname()方法

> 原文:[https://www.geeksforgeeks.org/python-os-uname-method/](https://www.geeksforgeeks.org/python-os-uname-method/)

***OS . uname()**python 中的*方法用于获取当前操作系统的信息。该方法以元组状对象的属性形式返回当前操作系统的名称、版本和版本、网络上机器的名称和硬件标识符等信息。

> ***语法:*** os.uname()
> 
> ***参数:*** 不需要
> 
> ***返回类型:*** 这个方法返回一个元组样的对象，它有五个属性:
> 
> *   **系统名**–操作系统名
> *   **节点名**–网络上机器的名称(实现定义)
> *   **发布**–操作系统发布
> *   **版本**–操作系统版本
> *   **机器**–硬件标识符

**代码#1:** 使用 os.uname()方法

```py
# Python program to explain os.uname() method 

# importing os module 
import os

# Get the information of current
# operating system
os_info = os.uname()

# print the information
print(os_info) 
```

**Output:**

```py
posix.uname_result(sysname='Linux', nodename='pppContainer', release='4.4.0-1075-aws', 
version='#85-Ubuntu SMP Thu Jan 17 17:15:12 UTC 2019', machine='x86_64')

```