# 用 Python 中的语句

> 原文:[https://www.geeksforgeeks.org/with-statement-in-python/](https://www.geeksforgeeks.org/with-statement-in-python/)

Python 中的 **`with`** 语句用于异常处理，使代码更加清晰易读。它简化了文件流等公共资源的管理。观察下面的代码示例，了解使用`with`语句如何使代码更加清晰。

```
# file handling

# 1) without using with statement
file = open('file_path', 'w')
file.write('hello world !')
file.close()

# 2) without using with statement
file = open('file_path', 'w')
try:
    file.write('hello world')
finally:
    file.close()
```

```
# using with statement
with open('file_path', 'w') as file:
    file.write('hello world !')
```

请注意，与前两种实现不同，使用`with`语句时不需要调用`file.close()`。`with`声明本身确保了资源的适当获取和释放。第一个实现中`file.write()`调用期间的异常会阻止文件正确关闭，这可能会在代码中引入几个错误，即文件中的许多更改直到文件正确关闭后才会生效。

上面例子中的第二种方法处理了所有的异常，但是使用`with`语句使得代码更加紧凑，可读性更强。因此，`with`语句通过确保在使用资源的代码完全执行时正确释放资源，帮助避免错误和泄漏。`with`语句通常用于文件流，如上所示，以及锁、套接字、子进程和远程登录等。

### 支持用户定义对象中的“with”语句

`open()`中没有什么特别之处，使得它可以与`with`语句一起使用，并且可以在用户定义的对象中提供相同的功能。在您的对象中支持`with`语句将确保您永远不会让任何资源处于打开状态。
要在用户定义的对象中使用`with`语句，您只需要在对象方法中添加方法`__enter__()`和`__exit__()`。考虑下面的例子来进一步澄清。

```
# a simple file writer object

class MessageWriter(object):
    def __init__(self, file_name):
        self.file_name = file_name

    def __enter__(self):
        self.file = open(self.file_name, 'w')
        return self.file

    def __exit__(self):
        self.file.close()

# using with statement with MessageWriter

with MessageWriter('my_file.txt') as xfile:
    xfile.write('hello world')
```

让我们检查一下上面的代码。如果你注意到了，`with`关键字后面的是`MessageWriter`的构造函数。一旦执行进入`with`语句的上下文，就会创建一个`MessageWriter`对象，python 然后调用`__enter__()`方法。在这个`__enter__()`方法中，初始化你希望在对象中使用的资源。这个`__enter__()`方法应该总是返回所获取资源的描述符。

**什么是资源描述符？**
这些是操作系统提供的访问请求资源的句柄。在下面的代码块中，`file`是文件流资源的描述符。

```
file = open('hello.txt')
```

在上面提供的`MessageWriter`示例中，`__enter__()`方法创建一个文件描述符并返回它。这里`xfile`这个名字是用来指`__enter__()`方法返回的文件描述符。使用获取的资源的代码块被放置在`with`语句的块中。一旦执行了`with`块中的代码，就调用`__exit__()`方法。所有获取的资源都通过`__exit__()`方法释放。这就是我们如何对用户定义的对象使用`with`语句。

在用户定义对象中提供`with`语句支持的`__enter__()`和`__exit__()`方法的这个接口称为 ***上下文管理器*** 。

### contextlib 模块

如上所示的基于类的上下文管理器不是支持用户定义对象中的`with`语句的唯一方法。 [`contextlib`](https://docs.python.org/2/library/contextlib.html) 模块提供了一些建立在基本上下文管理器界面上的抽象。下面是我们如何使用`contextlib`模块重写`MessageWriter`对象的上下文管理器。

```
from contextlib import contextmanager

class MessageWriter(object):
    def __init__(self, filename):
        self.file_name = filename

    @contextmanager
    def open_file(self):
        try:
            file = open(self.file_name, 'w')
            yield file
        finally:
            file.close()

# usage
message_writer = MessageWriter('hello.txt')
with message_writer.open_file() as my_file:
    my_file.write('hello world')
```

在此代码示例中，由于其定义中的`[yield](https://www.geeksforgeeks.org/use-yield-keyword-instead-return-keyword-python/)`语句，函数`open_file()`是一个[生成器函数](https://www.geeksforgeeks.org/generators-in-python/)。
调用这个`open_file()`函数时，会创建一个名为`file`的资源描述符。这个资源描述符然后被传递给调用者，在这里由变量`my_file`表示。执行`with`块内的代码后，程序控制返回到`open_file()`功能。`open_file()`函数恢复执行，并执行`yield`语句后面的代码。出现在`yield`语句之后的这部分代码释放了获取的资源。这里的`@contextmanager`是一个[装饰器](https://www.geeksforgeeks.org/decorators-in-python/)。

以前基于类的实现和这个基于生成器的上下文管理器实现在内部是相同的。虽然后者看起来更具可读性，但它需要发电机、装修商和`yield`的知识。