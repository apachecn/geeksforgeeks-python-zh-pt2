# 将字符串矩阵表示转换为矩阵的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序-转换-字符串-矩阵-表示-矩阵/](https://www.geeksforgeeks.org/python-program-to-convert-string-matrix-representation-to-matrix/)

给定一个带有矩阵表示的字符串，这里的任务是编写一个 python 程序，将它转换成矩阵。

> **输入:** test_str = "[gfg，is]，[best，for]，[all，geeks]"
> 
> **输出:** [['gfg '，' is']，['best '，' for']，['all '，' geeks']]
> 
> **说明:**必选字符串矩阵转换为列表为数据类型的矩阵。
> 
> **输入:** test_str = "[gfg，is]，[for]，[all，geeks]"
> 
> **输出:** [['gfg '，' is']，['for']，['all '，' geeks']]
> 
> **说明:**必选字符串矩阵转换为列表为数据类型的矩阵。

**方法 1 :** 使用[分裂()](https://www.geeksforgeeks.org/python-string-split/)和[正则表达式](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)

在这种情况下，使用适当的正则表达式构造一个普通列表，split()执行为 2D 矩阵获取内维的任务。

**示例:**

## 蟒蛇 3

```
import re

# initializing string
test_str = "[gfg,is],[best,for],[all,geeks]"

# printing original string
print("The original string is : " + str(test_str))

flat_1 = re.findall(r"\[(.+?)\]", test_str)
res = [sub.split(",") for sub in flat_1]

# printing result
print("The type of result : " + str(type(res)))
print("Converted Matrix : " + str(res))
```

**输出:**

> 原始字符串是:[gfg，is]，[best，for]，[all，geeks]
> 
> 结果类型:<class></class>
> 
> 转换矩阵:[[[' gfg '，' is']，['best '，' for']，['all '，' geeks']]

**方法 2 :** 使用 [json.loads()](https://www.geeksforgeeks.org/json-load-in-python/)

在这种情况下，转换到矩阵的任务是使用 JSON 库的 loads()的未构建方法来完成的。

**示例:**

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert String Matrix Representation to Matrix
# Using json.loads()
import json

# initializing string
test_str = '[["gfg", "is"], ["best", "for"], ["all", "geeks"]]'

# printing original string
print("The original string is : " + str(test_str))

# inbuild function performing task of conversion
# notice input
res = json.loads(test_str)

# printing result
print("The type of result : " + str(type(res)))
print("Converted Matrix : " + str(res))
```

**输出:**

> 原字符串为:[[“gfg”，“is”]，[“best”，“for”]，[“all”，“geeks”]]
> 
> 结果类型:<class></class>
> 
> 转换矩阵:[[[' gfg '，' is']，['best '，' for']，['all '，' geeks']]