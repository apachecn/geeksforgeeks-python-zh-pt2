# Python |在矩阵中搜索元素

> 原文:[https://www . geesforgeks . org/python-search-elements-in-a-matrix/](https://www.geeksforgeeks.org/python-search-elements-in-a-matrix/)

Python 支持列表作为其列表元素，因此可以形成矩阵。有时我们可能会有一个实用程序，我们需要在列表(即矩阵)列表中执行搜索，这在所有编码领域都很常见。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`any()` +列表理解**
可以使用任意函数执行 if 条件的任务，并且可以使用列表理解计算嵌套列表中每个元素的检查。

```py
# Python3 code to demonstrate
# Search in Matrix
# using any() + list comprehension

# initializing list
test_list = [[4, 5, 6],
             [10, 2, 13],
             [1, 11, 18]]

# printing original list 
print("The original list : " + str(test_list))

# using any() + list comprehension
# to Search in Matrix
res = any(13 in sub for sub in test_list)

# printing result
print("Is 13 present in Matrix ? : " + str(res))
```

**Output :**

```py
The original list : [[4, 5, 6], [10, 2, 13], [1, 11, 18]]
Is 13 present in Matrix ? : True

```