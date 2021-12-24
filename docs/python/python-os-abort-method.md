# Python | os.abort()方法

> 原文:[https://www.geeksforgeeks.org/python-os-abort-method/](https://www.geeksforgeeks.org/python-os-abort-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.abort()***`方法用于向当前进程生成一个 *SIGABRT* 信号。在 Unix 上，这个方法产生一个核心转储，而在 Windows 上，这个过程会立即返回一个退出代码 3。
该方法不调用为 *SIGABRT* 信号注册的 Python 信号处理程序，而是使用 [signal.signal()。](https://docs.python.org/3/library/signal.html#signal.signal)

> **语法:** os.abort()
> 
> **参数:**不需要参数。
> 
> **返回类型:**该方法在调用过程中不返回值。

**代码#1:** 使用`***os.abort()***`方法

```
# Python program to explain os.abort() method 

# importing os module  
import os

print("Hello ! Geeks")

# os.abort() method
# will generate 'SIGABRT'
# signal to the current process
# On Unix, a core dump
# will be produced
# On windows, process
# will exit with exit code 3
os.abort()

# As process is aborted
# the line after os.abort() statement
# will not be executed.
print("This will not be printed")
```

**Output:**

```
Hello! Geeks
Aborted (core dumped)

```

**代码#2:** 使用`***os.abort()***`方法

```
# Python program to explain os.abort() method 

# importing os module  
import os, signal

# Create a child process
# using os.fork() method 
pid = os.fork()

# pid greater than 0
# indicates the parent process 
if pid > 0:
    # Parent process    
    print("\nIn Parent process")

    # Wait for the completion 
    # of child process and get 
    # its pid and exit status indication
    # using os.wait() method 
    info = os.wait()

    sig = os.WTERMSIG(info[1]) 
    print("Child exited due to signal no:", sig)
    print("Signal name:", signal.Signals(sig).name)

else :

    # child process
    print("In child process")
    print("Process ID:", os.getpid())
    print("Hello ! Geeks")

    # Abort the child process
    # by generating SIGABRT signal
    # using os.abort() method
    os.abort()
```

**Output:**

```
In child process
Process ID: 13914
Hello! Geeks

In Parent process
Child stopped due to signal no: 6
Signal name: SIGABRT

```

**参考文献:**T2】https://docs.python.org/3/library/os.html#os.abort