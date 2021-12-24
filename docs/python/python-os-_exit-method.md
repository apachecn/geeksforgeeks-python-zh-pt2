# Python | os。_ 退出()方法

> 原文:[https://www.geeksforgeeks.org/python-os-_exit-method/](https://www.geeksforgeeks.org/python-os-_exit-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

`***os._exit()***`Python 中的方法用于以指定的状态退出进程，而无需调用清理处理程序、刷新 stdio 缓冲区等。

**注意:**此方法通常用于 os.fork()系统调用后的子进程。退出流程的标准方式是`***sys.exit(n)***`方法。

> **语法:** os。_ 退出(状态)
> 
> **参数:**
> **状态:**代表退出状态的整数值或以上定义值。
> 
> **返回类型:**该方法在调用过程中不返回值。

**代码:**使用`***os._exit()***`方法

```py
# Python program to explain os._exit() method 

# importing os module  
import os

# Create a child process
# using os.fork() method 
pid = os.fork()

# pid greater than 0
# indicates the parent process 
if pid > 0:

    print("\nIn parent process")
    # Wait for the completion 
    # of child process and    
    # get its pid and 
    # exit status indication using
    # os.wait() method
    info = os.waitpid(pid, 0)

    # os.waitpid() method returns a tuple
    # first attribute represents child's pid
    # while second one represents
    # exit status indication

    # Get the Exit code 
    # used by the child process
    # in os._exit() method

    # firstly check if
    # os.WIFEXITED() is True or not
    if os.WIFEXITED(info[1]) :
        code = os.WEXITSTATUS(info[1])
        print("Child's exit code:", code)

else :
    print("In child process")
    print("Process ID:", os.getpid())
    print("Hello ! Geeks")
    print("Child exiting..")

    # Exit with status os.EX_OK
    # using os._exit() method
    # The value of os.EX_OK is 0        
    os._exit(os.EX_OK)
```

**Output:**

```py
In child process
Process ID: 15240
Hello! Geeks
Child exiting..

In parent process
Child's exit code: 0

```

**参考文献:**T2】https://docs.python.org/3/library/os.html#os._exit