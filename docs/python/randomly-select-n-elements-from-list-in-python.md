# 在 Python 中从列表中随机选择 n 个元素

> 原文:[https://www . geesforgeks . org/从 python 列表中随机选择 n 个元素/](https://www.geeksforgeeks.org/randomly-select-n-elements-from-list-in-python/)

在本文中，我们将讨论如何在 Python 中从列表中随机选择 n 个元素。在进入方法之前，让我们讨论一下我们将在方法中使用的**随机**模块。
**随机模块:**
随机模块是 Python 中预定义的模块，包含返回随机值的方法。当我们想要生成随机值时，这个模块很有用。Random 模块的方法有:-
`seed()``getstate()``choice()``sample()`等。

让我们讨论实现这一点的不同方法。
**进场 1 :** 采用`[sample()](https://www.geeksforgeeks.org/python-random-sample-function/)`法。`sample()`方法用于从给定序列返回所需的项目列表。此方法不允许序列中有重复的元素。

```py
# importing random module
import random

# declaring list
list = [2, 2, 4, 6, 6, 8]

# initializing the value of n
n = 4

# printing n elements from list
print(random.sample(list, n))
```

**输出:**

```py
[8, 6, 6, 4]

```

**方法 2 :** 使用`[choice()](https://www.geeksforgeeks.org/python-numbers-choice-function/)`方法。`choice()`方法用于从给定序列中返回一个随机数。序列可以是列表或元组。这将从可用数据中返回一个值，该值考虑序列(列表)中的重复值。

```py
# importing random module
import random

# declaring list
list = [2, 2, 4, 6, 6, 8]

# initializing the value of n
n = 4

# traversing and printing random elements
for i in range(n):

    # end = " " so that we get output in single line
    print(random.choice(list), end = " ")
```

**输出:**

```py
8 2 4 6 

```