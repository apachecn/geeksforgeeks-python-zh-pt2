# Python | os。WCOREDUMP()方法

> 原文:[https://www.geeksforgeeks.org/python-os-wcoredump-method/](https://www.geeksforgeeks.org/python-os-wcoredump-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.WCOREDUMP()***`方法用于检查进程是否生成了核心转储。该方法以`***os.wait()***`、`***os.system()***`或`***os.waitpid()***`方法返回的过程状态码为参数。

> **语法:** os。WCOREDUMP(状态)
> 
> **参数:**
> **状态:**该参数取 os.system()、os.wait()或 os.waitpid()方法返回的进程状态码(整数值)。
> 
> **返回类型:**这个方法返回一个布尔值类“bool”。如果为进程生成了核心转储，则返回 True，否则返回 False。

**代码#1:** 使用`***os.WCOREDUMP()***`方法

```py
# Python program to explain os.WCOREDUMP() method 

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
    # child's pid and
    # exit status indication
    info = os.wait()    

    # info is a tuple
    # info[0] represents child's id
    # info[1] represents exit status code

    print("\nIn parent process")

    # Check if core dump was
    # generated for the child process
    core_dump = os.WCOREDUMP(info[1]) 

    print("Was core dump generated?", core_dump)

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

```py
In Child process
Process ID: 15059
Hello! Geeks

In parent process
Was core dump generated? True

```

**代码#2:** 使用`***os.WCOREDUMP()***`方法

```py
# Python program to explain os.WCOREDUMP() method 

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

        # child_info is a tuple, where
        # child_info[0] represents child's id
        # child_info[1] represents exit status code

        print("\nIn parent process")

        # Check if core dump was
        # generated for the 
        # first child process
        core_dump = os.WCOREDUMP(child1_info[1]) 
        print("Was core dump generated for first child process?")
        print(core_dump)

        # Check if core dump was
        # generated for the 
        # first child process
        core_dump = os.WCOREDUMP(child2_info[1]) 
        print("\nWas core dump generated for second child process?")
        print(core_dump)

    else :
        print("\nIn second child process")
        print("Process id:", os.getpid())
        print("Hey ! there")
        print("Exiting") 

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

```py
In first child process
Process ID: 16289
Hello! Geeks

In second child process
Process id: 16290
Hey! there
Exiting

In parent process
Was core dump generated for first child process?
True

Was core dump generated for second child process?
False

```

**参考文献:**T2】https://docs.python.org/3/library/os.html#os.WCOREDUMP