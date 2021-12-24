# if _ _ name _ _ = = " _ _ main _ _ ":做什么？

> 原文:[https://www . geesforgeks . org/what-the-if-then-name _ _-_ _ main _ _-do/](https://www.geeksforgeeks.org/what-does-the-if-__name__-__main__-do/)

在执行代码之前，Python 解释器读取源文件并定义很少的特殊变量/全局变量。
如果 python 解释器将该模块(源文件)作为主程序运行，它会将特殊的 __name__ 变量设置为一个值**“_ _ main _ _”**。如果该文件正从另一个模块导入，则 __name__ 将被设置为**模块的名称。**模块的名称可以作为 __name__ 全局变量的值。

模块是包含 Python 定义和语句的文件。文件名是带后缀的模块名。附加了 py。

当我们对 python 解释器执行 file as 命令时，

```py
python script.py
```

## 蟒蛇 3

```py
# Python program to execute
# main directly
print ("Always executed")

if __name__ == "__main__":
    print ("Executed when invoked directly")
else:
    print ("Executed when imported")
```

*   所有缩进级别为 0[块 1]的代码都会被执行。定义好的函数和类都已经定义好了，但是它们的代码都没有运行。
*   这里，当我们直接执行 script.py 时 __name__ 变量将是 **__main__** 。因此，这个 if 块[Block 2]中的代码只有在该模块是程序的入口点时才会运行。
*   因此，您可以通过测试 __name__ 变量来测试您的脚本是直接运行还是由其他东西导入。
*   如果脚本正在被某个其他模块导入，那么**_ _ 名称 __** 将是模块名称。

**我们为什么需要它？**

例如，我们正在开发设计用作模块的脚本:

## 蟒蛇 3

```py
# Python program to execute
# function directly
def my_function():
    print ("I am inside function")

# We can test function by calling it.
my_function()
```

现在，如果我们想通过导入来使用该模块，我们必须注释掉我们的调用。最好的方法不是使用这种方法，而是使用以下代码:

## 蟒蛇 3

```py
# Python program to use
# main for function call.
if __name__ == "__main__":
    my_function()

import myscript

myscript.my_function()
```

**优势:**

1.  每个 Python 模块都定义了它的 __name__ 如果这是“__main__”，这意味着该模块由用户独立运行，我们可以做相应的适当操作。
2.  如果将此脚本作为另一个脚本中的模块导入，则将 __name__ 设置为脚本/模块的名称。
3.  Python 文件既可以作为可重用模块，也可以作为独立程序。
4.  if _ _ name _ _ = =“main”:如果文件是直接运行的，而不是导入的，则仅用于执行部分代码**。**

**本文由 **Nirmi Shah** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**