# Python | os。WIFCONTINUED()方法

> 原文:[https://www . geesforgeks . org/python-OS-wifi continued-method/](https://www.geeksforgeeks.org/python-os-wifcontinued-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

`***os.WIFCONTINUED()***`Python 中的方法用于检查一个进程是否从作业控制停止继续。该方法以`***os.wait()***`、`***os.system()***`或`***os.waitpid()***`方法返回的过程状态代码为参数，如果过程已经停止，则返回真，否则返回假。

> **语法:** os。无线继续(状态)
> 
> **参数:**
> **状态:**该参数取 os.system()、os.wait()或 os.waitpid()方法返回的进程状态码(整数值)。
> 
> **返回类型:**这个方法返回一个布尔值类“bool”。如果进程从作业控制停止继续，此方法返回真，否则返回假。

**代码:**使用`***os.WIFCONTINUED()***`方法

```
# Python program to explain os.WIFCONTINUED() method 

# importing os and signal module  
import os, signal

# Create a child process
# using os.fork() method 
pid = os.fork()

# pid greater than 0
# indicates the parent process 
if pid :

    # Send signal 'SIGSTOP'
    # to child process
    # using os.kill() method
    # signal 'SIGCONT' will cause
    # the child process to stop
    os.kill(pid, signal.SIGSTOP)

    # Send signal 'SIGCONT'
    # to child process
    # using os.kill() method
    # SIGCONT signal will cause
    # the child process to continue
    os.kill(pid, signal.SIGCONT)

    # Get the child's pid and 
    # status code using
    # os.waitpid() method
    info = os.waitpid(pid, os.WCONTINUED)

    # info is a tuple
    # info[0] represents child's pid
    # info[1] represents exit status code

    print("\nIn parent process")

    # Check whether the child process
    # has been continued 
    # from a job control stop or not    
    # using os.WIFCONTINUED() method
    continued = os.WIFCONTINUED(info[1]) 

    print("Has child process been continued from a job control stop?")
    print(continued)

else :

    print("In Child process")
    print("Process ID:", os.getpid())
    print("Hello ! Geeks")

```

**Output:**

```
In Child process
Process ID: 12371
Hello! Geeks

In parent process
Has child process been continued from a job control stop?
True

```

**参考文献:**T2】https://docs.python.org/3/library/os.html#os.WIFCONTINUED