# Python | os.chmod 方法

> 原文:[https://www.geeksforgeeks.org/python-os-chmod-method/](https://www.geeksforgeeks.org/python-os-chmod-method/)

**`os.chmod()`** 方法在 Python 中是用来将路径的模式改为数值模式的。

**语法:**

```py
os.chmod(path, mode)
```

> **参数:**
> 路径–文件或目录路径的路径名
> 模式–*模式*可以采用以下值之一:
> 
> *   **stat。S_ISUID :** 执行时设置用户标识
> *   **stat。S_ISGID :** 执行时设置组标识
> *   **stat。S_ENFMT :** 强制执行记录锁定
> *   **stat。S_ISVTX :** 执行后保存文字图像
> *   **stat。S_IREAD :** 由所有者读取。
> *   **stat。S_IWRITE :** 由所有者编写。
> *   **stat。S_IEXEC :** 由所有者执行。
> *   **stat。S_IRWXU :** 由所有者读取、写入和执行
> *   **stat。S_IRUSR :** 由所有者读取
> *   **stat。S_IWUSR :** 由所有者编写。
> *   **stat。S_IXUSR :** 由所有者执行。
> *   **stat。S_IRWXG :** 按组读取、写入和执行
> *   **stat。S_IRGRP :** 分组阅读
> *   **stat。S_IWGRP :** 按组写入
> *   **stat。S_IXGRP :** 按组执行
> *   **stat。S_IRWXO :** 由他人读取、写入和执行。
> *   **stat。S_IROTH :** 其他人阅读
> *   **stat。S_IWOTH :** 他人代写
> *   **stat。S_IXOTH :** 由他人执行

**代码#1:**

```py
# Python program to explain os.chmod() method

# importing necessary libraries
import os, sys, stat

# Set given file read by the owner.
os.chmod("/Geeks/gfg.txt", stat.S_IREAD)
print("File can be read only by owner.")

# Set given file read by others.
os.chmod("/Geeks/gfg.txt", stat.S_IROTH)
print("File access changed, can be read by others now.")
```

**输出:**

```py
File can be read only by owner.
File access changed, can be read by others now.

```

**代码#2:**

```py
# Python program to explain os.chmod() method

# importing necessary libraries
import os, sys, stat

# Set given file written by the owner.
os.chmod("/Geeks/gfg.txt", stat.S_IWRITE)

# Set given file executed by the owner.
os.chmod("/Geeks/gfg.txt", stat.S_IXUSR)
print("File can be written and executed only by owner.")
```

**输出:**

```py
File can be written and executed only by owner.
```