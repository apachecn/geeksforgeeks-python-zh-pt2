# Python | os.wait()方法

> 原文:[https://www.geeksforgeeks.org/python-os-wait-method/](https://www.geeksforgeeks.org/python-os-wait-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.wait()***`方法被一个进程用来等待一个子进程的完成。
该方法返回一个包含其 PID 和退出状态指示的元组。子进程的退出状态由一个 16 位数字表示，其低位字节是终止进程的信号号，高位字节是退出状态(如果信号号为零)。

> **语法:** os.wait()
> 
> **参数:**不需要参数。
> 
> **返回类型:**该方法返回一个包含终止子进程的进程号和退出状态指示的元组。

**代码:**使用`***os.wait()***`方法

```py
# Python program to explain os.wait() method 

# importing os module  
import os 

# Create a child process
# using os.fork() method 
pid = os.fork()

# a Non-zero process id (pid)
# indicates the parent process 
if pid :

    # Wait for the completion of
    # child process using
    # os.wait() method    
    status = os.wait()
    print("\nIn parent process-")
    print("Terminated child's process id:", status[0])
    print("Signal number that killed the child process:", status[1])

else :
    print("In Child process-")
    print("Process ID:", os.getpid())
    print("Hello ! Geeks")
    print("Exiting")

# using os.wait() method    
# Parent process will wait till 
# the completion of child process
# and then only it will 
# begin its execution
```

**Output:**

```py
In Child process-
Process ID: 6276
Hello! Geeks
Exiting

In parent process-
Terminated child's process id: 6276
Signal number that killed the child process: 0

```