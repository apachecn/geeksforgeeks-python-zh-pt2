# Python 中的警告

> 原文:[https://www.geeksforgeeks.org/warnings-in-python/](https://www.geeksforgeeks.org/warnings-in-python/)

提供警告是为了警告开发人员不一定是异常的情况。通常，当某些编程元素过时时会出现警告，如关键字、函数或类等。程序中的警告不同于错误。如果发生错误，Python 程序会立即终止。相反，警告并不重要。它显示一些信息，但程序运行。在“`warning`”模块中定义的`warn()`功能用于显示警告信息。警告模块实际上是异常的一个子类，异常是 Python 中的一个内置类。

```
# program to display warning a message 

import warnings

print('Geeks')

# displaying the warning message 
warnings.warn('Warning Message: 4')

print('Geeks !')
```

**输出:**

```
Geeks
main.py:8: UserWarning: Warning Message: 4  
  warnings.warn('Warning Message: 4')
Geeks!

```

在上述程序中，报警模块的`warn()`功能用于显示信息`Warning: Message: 4`，`UserWarning`是`warn()`功能的默认类别。

#### 警告类别

在 Python 中，有各种反映警告类别的内置异常，其中一些是:

*   **警告类:**是所有警告类别类的超级类，也是异常类的子类。
*   **UserWarning 类:** warn()函数默认类别。
*   **过时警告类:**针对过时功能的警告的基本类别，这些警告是针对其他开发人员的(由 __main__ 中的代码触发，除非被忽略)。
*   **语法警告类:**可疑语法属性警告的基类。
*   **运行时警告类:**可疑运行时属性警告的基类。
*   **未来学习类:**当某些警告是针对 Python 编写的程序的最终用户时，关于过时功能的警告的基类。
*   **挂起的属性警告类:**过期属性警告的基类。
*   **导入警告类:**模块导入过程中导致的警告的基类。
*   【Unicode 警告类:基于 Unicode 的警告的基类。
*   **字节警告类:**基于字节和字节数组的警告的基类。
*   **资源警告类:**资源相关警告的基类。

#### 警告过滤器

Python 中的警告过滤器处理警告(出现、忽略或引发异常)。警告过滤器建立过滤器参数的组织列表，任何特定的警告在整个列表中的每个过滤器要求上匹配，直到匹配完成，过滤器确定匹配安排。每个条目实际上都是以下形式的元组(动作、消息、类别、模块、行号):

*   The **action** can be any of the following strings:

    | Line | Description |
    | --- | --- |
    | "Default" | Display the first matching warning for each position |
    | 【 Error 】 | The opposite warning |
    | 【 Ignore 】 | do not display the matching warning. | Always | Always display matching warnings |
    | Module | Display the first matching warning of each module |
    | "Once" |

*   **消息**是一个字符串，其正则表达式必须与警告的开头相匹配。(编译的表达式总是不区分大小写)
*   **类别**是警告类必须是子类才能匹配的类(警告子类)。
*   **模块**是一个带有正则表达式的字符串，该表达式必须与模块名称匹配(编译的表达式总是不区分大小写)。
*   **行号**是一个整数，用于匹配出现警告的行号，或者是 0，用于匹配任何行号。

#### 警告功能

警告模块的一些常用功能有:

*   **warn(message, category=None, stacklevel=1, source=None):** This function displays a warning, or disregard it or converts is to an exception.

    ```
    # program to illustrate warn() 
    # function in warning module

    # importing modules
    import warnings

    # displaying warning
    warnings.warn('Geeks 4 Geeks')
    ```

    **输出:**

    ```
    main.py:2: UserWarning: Geeks 4 Geeks
      warnings.warn('Geeks 4 Geeks')

    ```

    在上述程序中，使用警告模块的`warn()`功能显示警告。

*   **warn_explicit(消息、类别、文件名、行号、模块=无、注册表=无、模块 _ globals =无、源=无):**这个函数是一个具有 warn()特性的低级方法
*   **filterwarnings(action, message=”, category=Warning, module=”, lineno=0, append=False):** This function adds an entry into the specifications of the warnings filter.

    ```
    # program to illustrate filterwarnings()
    # function in warning module

    # importing module
    import warnings

    # adding entry into the specifications
    # of the warnings filter.
    warnings.filterwarnings('ignore', '.*do not.*', )

    # displaying warinings
    warnings.warn('Geeks 4 Geeks !')

    # this warning will not be displayed
    warnings.warn('Do not show this message')
    ```

    **输出:**

    ```
    main.py:8: UserWarning: Geeks 4 Geeks!
      warnings.warn('Geeks 4 Geeks!')

    ```

    此处由于`warnings.filterwarnings('ignore', '.*do not.*', )`不显示第二条警告信息，其中动作为`"ignore"`。

*   **显示警告(消息、类别、文件名、行号、文件=无、行=无):**该函数向文件写入警告。
*   **simplefilter(action, category=Warning, lineno=0, append=False):** This function adds a single entry into the warnings filter requirements list.

    ```
    # program to illustrate simplefilter() 
    # function in warning module

    # importing module
    import warnings

    # adding a single entry into warnings filter
    warnings.simplefilter('error', UserWarning)

    # displaying the warning
    warnings.warn('This is a warning message')
    ```

    **输出:**

    ```
    Traceback (most recent call last):
      File "main.py", line 8, in     
         warnings.warn('This is a warning message')
    UserWarning: This is a warning message

    ```

    在上述程序中，使用`warnings.simplefilter('error', UserWarning)`将单个条目添加到警告过滤器中，其中动作为`"error"`，类别为`UserWrning`，然后使用`warn()`方法显示警告。