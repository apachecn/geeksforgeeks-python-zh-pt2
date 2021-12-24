# python | OS . support _ bytes _ about object

> 原文:[https://www . geesforgeks . org/python-OS-supports _ bytes _ environ-object-2/](https://www.geeksforgeeks.org/python-os-supports_bytes_environ-object-2/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。
***Python 中的 os . supports _ bytes _ environ***对象用于检查环境的原生 OS 类型是否为字节。
某些方法和对象的功能，如 ***os.getenvb()*** 和***OS . envirob***在 Python 中只有在***OS . supports _ bytes _ environ***的值为 True 时才可用。
**例如:***Windows*上环境的原生 OS 类型不是字节。所以***OS . supports _ bytes _ environ***为 False，因此 ***os.getenvb()*** 和*T34】OS . environ b*在 Windows 上不可用。

> ***语法:***OS . supports _ bytes _ environ
> ***参数:*** 这是一个不可调用的对象。因此，不需要参数
> ***返回类型:*** 该方法返回 bool 类的布尔值。如果环境的本机操作系统类型为字节，则此方法返回真，否则返回假。

**代码:**使用操作系统支持 _ 字节 _ 环境对象

## 蟒蛇 3

```
# Python program to explain os.supports_bytes_environ object

# importing os module
import os

# Check whether the native OS
# type of the environment is
# bytes or not
isBytes = os.supports_bytes_environ

# Print the result
print(isBytes)
```

**Output:** 

```
True
```