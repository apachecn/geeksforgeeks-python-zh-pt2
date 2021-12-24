# Python | os。WIFSIGNALED()方法

> 原文:[https://www.geeksforgeeks.org/python-os-wifsignaled-method/](https://www.geeksforgeeks.org/python-os-wifsignaled-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

***os。Python 中的 wifi signed()***方法用于检查进程是否因任何信号而退出。该方法将*T5【OS . wait()】*、 ***os.system()*** 或 ***os.waitpid()*** 方法返回的进程状态代码作为参数，如果进程因信号退出则返回 True，否则返回 False。

> **语法:** os。WIFSIGNALED(状态)
> **参数:**
> **状态:**该参数取 os.system()、os.wait()或 os.waitpid()方法返回的进程状态码(整数值)。
> **返回类型:**该方法返回类“bool”的布尔值。如果进程因信号退出，此方法返回真，否则返回假。

**代码#1:** 使用 ***os。**方法*

## 蟒蛇 3

```
# Python program to explain os.WIFSIGNALED() method

# importing os module 
import os

# Create a child process
# using os.fork() method
pid = os.fork()

# pid greater than 0
# indicates the parent process
if pid :

    # Wait for the completion of
    # the child process and get
    # its pid and
    # exit status indication
    info = os.wait()   

    # info is a tuple
    # info[0] represents child's id
    # info[1] represents exit status code

    print("\nIn parent process")

    # Check whether the child process
    # exited due to a signal
    # using os.WIFSIGNALED() method
    signaled = os.WIFSIGNALED(info[1])

    print("Child process exited due a signal?")
    print(signaled)

else :
    print("In Child process")
    print("Process ID:", os.getpid())
    print("Hello ! Geeks")

    # os.abort() method will
    # generate a SIGABRT signal
    # to the current process
    os.abort()
```

**Output:** 

```
In Child process
Process ID: 10224
Hello! Geeks

In parent process
Child process exited due a signal?
True
```

**代码#2:** 使用 ***os。**方法*

## 蟒蛇 3

```
# Python program to explain os.WIFSIGNALED() method

# importing os and signal module 
import os, signal

# Create a child process
# using os.fork() method
pid = os.fork()

# pid greater than 0
# indicates the parent process
if pid :

    # Create one more child
    pid2 = os.fork()

    if pid2 :

        # Wait for the completion of
        # first child process and get
        # its pid and
        # exit status indication
        # using os.waitpid() method
        child1_info = os.waitpid(pid, 0)

        # Send signal 'SIGKILL' to
        # second child process
        # using os.kill() method
        # and get its pid and
        # exit status code
        # using os.waitpid() method
        os.kill(pid2, signal.SIGKILL)
        child2_info = os.waitpid(pid2, 0)   

        # os.waitpid() method
        # returns a tuple which
        # represents child's pid
        # and exit status code

        print("\nIn parent process")

        # Check whether the first child
        # process exited due a signal
        # using os.WIFSIGNALED() method
        isSignaled = os.WIFSIGNALED(child1_info[1])

        print("First child process exited due to a signal?")
        print(isSignaled)

        # Check whether the second child
        # process exited due a signal
        # using os.WIFSIGNALED() method
        isSignaled = os.WIFSIGNALED(child2_info[1])

        print("Second child process exited due to a signal?")
        print(isSignaled)

    else :
        print("\nIn second child process")
        print("Process id:", os.getpid())
        print("Hey ! there")
        while True :
            print("Waiting for signal..")

else :
    print("In first child process")
    print("Process ID:", os.getpid())
    print("Hello ! Geeks")
    print("Exiting")
```

**Output:** 

```
In First child process
Process ID: 3752
Hello! Geeks

In second child process
Process id: 3753
Hey! there
Waiting for signal..
Waiting for signal..
Waiting for signal..
Waiting for signal..
Waiting for signal..

In parent process
First child process exited due to a signal?
False
Second child process exited due to a signal?
True
```

**参考文献:**T2https://docs.python.org/3/library/os.html#os.WIFSIGNALED