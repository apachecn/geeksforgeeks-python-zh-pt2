# Python |移除元组矩阵中相似的元素行

> 原文:[https://www . geesforgeks . org/python-remove-相似元素-元组中的行-矩阵/](https://www.geeksforgeeks.org/python-remove-similar-element-rows-in-tuple-matrix/)

有时，在处理数据时，我们会遇到一个问题，即我们需要从元组矩阵中移除元素，条件是如果元组矩阵的行中的所有元素都相同。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `all()`**
该任务可以使用以上功能的组合来执行。在这种情况下，我们使用列表理解遍历所有行，并在`all()`的帮助下移除行列中与初始元素匹配的所有元素。

```
# Python3 code to demonstrate working of
# Remove similar element rows in tuple Matrix
# using list comprehension + all()

# initialize tuple
test_tup = ((1, 3, 5), (2, 2, 2),
            (9, 10, 10), (4, 4, 4))

# printing original tuple
print("The original tuple : " + str(test_tup))

# Remove similar element rows in tuple Matrix
# using list comprehension + all()
res = tuple(ele for ele in test_tup if not all(sub == ele[0] for sub in ele))

# printing result
print("The tuple after removal of like-element rows : " + str(res))
```

**Output :**

```
The original tuple : ((1, 3, 5), (2, 2, 2), (9, 10, 10), (4, 4, 4))
The tuple after removal of like-element rows : ((1, 3, 5), (9, 10, 10))

```