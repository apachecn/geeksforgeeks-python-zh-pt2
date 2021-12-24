# Python 中用户定义的异常，示例

> 原文:[https://www . geesforgeks . org/用户定义-异常-python-示例/](https://www.geeksforgeeks.org/user-defined-exceptions-python-examples/)

先决条件- [本文是异常处理的扩展。](https://www.geeksforgeeks.org/python-exception-handling/)
当有代码出错时，Python 会抛出错误和异常，这可能会导致程序突然停止。Python 还在 try-except 的帮助下提供了一种异常处理方法。一些最常见的标准异常包括 IndexError、ImportError、IOError、ZeroDivisionError、TypeError 和 FileNotFoundError。用户可以使用异常类创建自己的错误。

**创建用户定义的异常**

程序员可以通过创建一个新的异常类来命名自己的异常。异常需要直接或间接从异常类派生。虽然不是强制性的，但大多数异常都是以**“Error”**结尾的名称命名的，类似于 python 中标准异常的命名。例如:

## 大蟒

```
# A python program to create user-defined exception

# class MyError is derived from super class Exception
class MyError(Exception):

    # Constructor or Initializer
    def __init__(self, value):
        self.value = value

    # __str__ is to print() the value
    def __str__(self):
        return(repr(self.value))

try:
    raise(MyError(3*2))

# Value of Exception is stored in error
except MyError as error:
    print('A New Exception occured: ',error.value)
```

输出:

```
('A New Exception occured: ', 6)
```

**了解异常类**

要了解关于异常类的更多信息，请运行下面的代码

## 大蟒

```
help(Exception)
```

**从超类异常中导出错误**

当一个模块需要处理几个不同的错误时，就会创建超类异常。常见的方法之一是为该模块定义的异常创建一个基类。此外，定义了各种子类来为不同的错误条件创建特定的异常类。

## 大蟒

```
# class Error is derived from super class Exception
class Error(Exception):

    # Error is derived class for Exception, but
    # Base class for exceptions in this module
    pass

class TransitionError(Error):

    # Raised when an operation attempts a state
    # transition that's not allowed.
    def __init__(self, prev, nex, msg):
        self.prev = prev
        self.next = nex

        # Error message thrown is saved in msg
        self.msg = msg
try:
    raise(TransitionError(2,3*2,"Not Allowed"))

# Value of Exception is stored in error
except TransitionError as error:
    print('Exception occured: ',error.msg)
```

输出:

```
('Exception occured: ', 'Not Allowed')
```

**如何使用标准异常作为**一个**基类？**
运行时错误是一个标准异常类，当生成的错误不属于任何类别时会引发该类。这个程序演示了如何使用运行时错误作为基类，使用网络错误作为派生类。以类似的方式，可以从 Python 的标准异常中派生出一个异常。

## 大蟒

```
# NetworkError has base RuntimeError
# and not Exception
class Networkerror(RuntimeError):
    def __init__(self, arg):
        self.args = arg

try:
    raise Networkerror("Error")

except Networkerror as e:
    print (e.args)
```

输出:

```
('E', 'r', 'r', 'o', 'r')
```

本文由 **Piyush Doorwar** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。