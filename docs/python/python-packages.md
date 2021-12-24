# Python 包

> 原文:[https://www.geeksforgeeks.org/python-packages/](https://www.geeksforgeeks.org/python-packages/)

我们通常根据一些标准将文件组织在不同的文件夹和子文件夹中，以便轻松高效地管理它们。例如，我们将所有的游戏保存在一个游戏文件夹中，我们甚至可以根据游戏的类型或类似的东西进行子分类。Python 包遵循了同样的类比。

一个 [Python 模块](https://www.geeksforgeeks.org/python-modules/)可能包含几个类、函数、变量等。而 Python 包可以包含几个模块。简单来说，包是包含各种模块的文件夹。

## 创建包

让我们创建一个名为 mypckg 的包，它将包含两个模块 mod1 和 mod2。要创建此模块，请遵循以下步骤–

*   创建一个名为 mypckg 的文件夹。
*   在这个文件中创建一个空的 Python 文件，即 __init__。巴拉圭
*   然后在这个文件夹中创建两个模块 mod1 和 mod2。

### Mod1.py

## 蟒蛇 3

```py
def gfg():
    print("Welcome to GFG")
```

### Mod2.py 

## 蟒蛇 3

```py
def sum(a, b):
    return a+b
```

我们的产品包的层次结构如下–

```py
mypckg
|
|
---__init__.py
|
|
---mod1.py
|
|
---mod2.py
```

## 理解 __init__。巴拉圭

__init__。py 帮助 Python 解释器将文件夹识别为包。它还指定了要从模块中导入的资源。如果 __init__。py 为空这意味着模块的所有功能都将被导入。我们还可以指定每个模块中可用的功能。

例如，我们还可以创建 __init__。上述模块的 py 文件为–

### __init__.py

## 蟒蛇 3

```py
from .mod1 import gfg
from .mod2 import sum
```

这个 __init__。py 仅允许导入 mod1 和 mod2 模块中的 gfg 和 sum 功能。

## 从包中导入模块

我们可以使用 [from…import 语句](https://www.geeksforgeeks.org/import-module-python/)和点(。)运算符。

**语法:**

```py
import package_name.module_name
```

### 示例:从包导入模块

我们将从上面创建的包中导入模块，并将使用这些模块中的函数。

## 蟒蛇 3

```py
from mypckg import mod1
from mypckg import mod2

mod1.gfg()
res = mod2.sum(1, 2)
print(res)
```

**输出:**

```py
Welcome to GFG
3
```

我们也可以使用相同的语法导入特定的函数。

### 示例:从模块导入特定函数

## 蟒蛇 3

```py
from mypckg.mod1 import gfg
from mypckg.mod2 import sum

gfg()
res = sum(1, 2)
print(res)
```

**输出:**

```py
Welcome to GFG
3
```