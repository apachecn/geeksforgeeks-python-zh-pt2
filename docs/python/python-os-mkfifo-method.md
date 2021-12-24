# Python | os.mkfifo()方法

> 原文:[https://www.geeksforgeeks.org/python-os-mkfifo-method/](https://www.geeksforgeeks.org/python-os-mkfifo-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.mkfifo()***`方法用于创建一个具有指定模式的 FIFO(一个命名管道)命名路径。

*先进先出*是命名管道，可以像其他常规文件一样访问。这个方法只创建*先进先出*，但是不要打开它，创建的先进先出在被删除之前是存在的。*先进先出*一般是我们作为客户端和“服务器”类型进程之间的汇合点。

> **语法:** os.mkfifo(路径，模式= 0o666，* dir _ FD =无)
> 
> **参数:**
> **路径:**表示文件系统路径的类路径对象。它可以是表示文件路径的字符串或字节对象。
> **模式**(可选):代表要创建的先进先出(命名管道)模式的数值。模式参数的默认值是 0o666(八进制)。
> **dir_fd** (可选):这是一个引用目录的文件描述符。
> 
> **注意:**参数列表中的“*”表示以下所有参数(在我们的例子中为‘dir _ FD’)都是仅包含关键字的参数，并且可以使用它们的名称来提供，而不是作为位置参数。
> 
> **返回类型:**此方法不返回值。

**代码:**使用`***os.mkfifo()***`方法

```
# Python3 program to explain os.mkfifo() method

# importing os module
import os

# Path
path = "./mypipe"

# Mode of the FIFO (a named pipe)
# to be created
mode = 0o600

# Create a FIFO named path
# with the specified mode
# using os.mkfifo() method
os.mkfifo(path, mode)

print("FIFO named '% s' is created successfully." % path)
```

**Output:**

```
FIFO named './mypipe' is created successfully.

```