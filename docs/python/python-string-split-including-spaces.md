# Python |包含空格的字符串拆分

> 原文:[https://www . geesforgeks . org/python-string-split-include-spaces/](https://www.geeksforgeeks.org/python-string-split-including-spaces/)

在使用 python 字符串时，列表拆分的问题和应用程序是很常见的。在用例中，空格通常会被忽略。但是有时，我们可能不需要省略空格，而是将它们包含在我们的编程输出中。让我们讨论一下解决这个问题的某些方法。

**方法一:使用`split()` +列表理解**

这种操作可以使用拆分功能和列表理解来执行。不省略空格的主要区别在于，我们特别在每个元素之后添加了在过程中可能省略的空格。

```py
# Python3 code to demonstrate
# String Split including spaces
# using list comprehension + split()

# initializing string
test_string = "GfG is Best"

# printing original string
print("The original string : " + str(test_string))

# using list comprehension + split()
# String Split including spaces
res = [i for j in test_string.split() for i in (j, ' ')][:-1]

# print result
print("The list without omitting spaces : " + str(res))
```

**Output :**

```py
The original string : GfG is Best
The list without omitting spaces : ['GfG', ' ', 'is', ' ', 'Best']

```

**方法 2:使用`zip() + chain() + cycle()`**

这个特殊的任务也可以使用上述 3 个功能的组合来执行。zip 函数可用于绑定逻辑，chain 和 cycle 函数执行在适当位置插入空间的任务。

```py
# Python3 code to demonstrate
# String Split including spaces
# using zip() + chain() + cycle()
from itertools import chain, cycle

# initializing string
test_string = "GfG is Best"

# printing original string
print("The original string : " + str(test_string))

# using zip() + chain() + cycle()
# String Split including spaces
res = list(chain(*zip(test_string.split(), cycle(' '))))[:-1]

# print result
print("The list without omitting spaces : " + str(res))
```

**Output :**

```py
The original string : GfG is Best
The list without omitting spaces : ['GfG', ' ', 'is', ' ', 'Best']

```