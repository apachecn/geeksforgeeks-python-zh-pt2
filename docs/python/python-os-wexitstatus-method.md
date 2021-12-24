# Python | os。WEXITSTATUS()方法

> 原文:[https://www.geeksforgeeks.org/python-os-wexitstatus-method/](https://www.geeksforgeeks.org/python-os-wexitstatus-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

如果`***os.WIFEXITED(status)***`为真，Python 中的`***os.WEXITSTATUS()***`方法用于获取退出(2)系统调用时进程使用的整数参数。如果`***os.WIFEXITED(status)***`为假，则该方法返回一个无意义的值。

> **语法:**OS . wexity status(状态)
> 
> **参数:**
> **状态:**该参数取 os.system()、os.wait()或 os.waitpid()方法返回的进程状态码(整数值)。
> 
> **返回类型:**该方法返回一个进程在 exit(2)系统调用中使用的整数值。

**代码:**使用`***os.WEXITSTATUS()***`方法

```
# Python program to explain os.WEXITSTATUS() method 

# importing os module  
import os

# Create a child process
# using os.fork() method 
pid = os.fork()

# pid greater than 0
# indicates the parent process 
if pid :

    # Create one more child
    pid2 = os.fork()

    if pid2 :

        print("\nIn parent process")
        # Wait for the completion 
        # of first child process and    
        # get its pid and 
        # exit status indication using
        # os.waitpid() method
        info1 = os.waitpid(pid, 0)

        # Wait for the completion 
        # of second child process and    
        # get its pid and 
        # exit status indication using
        # os.waitpid() method
        info2 = os.waitpid(pid2, 0)

        # os.waitpid() method returns a tuple
        # first attribute represents child's pid
        # while second one represents
        # exit status indication

        # Get the integer parameter 
        # used first child process
        # in exit(2) system call

        # firstly check if
        # os.WIFEXITED() is True or not
        if os.WIFEXITED(info1[1]) :
            code = os.WEXITSTATUS(info1[1])
            print("First child's exit code:", code)
        else :
            print("First child does not exited using exit(2) system call.")

        # Get the integer parameter 
        # used second child process
        # in exit(2) system call

        # firstly check if
        # os.WIFEXITED() is True or not
        if os.WIFEXITED(info2[1]) :
            code = os.WEXITSTATUS(info2[1])
            print("\nSecond child's exit code:", code)
        else :
            print("\nSecond child does not exited using exit(2) system call.")

    else :
        print("\nIn second child process")
        print("Process ID:", os.getpid())
        print("Hey ! there")
        print("Second child aborted")

        # os.abort() method will
        # generate a SIGABRT signal
        # to the current process.
        os.abort()    

else :
    print("In first child process")
    print("Process ID:", os.getpid())
    print("Hello ! Geeks")
    print("First child exiting..")

    # Exit with status code 5
    # using os._exit() method        
    os._exit(5)
```

**Output:**

```
In first child process
Process ID: 11614
Hello! Geeks
First child exiting..

In second child process
Process ID: 11615
Hey! there
Second child aborted

In parent process
First child's exit code: 5
Second child does not exited using exit(2) system call.

```

**参考文献:**T2】https://docs.python.org/3/library/os.html#os.WEXITSTATUS