# Python | os。WSTOPSIG()方法

> 原文:[https://www.geeksforgeeks.org/python-os-wstopsig-method/](https://www.geeksforgeeks.org/python-os-wstopsig-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

`***os.WSTOPSIG()***`Python 中的方法用于获取导致进程停止的信号编号。该方法以`***os.wait()***`、`***os.system()***`或`***os.waitpid()***`方法返回的过程状态代码为参数，返回导致过程停止的信号编号。

> **语法:** os。WSTOPSIG(状态)
> 
> **参数:**
> **状态:**该参数取 os.system()、os.wait()或 os.waitpid()方法返回的进程状态码(整数值)。
> 
> **返回类型:**该方法返回一个整数值，代表导致进程停止的信号号。

**代码:**使用`***os.WSTOPSIG()***`方法

```
# Python program to explain os.WSTOPSIG() method 

# importing os and signal module  
import os, signal

# Create a child process
# using os.fork() method 
pid = os.fork()

# pid greater than 0
# indicates the parent process 
if pid :

    # send signal 'SIGSTOP'
    # to the child process
    # using os.kill() method
    # 'SIGSTOP' signal will
    # cause the process to stop
    os.kill(pid, signal.SIGSTOP) 

    # get the child's pid
    # and status code
    # using os.waitpid() method
    info = os.waitpid(pid, os.WSTOPPED)

    # os.waitpid() method
    # returns a tuple which
    # represents child's pid
    # and exit status code

    print("\nIn parent process")

    # Get the signal number due
    # to which child process stopped 
    # using os.WSTOPSIG() method
    stopSignal = os.WSTOPSIG(info[1]) 

    print("Child stopped due to signal no:", stopSignal)
    print("Signal name:", signal.Signals(stopSignal).name)

else :
    print("In child process")
    print("Process ID:", os.getpid())
    print("Hello ! Geeks")
    print("Exiting")
```

**Output:**

```
In Child process

In parent process
Child stopped due to signal no: 19
Signal name: SIGSTOP

```

**参考文献:**T2】https://docs.python.org/3/library/os.html#os.WSTOPSIG