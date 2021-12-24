# Python 模块

> 原文:[https://www.geeksforgeeks.org/python-modules/](https://www.geeksforgeeks.org/python-modules/)

Python 模块是包含 Python 定义和语句的文件。模块可以定义函数、类和变量。模块也可以包括可运行的代码。将相关代码分组到一个模块中使代码更容易理解和使用。它还使代码有逻辑地组织起来。

### **示例:创建一个简单的模块**

## 计算机编程语言

```py
# A simple module, calc.py

def add(x, y):
    return (x+y)

def subtract(x, y):
    return (x-y)
```

## **Python 中的导入模块–导入语句**

我们可以使用其他 Python 源文件中的 [**导入语句**](https://www.geeksforgeeks.org/import-module-python/) 将一个模块中定义的函数、类导入到另一个模块中。

**语法:**

```py
import module
```

当解释器遇到导入语句时，如果模块出现在搜索路径中，它将导入该模块。搜索路径是解释器在导入模块时搜索的目录列表。例如，要导入模块 calc.py，我们需要将以下命令放在脚本的顶部。

**注意:**这不会直接导入函数或类，而是只导入模块。要访问模块内部的功能，请使用点号(。)运算符。

### **示例:在 Python 中导入模块**

## 计算机编程语言

```py
# importing  module calc.py
import calc

print(calc.add(10, 2))
```

**输出:**

```py
12
```

## **The from import******Statement****

**Python 的 *from* 语句允许您从模块导入特定属性，而无需将模块作为一个整体导入。**

### **示例:从模块导入特定属性**

## **蟒蛇 3**

```py
# importing sqrt() and factorial from the
# module math
from math import sqrt, factorial

# if we simply do "import math", then
# math.sqrt(16) and math.factorial()
# are required.
print(sqrt(16))
print(factorial(6))
```

****输出:****

```py
4.0
720
```

## **导入所有名称–从导入*语句**

**与 from import 语句一起使用的*符号用于将模块中的所有名称导入到当前命名空间。**

****语法:****

```py
from module_name import *
```

**使用*有它的优点和缺点。如果您确切知道您将从该模块中需要什么，则不建议使用*，否则请使用。**

### **示例:导入所有名称**

## **蟒蛇 3**

```py
# importing sqrt() and factorial from the
# module math
from math import *

# if we simply do "import math", then
# math.sqrt(16) and math.factorial()
# are required.
print(sqrt(16))
print(factorial(6))
```

****Output**

```py
4.0
720

```** 

## **定位模块**

**每当在 Python 中导入一个模块时，解释器都会寻找几个位置。首先，它将检查内置模块，如果没有找到，那么它将查找在[系统路径](https://www.geeksforgeeks.org/sys-path-in-python/)中定义的目录列表。Python 解释器按照以下方式搜索模块–**

*   **First, it searches the current directory for modules.**
***   If the module is not found in the current directory, Python will search every directory in the shell variable [. PYTHONPATH is an environment variable, which consists of a directory list.](https://www.geeksforgeeks.org/pythonpath-environment-variable-in-python/)*   If it fails again, python will check the list of installation-dependent directories configured when installing Python.**

### ****示例:模块目录列表****

## **蟒蛇 3**

```py
# importing sys module
import sys

# importing sys.path
print(sys.path)
```

****输出:****

> **['/home/nikhil/Desktop/gfg '，'/usr/lib/python38.zip '，'/usr/lib/python3.8 '，'/usr/lib/python3.8/lib-dynload '，"，'/home/nikhil/。local/lib/python 3 . 8/site-packages '，'/usr/local/lib/python 3 . 8/dist-packages '，'/usr/lib/python3/dist-packages '，'/usr/local/lib/python 3 . 8/dist-packages/IPython/extensions '，'/home/nikhil/。**

## **导入和重命名模块**

**我们可以在导入模块时使用 as 关键字对其进行重命名。**

### **示例:重命名模块**

## **蟒蛇 3**

```py
# importing sqrt() and factorial from the
# module math
import math as gfg

# if we simply do "import math", then
# math.sqrt(16) and math.factorial()
# are required.
print(gfg.sqrt(16))
print(gfg.factorial(6))
```

****Output**

```py
4.0
720

```** 

## ****dir()功能****

**dir()内置函数返回包含模块定义的名称的字符串排序列表。该列表包含模块中定义的所有模块、变量和函数的名称。**

**T2T4

```py
#  Import built-in module  random
import  random
print(dir(random))
```

T5**

****输出:****

> **['BPF '，' LOG4 '，' NV _ MAGICCONST '，' RECIP_BPF '，' Random '，' SG _ MAGICCONST '，' SystemRandom '，' TWOPI '，' _BuiltinMethodType '，' _Sequence '，' _Set '，' __all__ '，' __ builtins _ _ '，' __cached_ '，' __doc_ '，' __file__ '，' __loader__ '，' __name__ '，' _ _ '**

****说明 python 内置模块的代码片段:****

## **python 3**

```py
# importing built-in module math
import math

# using square root(sqrt) function contained 
# in math module
print(math.sqrt(25)) 

# using pi function contained in math module
print(math.pi) 

# 2 radians = 114.59 degrees
print(math.degrees(2))  

# 60 degrees = 1.04 radians
print(math.radians(60))  

# Sine of 2 radians
print(math.sin(2))  

# Cosine of 0.5 radians
print(math.cos(0.5))  

# Tangent of 0.23 radians
print(math.tan(0.23)) 

# 1 * 2 * 3 * 4 = 24
print(math.factorial(4))  

# importing built in module random
import random

# printing random integer between 0 and 5
print(random.randint(0, 5))  

# print random floating point number between 0 and 1
print(random.random())  

# random number between 0 and 100
print(random.random() * 100)  

List = [1, 4, True, 800, "python", 27, "hello"]

# using choice function in random module for choosing 
# a random element from a set such as a list
print(random.choice(List)) 

# importing built in module datetime
import datetime
from datetime import date
import time

# Returns the number of seconds since the
# Unix Epoch, January 1st 1970
print(time.time())  

# Converts a number of seconds to a date object
print(date.fromtimestamp(454554))  
```

****输出:****

```py
5.0
3.14159265359
114.591559026
1.0471975512
0.909297426826
0.87758256189
0.234143362351
24
3
0.401533172951
88.4917616788
True
1461425771.87
1970-01-06
```

 **本文由 **Gaurav Shrestha** 供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。**