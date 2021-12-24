# Python |合并连续数字字符串

> 原文:[https://www . geesforgeks . org/python-merge-continuous-digits-strings/](https://www.geeksforgeeks.org/python-merge-consecutive-digits-strings/)

有时，在处理数据时，我们可能会遇到需要合并数字的问题。这是一个比较简单的问题。但是一旦我们需要合并某些元素，比如过于连续的数字，事情就变得复杂了。让我们讨论执行这项任务的某些方法。
**方法#1:使用列表理解+ groupby() + isdigit()**
以上功能的组合可以用来执行这个任务。在这种情况下，我们首先将所有连续的数字分组，然后执行连接。

## 蟒蛇 3

```
# Python3 code to demonstrate
# Merge Consecutive digits Strings
# using list comprehension + groupby() + isdigit()
from itertools import groupby

# Initializing list
test_list = ['gfg', '1', '2', 'is', '5', 'best', '6', '7']

# printing original list
print("The original list is : " + str(test_list))

# Merge Consecutive digits Strings
# using list comprehension + groupby() + isdigit()
res = [sub for i, j in groupby(test_list, str.isdigit) for sub in ([''.join(j)] if i else j)]

# printing result
print ("List after digit merge : " + str(res))
```

**Output : **

```
The original list is : ['gfg', '1', '2', 'is', '5', 'best', '6', '7']
List after digit merge : ['gfg', '12', 'is', '5', 'best', '67']
```

**方法 2:使用 regex + join()**
以上函数的组合也可以用来处理这个。在本文中，我们使用 regex 函数找到数字，并使用 join()执行合并。仅适用于单个字符。

## 蟒蛇 3

```
# Python3 code to demonstrate
# Merge Consecutive digits Strings
# using regex() + join()
import re

# Initializing list
test_list = ['g', '1', '2', 'i', '5', 'b', '6', '7']

# printing original list
print("The original list is : " + str(test_list))

# Merge Consecutive digits Strings
# using regex() + join()
res = re.findall('\d+|.', ''.join(test_list))

# printing result
print ("List after digit merge : " + str(res))
```

**Output : **

```
The original list is : ['g', '1', '2', 'i', '5', 'b', '6', '7']
List after digit merge : ['g', '12', 'i', '5', 'b', '67']
```