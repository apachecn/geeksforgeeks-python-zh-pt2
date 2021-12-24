# Python | os.pipe2()方法

> 原文:[https://www.geeksforgeeks.org/python-os-pipe2-method/](https://www.geeksforgeeks.org/python-os-pipe2-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

管道是将信息从一个进程传递到另一个进程的方法。它只提供单向通信，传递的信息由系统保存，直到被接收进程读取。Python 中的
`***os.pipe2()***`方法用于创建一个自动设置标志的管道。

> ***语法:*** os.pipe2(旗帜)
> 
> ***参数:***
> **标志:**标志参数由一个或多个操作系统一起或构成。O _ NONBLOCK 和 os。O_CLOEXEC 值。
> 
> ***返回类型:*** 这个方法分别返回一对可读写的文件描述符(r，w)。

**Code:** Use of os.pipe2() method to create a pipe with flags set automatically

```py
# Python program to explain os.pipe2() method 

# importing os module 
import os

# Create a pipe with
# flag set automatically
# os.O_NONBLOCK flag tells 
# that file descriptor 
# is in non-blocking mode
flags = os.O_NONBLOCK
r, w = os.pipe2(flags)

# The returned file descriptor r and w
# can be used for reading and
# writing respectively.

# We will create a child process
# and using these file descriptor
# the parent process will write 
# some text and child process will
# read the text written by the parent process

# Create a child process
pid = os.fork()

# pid greater than 0 represents
# the parent process
if pid > 0:

    # This is the parent process 
    # Closes file descriptor r
    os.close(r)

    # Write some text to file descriptor w 
    print("Parent process is writing")
    text = b"Hello child process"
    os.write(w, text)
    print("Written text:", text.decode())

else:

    # This is the child process 
    # Closes file descriptor w
    os.close(w)

    # Read the text written by parent process
    print("\nChild Process is reading")
    r = os.fdopen(r)
    print("Read text:", r.read())
```

**Output:**

```py
Parent process is writing
Text written: Hello child process

Child Process is reading
Text read: Hello child process

```

**参考:**T2】https://docs.python.org/3/library/os.html#os.pipe2