# Python 的模块、包和库有什么区别？

> 原文:[https://www . geesforgeks . org/蟒蛇-模块-包-库的区别是什么/](https://www.geeksforgeeks.org/what-is-the-difference-between-pythons-module-package-and-library/)

**模块:****模块**是一个简单的 Python 文件，包含函数和全局变量的集合，扩展名为`.py`。它是一个可执行文件，为了组织所有模块，我们有一个在 Python 中称为 Package 的概念。

**示例:**将代码保存在名为 demo_module.py 的文件中

```
def myModule(name):
    print("This is My Module : "+ name)
```

导入名为 demo_module 的模块，并在其中调用 myModule 函数。

```
import demo_module

demo_module.myModule("Math")
```

**输出:**

```
This is My Module : Math
```

**包:****包**是一个包含模块集合的简单目录。该目录包含 Python 模块，并且还包含`[__init__.py](https://www.geeksforgeeks.org/__init__-in-python/)`文件，解释器通过该文件将其解释为包。包只是一个命名空间。包中还包含子包。

**示例:**

```
Student(Package)
| __init__.py (Constructor)
| details.py (Module)
| marks.py (Module)
| collegeDetails.py (Module)
```

**库:****库**有一个相关功能的代码集合，允许你在不写代码的情况下执行许多任务。这是一个可重用的代码块，我们可以通过在程序中导入它来使用它，我们可以通过导入那个库并用`period(.)`调用那个库的方法来使用它。

**例:**导入熊猫库，使用熊猫别名即 pd 调用 read_csv 方法。

```
import pandas as pd

df = pd.read_csv("file_name.csv")
```