# Python |合并子列表元素

> 原文:[https://www . geesforgeks . org/python-merge-elements-of-sublist/](https://www.geeksforgeeks.org/python-merge-elements-of-sublists/)

给定两个包含子列表的列表，任务是将两个列表的子列表的元素合并到一个列表中。

**示例:**

```py
Input:
list1 = [[1, 20, 30],
         [40, 29, 72], 
         [119, 123, 115]]

list2 = [[29, 57, 64, 22],
         [33, 66, 88, 15], 
         [121, 100, 15, 117]]

Output: [[1, 20, 30, 29, 57, 64, 22],
         [40, 29, 72, 33, 66, 88, 15],
         [119, 123, 115, 121, 100, 15, 117]]

```

**方法#1:使用`Map + lambda`**

```py
# Python code to merge elements of sublists

# Initialisation of first list
list1 = [[1, 20, 30],
         [40, 29, 72],
         [119, 123, 115]]

# Initialisation of second list
list2 = [[29, 57, 64, 22],
         [33, 66, 88, 15],
         [121, 100, 15, 117]]

# Using map + lambda to merge lists
Output = list(map(lambda x, y:x + y, list1, list2))

# Printing output
print(Output)
```

**Output:**

```py
[[1, 20, 30, 29, 57, 64, 22],
 [40, 29, 72, 33, 66, 88, 15], 
 [119, 123, 115, 121, 100, 15, 117]]

```

**方法 2:使用`Zip()`**

```py
# Python code to merge elements of sublists

# Initialisation of first list
list1 = [[1, 20, 30],
         [40, 29, 72],
         [119, 123, 115]]

# Initialisation of second list
list2 = [[29, 57, 64, 22],
         [33, 66, 88, 15],
         [121, 100, 15, 117]]

# Using zip to merge lists
Output = [x + y for x, y in zip(list1, list2)]

# Printing output
print(Output)
```

**Output:**

```py
[[1, 20, 30, 29, 57, 64, 22],
 [40, 29, 72, 33, 66, 88, 15],
 [119, 123, 115, 121, 100, 15, 117]]

```

**方法三:使用`starmap()` `concat()`**

```py
# Python code to merge elements of sublists

from operator import concat
from itertools import starmap

# Initialisation of first list
list1 = [[1, 20, 30],
         [40, 29, 72],
         [119, 123, 115]]

# Initialisation of second list
list2 = [[29, 57, 64, 22],
         [33, 66, 88, 15], 
         [121, 100, 15, 117]]

# Using starmap() and concat to merge list
Output = list(starmap(concat, zip(list1, list2)))

# Printing output
print(Output)
```

**Output:**

```py
[[1, 20, 30, 29, 57, 64, 22],
 [40, 29, 72, 33, 66, 88, 15],
 [119, 123, 115, 121, 100, 15, 117]]

```