# Python–混合长度 2D 列表中的最大列值

> 原文:[https://www . geesforgeks . org/python-最大列值-混合长度-2d-list/](https://www.geeksforgeeks.org/python-maximum-column-values-in-mixed-length-2d-list/)

与传统的 C 类型矩阵不同，通常的列表可以允许可变长度的嵌套列表，当我们要求其列最大化时，不均匀的行长度可能会导致该元素中的某些元素缺失，如果处理不正确，可能会引发异常。让我们讨论以无错误的方式解决这个问题的某些方法。

**方法#1:使用`max() + filter() + map()` +列表理解**
以上三个函数结合列表理解可以帮助我们执行这个特定的任务，max 函数有助于执行最大化，filter 允许我们检查当前元素，所有行都使用 map 函数进行组合。仅适用于 python 2。

```py
# Python code to demonstrate 
# Maximum column values mixed length 2D List
# using max() + filter() + map() + list comprehension

# initializing list of lists
test_list = [[1, 5, 3], [4], [9, 8]]

# printing original list 
print ("The original list is : " + str(test_list))

# using max() + filter() + map() + list comprehension
# Maximum column values mixed length 2D List
res = [max(filter(None, j)) for j in map(None, *test_list)]

# printing result
print ("The maximization of columns is : " + str(res))
```

**Output :**

```py
The original list is : [[1, 5, 3], [4], [9, 8]]
The maximization of columns is : [9, 8, 3]

```