# Python 主功能

> 原文:[https://www.geeksforgeeks.org/python-main-function/](https://www.geeksforgeeks.org/python-main-function/)

Main 函数就像程序的入口点。然而，Python 解释器从第一行就运行代码。代码的执行从开始一行一行地开始。主要功能存在于何处或是否存在并不重要。

由于 Python 中没有`main()`函数，所以当运行 Python 程序的命令被给予解释器时，处于 0 级缩进的代码将被执行。然而，在此之前，它将定义一些特殊的变量。`__name__` 就是这样一个特殊变量。如果源文件作为主程序执行，解释器将`__name__`变量设置为值`__main__`。如果该文件正从另一个模块导入，`__name__` 将被设置为该模块的名称。
`__name__`是一个内置变量，计算当前模块的名称。

**示例:**

```
# Python program to demonstrate
# main() function

print("Hello")

# Defining main function
def main():
    print("hey there")

# Using the special variable 
# __name__
if __name__=="__main__":
    main()
```

**输出:**

```
Hello
hey there

```

执行上述程序时，解释器将 name 的初始值声明为“main”。当解释器到达 if 语句时，它检查 name 的值，当 if 的值为真时，它运行 main 函数，否则 main 函数不执行。

#### 作为模块的主要功能

现在，当我们将 python 脚本作为模块导入时，`__name__`变量将获得与导入的 Python 脚本名称相同的值。

**示例:**我们来考虑一下有两个文件(File1.py 和 File2.py)。文件 1 如下。

```
# File1.py 

print("File1 __name__ = %s" %__name__)

if __name__ == "__main__": 
    print("File1 is being run directly")
else: 
    print("File1 is being imported")
```

**输出:**

```
File1 __name__ = __main__
File1 is being run directly

```

现在，当文件 1.py 被导入文件 2.py 时，__name__ 的值会发生变化。

```
# File2.py 

import File1 

print("File2 __name__ = %s" %__name__)

if __name__ == "__main__":
    print("File2 is being run directly")
else: 
    print("File2 is being imported")
```

**输出:**

```
File1 __name__ = File1
File1 is being imported
File2 __name__ = __main__
File2 is being run directly

```

如上图所示，直接运行 File1.py 时，解释器将`__name__`变量设置为`__main__`，通过导入运行 File2.py 时，将 __name__ 变量设置为 python 脚本的名称，即 File1。因此，可以说，如果 _ _ name _ _ = = " _ _ main _ _ "是程序的一部分，当使用 Python File1.py 这样的命令从命令行运行脚本时，该部分就会运行