# Python | os。WIFEXITED()方法

> 原文:[https://www.geeksforgeeks.org/python-os-wifexited-method/](https://www.geeksforgeeks.org/python-os-wifexited-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.WIFEXITED()***`方法用于检查进程是否使用 [exit(2)系统调用](https://linux.die.net/man/2/exit)退出。该方法以 os.system()、os.wait()或 os.waitpid()方法返回的进程状态码为参数，如果进程使用[退出(2)系统调用](https://linux.die.net/man/2/exit)退出，则返回*真*，否则返回*假*。

> **语法:** os。WIFEXITED(状态)
> 
> **参数:**
> **状态:**该参数取 os.system()、os.wait()或 os.waitpid()方法返回的进程状态码(整数值)。
> 
> **返回类型:**如果进程使用 exit(2)系统调用 exit 退出，则该方法返回 True，否则返回 False。

**代码:**使用`***os.WIFEXITED()***`方法

```
# Python program to explain os.WIFEXITED() method 

# importing os module  
import os

# Create a child process
# using os.fork() method 
pid = os.fork()

# pid greater than 0
# indicates the parent process 
if pid > 0:

    # Create one more child
    pid2 = os.fork()

    if pid2 > 0:

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

        # Check if the first child 
        # exited using exit(2) system call
        # using os.WIFEXITED() method
        if os.WIFEXITED(info1[1]) :
            print("First child exited using exit(2) system call.")
        else :
            print("First child does not exited using \
exit(2) system call.") 

        # Check if the second child 
        # exited using exit(2) system call
        # using os.WIFEXITED() method
        if os.WIFEXITED(info2[1]) :
            print("Second child exited using exit(2) system call.")
        else :
            print("Second child does not exited using \
exit(2) system call.") 

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

    # Exit using exit(2) system call        
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
First child exited using exit(2) system call.
Second child does not exited using exit(2) system call.

```

**参考文献:**T2】https://docs.python.org/3/library/os.html#os.WIFEXITED