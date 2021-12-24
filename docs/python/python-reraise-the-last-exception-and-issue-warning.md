# Python |重新显示最后一个异常并发出警告

> 原文:[https://www . geesforgeks . org/python-re raise-最后一个异常和问题-警告/](https://www.geeksforgeeks.org/python-reraise-the-last-exception-and-issue-warning/)

**问题–**重发异常，该异常已被**除**块捕获。

**Code #1: Using raise statement all by itself.**

```
def example():
    try:
        int('N/A')
    except ValueError:
        print("Didn't work")
        raise

example()
```

**输出:**

```
Didn't work
Traceback (most recent call last):
    File "", line 1, in 
    File "", line 3, in example
ValueError: invalid literal for int() with base 10: 'N/A'

```

当不需要采取任何措施来响应异常(例如，日志记录、清理等)时，通常会出现这个问题。).一个非常常见的用法可能是在全面异常处理程序中。

**代码#2:捕获所有异常处理程序。**

```
try:
 ...
except Exception as e:
    # Process exception information in some way
    ...
    # Propagate the exception
    raise
```

**问题 2–**让程序发出警告消息(例如，关于不推荐使用的功能或使用问题)。

**代码#3:使用`warnings.warn()`功能**

```
import warnings
def func(x, y, logfile = None, debug = False):
    if logfile is not None:
        warnings.warn('logfile argument deprecated',
                                DeprecationWarning)
```

`warn()`的参数是一条警告消息和一个警告类，通常是以下内容之一:
用户警告、拒绝警告、语法警告、运行时警告、资源警告或未来警告。
警告的处理取决于解释器的执行方式和其他配置。

使用 `-W all` 选项运行 Python 时的**输出。**

```
bash % python3 -W all example.py
example.py:5: DeprecationWarning: logfile argument is deprecated
  warnings.warn('logfile argument is deprecated', DeprecationWarning) 
```

通常，警告只会在标准错误时产生输出消息。要将警告变为异常，请使用 `-W error` 选项。

```
bash % python3 -W error example.py
Traceback (most recent call last):
    File "example.py", line 10, in <module>func(2, 3, logfile ='log.txt')
    File "example.py", line 5, in func
        warnings.warn('logfile argument is deprecated', DeprecationWarning)
DeprecationWarning: logfile argument is deprecated
bash %</module> 
```