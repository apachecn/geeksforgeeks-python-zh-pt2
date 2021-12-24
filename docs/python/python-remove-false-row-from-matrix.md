# Python |从矩阵中移除假行

> 原文:[https://www . geesforgeks . org/python-remove-false-row-from-matrix/](https://www.geeksforgeeks.org/python-remove-false-row-from-matrix/)

有时，在处理数据时，尤其是在机器学习领域，我们需要经历大量不完整或空白的数据。我们有时需要删除任何列中不包含值的行。让我们讨论某些方法来删除所有*假值*作为列表列的行。

**方法一:使用列表理解+ `count() + len()`**

我们可以使用列表理解方法来执行这个特殊的任务，与 *len* 和 count 函数的组合一起检查与列表长度相等的相似性元素计数器。

```py
# Python3 code to demonstrate
# removing False rows in matrix 
# using list comprehension + count() + len()

# initializing matrix
test_list = [[1, True, 2], [False, False, 3],
            [False, False, False], [1, 0, 1]]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + count() + len()
# removing False rows in matrix
res = [sub for sub in test_list 
       if sub.count(False) != len(sub)]

# print result
print("The list after removal of False rows : " + str(res))
```

**Output :**

> 原始列表:[[1，True，2]，[False，False，3]，[False，False，False]，[1，0，1]]
> 删除 False 行后的列表:[[1，True，2]，[False，False，3]，[1，0，1]]

**方法 2:使用列表理解+ `set()`**

也可以通过将整行转换为一个集合，然后检查单个值 False 集合是否相等并在找到匹配项时移除来执行此特定任务。

```py
# Python3 code to demonstrate
# removing False rows in matrix 
# using list comprehension + set()

# initializing matrix
test_list = [[1, True, 2], [False, False, 3],
            [False, False, False], [1, 0, 1]]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + set()
# removing False rows in matrix
res = [sub for sub in test_list if set(sub) != {False}]

# print result
print("The list after removal of False rows : " + str(res))
```

**Output :**

> 原始列表:[[1，True，2]，[False，False，3]，[False，False，False]，[1，0，1]]
> 删除 False 行后的列表:[[1，True，2]，[False，False，3]，[1，0，1]]