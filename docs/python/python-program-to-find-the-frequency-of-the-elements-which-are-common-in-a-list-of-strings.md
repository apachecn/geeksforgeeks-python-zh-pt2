# Python 程序查找字符串列表中常见元素的频率

> 原文:[https://www . geeksforgeeks . org/python-program-to-find-the-frequency-of-the-elements-in-common-list-of-strings/](https://www.geeksforgeeks.org/python-program-to-find-the-frequency-of-the-elements-which-are-common-in-a-list-of-strings/)

给定字符串列表。任务是找到在字符串列表中给出的所有字符串中常见的元素的频率。

**例:**

```py
Input : test_list = ["gegek", "gfgk", "kingg"]
Output : {'g': 2, 'k': 1}
Explanation : g occurs twice in all Strings.

Input : test_list = ["gefgek", "gfgk", "kinfgg"]
Output : {'g': 2, 'k': 1, 'f' : 1}
Explanation : f occurs once in all Strings.
```

**方法:使用 reduce() + lambda + Counter()**

上述功能的组合可以用来解决这个问题。在这种情况下，我们使用 Counter()执行计数的关键角色，并且使用[λ](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)结合 [reduce()](https://www.geeksforgeeks.org/reduce-in-python/) 分别对所有字符串执行逻辑的交集和扩展。

## python 3

```py
# Python3 code to demonstrate working of
# Strings list intersection
# Using reduce() + lambda + Counter()
from functools import reduce
from collections import Counter

# initializing list
test_list = ["geek", "gfgk", "king"]

# printing original list
print("The original list is : " + str(test_list))

# using & operator to perform intersection
res = reduce(lambda a, b: a & b, (Counter(ele) for ele in test_list[1:]),
             Counter(test_list[0]))

# printing result
print("String intersection and frequency : " + str(dict(res)))
```

**输出**

```py
The original list is : ['geek', 'gfgk', 'king']
String intersection and frequency : {'g': 1, 'k': 1}
```