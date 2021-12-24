# Python |打印所有子列表中的公共元素

> 原文:[https://www . geesforgeks . org/python-print-the-common-elements-in-all-sublist/](https://www.geeksforgeeks.org/python-print-the-common-elements-in-all-sublists/)

给定一个列表列表，任务是找到所有子列表中常见的元素。

有多种方法可以完成这项任务。让我们逐一讨论这些方法。

**方法#1:** 使用器械包

```py
# Python code to find duplicate element in all 
# sublist from list of list

# List of list initialization
Input = [ [10, 20, 30, 40],
          [30, 40, 60, 70],
          [20, 30, 40, 60, 70],
          [30, 40, 80, 90], ]

Output = set(Input[0])
for l in Input[1:]:
    Output &= set(l)

# Converting to list
Output = list(Output)

# Printing answer
print(Output)
```

**Output:**

```py
[40, 30]

```

**方法 2:** 使用`reduce` 和`map`

```py
# Python code to find duplicate element in all 
# sublist from list of list
import operator
from functools import reduce

# List of list initialization
Input = [ [10, 20, 30, 40],
          [30, 40, 60, 70],
          [20, 30, 40, 60, 70], 
          [30, 40, 80, 90], ]

# using reduce and map
out = reduce(operator.iand, map(set, Input))

# Converting into list
out = list(out)

# Printing output
print(out)
```

**Output:**

```py
[40, 30]

```

**方法 3:** 使用 `set.intersection`

```py
# Python code to find duplicate element in all 
# sublist from list of list

# importing reduce 
from functools import reduce

# function for set intersection
def func(a, b):
    return list(set(a).intersection(set(b)))

# List of list initialization
Input = [ [10, 20, 30, 40],
          [30, 40, 60, 70],
          [20, 30, 40, 60, 70], 
          [30, 40, 80, 90], ]

# using reduce and set.intersection
out = reduce(func, Input)

# Printing output
print(out)
```

**Output:**

```py
[40, 30]

```