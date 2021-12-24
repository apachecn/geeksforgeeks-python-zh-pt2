# Python | os。WTERMSIG()方法

> 原文:[https://www.geeksforgeeks.org/python-os-wtermsig-method/](https://www.geeksforgeeks.org/python-os-wtermsig-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。
***os。使用 Python 中的 WTERMSIG()*** 方法获取导致进程退出的信号编号。该方法以 ***os.wait()*** 、 ***os.system()*** 或 ***os.waitpid()*** 方法返回的进程状态代码为参数。

> **语法:** os。WTERMSIG(状态)
> **参数:**
> **状态:**该参数取 os.system()、os.wait()或 os.waitpid()方法返回的进程状态码(整数值)。
> **返回类型:**该方法返回一个整数值，代表导致进程退出的信号号。

**代码#1:** 使用 ***os。*** 方法

## 蟒蛇 3

```
# Python program to explain os.WTERMSIG() method

# importing os and signal module 
import os, signal

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

    # Get the signal number which caused
    # the child process to exit
    sig_num = os.WTERMSIG(info[1])

    print("Child process exited due to signal no:", sig_num )

    # We can get the signal name
    # corresponding to the signal number
    # in following way
    print("Signal name:", signal.Signals(sig_num).name)
else :
    print("In Child process")
    print("Process ID:", os.getpid())
    print("Hello ! Geeks")

    # os.abort() method will
    # generate a SIGABRT signal
    # to the current process
    # and will produce core dump.
    os.abort()
```

**Output:** 

```
In Child process
Process ID: 3421
Hello! Geeks

In parent process
Child process exited due to signal no: 6
Signal name: SIGABRT
```

**代码#2:** 使用 ***os。*** 方法

## 蟒蛇 3

```
# Python program to explain os.WTERMSIG() method

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

        # Wait for the completion of
        # second child process and get
        # its pid and exit status indication
        # using os.waitpid() method
        child2_info = os.waitpid(pid2, 0)   

        # os.waitpid() method
        # returns a tuple which
        # represents child's pid
        # and exit status code

        print("\nIn parent process")
        # Get the signal number which caused
        # first child process to exit
        sig_num = os.WTERMSIG(child1_info[1])
        if sig_num != 0 :
            print("First child process exited due to signal no:", sig_num )
            print("Signal name:", signal.Signals(sig_num).name)
        else:
            print("First child exited normally")

        # Get the signal number which caused
        # second child process to exit
        sig_num = os.WTERMSIG(child2_info[1])
        if sig_num != 0 :
            print("Second child process exited due to signal no:", sig_num )
            print("Signal name:", signal.Signals(sig_num).name)

        else:
            print("Second child exited normally")

        # sig_num equal to 0 represents
        # that no signal caused
        # the process to exit        

    else :
        print("\nIn second child process")
        print("Process id:", os.getpid())
        print("Hey ! there")
        print("Exiting..")

else :
    print("In first child process")
    print("Process ID:", os.getpid())
    print("Hello ! Geeks")

    # os.abort() method will
    # generate a SIGABRT signal
    # to the current process
    os.abort()
```

**Output:** 

```
In First child process
Process ID: 3752
Hello! Geeks

In second child process
Process id: 3753
Hey! there
Exiting..

In parent process
First child process exited due to signal no: 6
Signal name: SIGABRT
Second child exited normally
```

**参考文献:**T2https://docs.python.org/3/library/os.html#os.WTERMSIG