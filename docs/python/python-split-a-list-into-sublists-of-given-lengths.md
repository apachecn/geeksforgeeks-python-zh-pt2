# Python |将列表拆分成给定长度的子列表

> 原文:[https://www . geesforgeks . org/python-将列表拆分为给定长度的子列表/](https://www.geeksforgeeks.org/python-split-a-list-into-sublists-of-given-lengths/)

将列表拆分成子列表的问题非常普遍，但是在给定长度的子列表中进行拆分并不常见。给定列表和长度列表，任务是将列表拆分成给定长度的子列表。

**示例:**

```py
Input : Input = [1, 2, 3, 4, 5, 6, 7]
        length_to_split = [2, 1, 3, 1]

Output: [[1, 2], [3], [4, 5, 6], [7]]

```

**方法#1:** 使用`islice`将列表拆分成给定长度的子列表，是最优雅的方式。

```py
# Python code to split a list
# into sublists of given length.

from itertools import islice

# Input list initialization
Input = [1, 2, 3, 4, 5, 6, 7]

# list of length in which we have to split
length_to_split = [2, 1, 3, 1]

# Using islice
Inputt = iter(Input)
Output = [list(islice(Inputt, elem))
          for elem in length_to_split]

# Printing Output
print("Initial list is:", Input)
print("Split length list: ", length_to_split)
print("List after splitting", Output)
```

**Output:**

```py
Initial list is: [1, 2, 3, 4, 5, 6, 7]
Split length list:  [2, 1, 3, 1]
List after splitting [[1, 2], [3], [4, 5, 6], [7]]

```

**方法 2:** 使用`zip`是将列表拆分为给定长度的子列表的另一种方法。

```py
# Python code to split a list into
# sublists of given length.
from itertools import accumulate

# Input list initialization
Input = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

# list of length in which we have to split
length_to_split = [2, 2, 3, 3]

# Using islice
Output = [Input[x - y: x] for x, y in zip(
          accumulate(length_to_split), length_to_split)]

# Printing Output
print("Initial list is:", Input)
print("Split length list: ", length_to_split)
print("List after splitting", Output)
```

**Output:**

```py
Initial list is: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
Split length list:  [2, 2, 3, 3]
List after splitting [[1, 2], [3, 4], [5, 6, 7], [8, 9, 10]]

```