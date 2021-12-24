# Python | os.getpgrp()方法

> 原文:[https://www.geeksforgeeks.org/python-os-getpgrp-method/](https://www.geeksforgeeks.org/python-os-getpgrp-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

os 模块中的所有函数在文件名和路径无效或不可访问的情况下都会引发 **OSError** ，或者其他具有正确类型但不被操作系统接受的参数。

在类似 UNIX 的操作系统中，进程组表示一个或多个进程的集合。它用于控制信号的分配，即当一个信号指向一个过程组时，该过程组的每个成员都接收该信号。每个流程组都使用流程组 id 进行唯一标识。Python 中的
`***os.getpgrp()***`方法用于获取当前进程组 id。

**注意:** `***os.getsid()***`方法只在 UNIX 平台上可用。

> ***语法:*** os.getpgrp()
> 
> ***参数:*** 不需要参数
> 
> ***返回类型:*** 该方法返回一个整数值，表示当前进程的进程组标识。

**Code:** Use of os.getpgrp() method

```py
# Python program to explain os.getpgrp() method 

# importing os module 
import os

# Get the process group id
# of the current process
# using os.getpgrp() method
id = os.getpgrp()

# Print the process group id
# of the current process
print("Process group id of the current process:", id)
```

**输出:**
![os.getpgrp() method output](img/0f5384e4d133137ae3e1db610d900a6d.png)