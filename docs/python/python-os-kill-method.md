# Python | os.kill()方法

> 原文:[https://www.geeksforgeeks.org/python-os-kill-method/](https://www.geeksforgeeks.org/python-os-kill-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。
***OS . kill()***Python 中的方法用于向具有指定进程 id 的进程发送指定信号。主机平台上可用的特定信号的常数在[信号模块](https://docs.python.org/3/library/signal.html#module-signal)中定义。

> **语法:** os.kill(pid，sig)
> **参数:**
> **pid:** 表示信号要发送到的进程 id 的整数值。
> **sig** 表示待发送信号模块中定义的主机平台上可用的信号号或信号常数的整数。
> **返回类型:**此方法不返回任何值。

**代码:**使用 ***os.kill()*** 方法

## 蟒蛇 3

```
# Python program to explain os.kill() method

# importing os and signal module 
import os, signal

# Create a child process
# using os.fork() method
pid = os.fork()

# pid greater than 0
# indicates the parent process
if pid :

    print("\nIn parent process")

    # send signal 'SIGSTOP'
    # to the child process
    # using os.kill() method
    # 'SIGSTOP' signal will
    # cause the process to stop
    os.kill(pid, signal.SIGSTOP)

    print("Signal sent, child stopped.")

    info = os.waitpid(pid, os.WSTOPPED)
    # waitpid() method returns a
    # tuple whose first attribute
    # represents child's pid
    # and second attribute
    # representing child's status indication 

    # os.WSTOPSIG() returns the signal number
    # which caused the process to stop
    stopSignal = os.WSTOPSIG(info[1])
    print("Child stopped due to signal no:", stopSignal)
    print("Signal name:", signal.Signals(stopSignal).name)

    # send signal 'SIGCONT'
    # to the child process
    # using os.kill() method
    # 'SIGCONT' signal will
    # cause the process to continue
    os.kill(pid, signal.SIGCONT)
    print("\nSignal sent, child continued.")

else :

    print("\nIn child process")
    print("Process ID:", os.getpid())
    print("Hello ! Geeks")
    print("Exiting")
```

**Output:** 

```
In child process

In parent process
Signal sent, child stopped.
Child stopped due to signal no: 19
Signal name: SIGSTOP

Signal sent, child continued.

Process ID: 5166
Hello! Geeks
Exiting
```

**参考文献:**T2https://docs.python.org/3/library/os.html#os.kill