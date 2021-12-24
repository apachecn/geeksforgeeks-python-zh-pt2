# Python | os.pipe()方法

> 原文:[https://www.geeksforgeeks.org/python-os-pipe-method/](https://www.geeksforgeeks.org/python-os-pipe-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

在文件名和路径无效或不可访问的情况下，或者在其他具有正确类型但不被操作系统接受的参数的情况下，操作系统模块中的所有函数都会引发 **OSError** 。

Python 中的`***os.pipe()***`方法用于创建管道。管道是将信息从一个进程传递到另一个进程的方法。它只提供单向通信，传递的信息由系统保存，直到被接收进程读取。

> ***语法:*** os.pipe()
> 
> ***参数:*** 不需要参数
> 
> ***返回类型:*** 这个方法分别返回一对可读写的文件描述符(r，w)。

**Code:** Use of os.pipe() method

```
# Python program to explain os.pipe() method 

# importing os module 
import os

# Create a pipe
r, w = os.pipe()

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

    # This is the parent process 
    # Closes file descriptor w
    os.close(w)

    # Read the text written by parent process
    print("\nChild Process is reading")
    r = os.fdopen(r)
    print("Read text:", r.read())
```

**Output:**

```
Parent process is writing
Text written: Hello child process

Child Process is reading
Text read: Hello child process

```