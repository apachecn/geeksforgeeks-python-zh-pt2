# Python |按数字总和对数字列表进行排序

> 原文:[https://www . geesforgeks . org/python-按数字总和对数字列表进行排序/](https://www.geeksforgeeks.org/python-sort-list-of-numbers-by-sum-of-their-digits/)

给定一个非负数的列表，任务是根据这些整数的数字总和对它们进行排序。

**示例:**

```py
Input : [12, 10, 106, 31, 15]
Output : [10, 12, 31, 15, 106]

Input : [1111, 19, 29, 11, 12, 9]
Output : [11, 12, 1111, 9, 19, 29]

```

让我们讨论几个完成这项任务的 Pythonic 方法。

**方法#1 :** 列表理解

使用 for 循环将列表中的每个元素转换为不同的列表，并以其数字作为元素。现在，使用带有上述功能的排序功能作为*键*。

```py
# Python3 Program to Sort list of
# integers according to sum of digits

def sortList(lst):
    digits = [int(digit) for digit in str(lst) ]
    return sum(digits)

# Driver Code
lst = [12, 10, 106, 31, 15]
print(sorted(lst, key = sortList))
```

**Output:**

```py
[10, 12, 31, 15, 106]

```

**方法 2 :** 使用`map()`

这种方法与上述方法类似，只是略有不同，我们使用`map()`将列表的每个元素转换为不同的列表，以其数字作为元素，然后遵循与上述类似的方法。

```py
# Python3 Program to Sort list of
# integers according to sum of digits

def sortList(num):
    return sum(map(int, str(num)))

# Driver Code
lst = [12, 10, 106, 31, 15]
result = sorted(lst, key = sortList)
print(result)
```

**Output:**

```py
[10, 12, 31, 15, 106]

```

除了上述方法之外，还有一种单一的替代方法。

```py
def sortList(lst):
    return sorted(lst, key = lambda x:(sum(map(int, str(x)))))
```