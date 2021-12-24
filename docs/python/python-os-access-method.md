# Python | os.access()方法

> 原文:[https://www.geeksforgeeks.org/python-os-access-method/](https://www.geeksforgeeks.org/python-os-access-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统，属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

**`os.access()`** 方法使用真实的 uid/gid 来测试对路径的访问。大多数操作使用有效的 uid/gid，因此，这个例程可以在 suid/sgid 环境中使用，以测试调用用户是否具有指定的路径访问权限。

**语法:**

```py
os.access(path, mode)
```

**参数:**

> **路径:**要测试访问或存在的路径
> **模式:**应该是 F_OK 来测试路径的存在，或者可以是 R_OK、W_OK、X_OK 中的一个或多个的包含 or 来测试权限。

可以将以下值作为 access()的模式参数传递，以测试以下内容:

*   **os。F_OK:** 测试路径的存在性。*   **os。R_OK:** 测试路径的可读性。*   **os。W_OK:** 测试路径的可写性。*   **os.X_OK:** Checks if path can be executed.

    **返回:**如果允许访问，则返回真，否则返回假。

    **代码#1:** 了解访问()方法

    ```py
    # Python program tyring to access
    # file with different mode parameter

    # importing all necessary libraries
    import os
    import sys

    # Different mode parameters will 
    # return True if access is allowed,
    # else returns False.

    # Assuming only read operation is allowed on file
    # Checking access with os.F_OK
    path1 = os.access("gfg.txt", os.F_OK)
    print("Exists the path:", path1)

    # Checking access with os.R_OK
    path2 = os.access("gfg.txt", os.R_OK)
    print("Access to read the file:", path2)

    # Checking access with os.W_OK
    path3 = os.access("gfg.txt", os.W_OK)
    print("Access to write the file:", path3)

    # Checking access with os.X_OK
    path4 = os.access("gfg.txt", os.X_OK)
    print("Check if path can be executed:", path4)
    ```

    **输出:**

    ```py
    Exists the path: True
    Access to read the file: True
    Access to write the file: False
    Check if path can be executed: False
    ```

    **代码#2:** 允许验证访问后打开文件的代码

    ```py
    # Python program to open a file
    # after validating the access

    # checking readability of the path
    if os.access("gfg.txt", os.R_OK):

        # open txt file as file
        with open("gfg.txt") as file:
            return file.read()

    # in case can't access the file        
    return "Facing some issue"
    ```

    **输出:**

    ```py
    Facing some issue
    ```