# Python–相似索引元素矩阵

> 原文:[https://www . geesforgeks . org/python-相似-索引-元素-矩阵/](https://www.geeksforgeeks.org/python-similar-index-elements-matrix/)

有时，在处理数据时，我们可能会遇到这样的问题，即我们需要从列表元素中垂直地而不是水平地构建矩阵。这种应用可以出现在数据科学领域，我们需要从几个列表中构建矩阵。让我们讨论执行这项任务的某些方法。

**方法#1:使用`zip() + map()`**
上述功能的组合可用于执行该任务。在这种情况下，我们使用 zip()和 map()对列表进行配对。矩阵的构建是从配对的列表开始的。

```py
# Python3 code to demonstrate 
# Similar index elements Matrix
# using zip() + map()

# Initializing lists
test_list1 = [3, 4, 5]
test_list2 = [1, 2, 6]
test_list3 = [7, 9, 8]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))
print("The original list 3 is : " + str(test_list3))

# Similar index elements Matrix
# using zip() + map()
res = []
res += map(list, zip(test_list1, test_list2, test_list3))

# printing result 
print ("The matrix after cummulation is : " + str(res))
```

**Output :**

```py
The original list 1 is : [3, 4, 5]
The original list 2 is : [1, 2, 6]
The original list 3 is : [7, 9, 8]
The matrix after cummulation is : [[3, 1, 7], [4, 2, 9], [5, 6, 8]]

```