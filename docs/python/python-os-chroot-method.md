# Python–OS . chroot()方法

> 原文:[https://www.geeksforgeeks.org/python-os-chroot-method/](https://www.geeksforgeeks.org/python-os-chroot-method/)

**`os.chroot()`** 方法在 Python 中用于将当前进程的根目录改为路径。

> **语法:** os.chroot(路径)
> 
> **参数:**
> **路径:**路径要设置为当前进程的根。
> 
> **返回:**不返回任何值。

**代码#1:**

```py
# Python program to explain os.chroot() ethod

import os, sys

# Set current root path to /Geeks/gfg
os.chroot("/Geeks/gfg")
print ("root path successfully changed.")
```

输出:

```py
root path successfully changed.
```

**代码#2:**

```py
# Function to Change root directory of the process.
def change_root_directory(path):

    try:
        os.chdir(path)
        os.chroot(path)
    except Exception as exc:
        error = DaemonOSEnvironmentError("Unable to change root directory ({exc})".format(exc = exc))
        raise error 

# main function
change_root_directory("/Geeks/gfg")
```