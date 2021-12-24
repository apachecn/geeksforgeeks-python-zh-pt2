# 为什么用 Python 导入 star 是个馊主意

> 原文:[https://www . geesforgeks . org/why-import-python 中的 star-是个坏主意/](https://www.geeksforgeeks.org/why-import-star-in-python-is-a-bad-idea/)

在 python 程序中使用 **import *** 被认为是一个坏习惯，因为这样会污染您的命名空间，import *语句会将所有函数和类导入到您自己的命名空间中，这可能会与您定义的函数或您导入的其他库的函数发生冲突。有时也很难说出某个特定功能来自哪个库。在导入实践中，覆盖变量/函数等的风险始终存在。

以下是关于为什么不应该使用**导入*** 的几点:

*   Code readability
*   What is imported is always a mystery, and it is not easy to find which module something is imported from, which leads to low readability of the code.
*   Pollution namespace, import * Import all functions and classes in your own namespace that may conflict with the functions and classes you define or those of other libraries that you may import.
*   The specific possibility of hiding bugs
*   Tools like pyflakes cannot be used to statically detect errors in source code.

所有这一切并不意味着使用 **import *** 总是不好的，如果我告诉你这个宇宙中没有什么比 import *更好的东西了，你一定会非常渴望。使用 import *时，您应该记住的唯一一件事是，您应该始终谨慎使用它，并遵守纪律。

现在让我们深入到一个例子中，以一种更实际、更容易理解的方式来看待这个问题。

考虑一个包 **a** ，它包含一个函数 **sum (a，b)**

```
# import the module a using import * 
from a import *

# define a function sum
def sum (x, y):
    return x + y

print (sum (2, 6))
```

这段代码的错误在于，我们定义的 sum 函数覆盖了我们导入的模块‘a’中的 sum 函数，我们甚至对此一无所知。此外，在大型程序的情况下，识别实际调用的是哪个函数变得非常困难。

正确方法:

```
# import the module a as l
import a as l

def sum (x, y):
    return x + y

# calls the self-defined sum function
print (sum (2, 6))

# calls the sum function defined in the module a
print (l.sum(2, 6))
```

以这种方式编码增加了代码的可读性，也变得易于调试，并且几乎没有任何冲突发生的可能性。