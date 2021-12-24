# Python | OS . confstr _ name 对象

> 原文:[https://www . geesforgeks . org/python-OS-confstr _ names-object/](https://www.geeksforgeeks.org/python-os-confstr_names-object/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。
***OS . confstr _ names***Python 中的对象是由 ***os.confstr()*** 方法接受为参数的名称到主机操作系统为这些名称定义的整数值的字典映射。该对象用于确定系统已知的一组名称。
**注意:*****OS . confstr _ name***对象仅在 UNIX 平台上可用。

> ***语法:***OS . confstr _ name
> ***参数:*** 这是一个不可调用的对象。因此，不需要任何参数。
> ***返回类型:*** 该对象返回一个字典，该字典将操作系统已知的一组名称作为键，将它们对应的整数值(由操作系统定义)作为值。

**代码:**使用 os.confstr _ names 对象

## 蟒蛇 3

```py
# Python program to explain os.confstr_names

# importing os module
import os

# importing pprint module
import pprint

# Get the dictionary mapping of
# names accepted by os.confstr() method
# to their corresponding integer values
# defined by host OS
names = os.confstr_names

# print the dictionary mapping
# using pprint
print("The list of names known to the operating system:")
pprint.pprint(names, width = 1)
```

**Output:** 

```py
The list of names known to the operating system:
{'CS_GNU_LIBC_VERSION': 2,
 'CS_GNU_LIBPTHREAD_VERSION': 3,
 'CS_LFS64_CFLAGS': 1004,
 'CS_LFS64_LDFLAGS': 1005,
 'CS_LFS64_LIBS': 1006,
 'CS_LFS64_LINTFLAGS': 1007,
 'CS_LFS_CFLAGS': 1000,
 'CS_LFS_LDFLAGS': 1001,
 'CS_LFS_LIBS': 1002,
 'CS_LFS_LINTFLAGS': 1003,
 'CS_PATH': 0,
 'CS_XBS5_ILP32_OFF32_CFLAGS': 1100,
 'CS_XBS5_ILP32_OFF32_LDFLAGS': 1101,
 'CS_XBS5_ILP32_OFF32_LIBS': 1102,
 'CS_XBS5_ILP32_OFF32_LINTFLAGS': 1103,
 'CS_XBS5_ILP32_OFFBIG_CFLAGS': 1104,
 'CS_XBS5_ILP32_OFFBIG_LDFLAGS': 1105,
 'CS_XBS5_ILP32_OFFBIG_LIBS': 1106,
 'CS_XBS5_ILP32_OFFBIG_LINTFLAGS': 1107,
 'CS_XBS5_LP64_OFF64_CFLAGS': 1108,
 'CS_XBS5_LP64_OFF64_LDFLAGS': 1109,
 'CS_XBS5_LP64_OFF64_LIBS': 1110,
 'CS_XBS5_LP64_OFF64_LINTFLAGS': 1111,
 'CS_XBS5_LPBIG_OFFBIG_CFLAGS': 1112,
 'CS_XBS5_LPBIG_OFFBIG_LDFLAGS': 1113,
 'CS_XBS5_LPBIG_OFFBIG_LIBS': 1114,
 'CS_XBS5_LPBIG_OFFBIG_LINTFLAGS': 1115}
```