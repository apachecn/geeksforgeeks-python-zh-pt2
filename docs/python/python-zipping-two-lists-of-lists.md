# 如何在 Python 中压缩两个列表列表？

> 原文:[https://www . geesforgeks . org/python-zipping-双列表列表/](https://www.geeksforgeeks.org/python-zipping-two-lists-of-lists/)

普通的 zip 函数允许我们在一个容器中聚合值。但是有时候，我们有一个要求，我们需要有多个列表和包含列表作为索引元素，我们需要将它们合并/压缩在一起。这是一个非常罕见的问题，但解决它仍然很方便。让我们讨论设计解决方案的某些方法。

**方法#1:使用`map() + __add__`**
这个问题可以用带加法运算的地图函数来解决。map 函数执行与 zip 函数类似的功能，在这种情况下可以帮助找到解决方案。

```py
# Python3 code to demonstrate 
# zipping lists of lists 
# using map() + __add__

# initializing lists
test_list1 = [[1, 3], [4, 5], [5, 6]]
test_list2 = [[7, 9], [3, 2], [3, 10]]

# printing original lists
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " + str(test_list2))

# using map() + __add__
# zipping lists of lists 
res = list(map(list.__add__, test_list1, test_list2))

# printing result 
print ("The modified zipped list is : " +  str(res))
```

**输出:**

```py
The original list 1 is : [[1, 3], [4, 5], [5, 6]]
The original list 2 is : [[7, 9], [3, 2], [3, 10]]
The modified zipped list is : [[1, 3, 7, 9], [4, 5, 3, 2], [5, 6, 3, 10]]

```

**方法 2:使用`itertools.chain() + zip()`**
这两个功能的组合可以用来执行这个特定的任务。链函数可用于执行列表间聚合，列表内聚合由 zip 函数完成。

```py
# Python3 code to demonstrate 
# zipping lists of lists 
# using map() + __add__
import itertools

# initializing lists
test_list1 = [[1, 3], [4, 5], [5, 6]]
test_list2 = [[7, 9], [3, 2], [3, 10]]

# printing original lists
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " + str(test_list2))

# using map() + __add__
# zipping lists of lists 
res = [list(itertools.chain(*i)) 
       for i in zip(test_list1, test_list2)]

# printing result 
print ("The modified zipped list is : " +  str(res))
```

**输出:**

```py
The original list 1 is : [[1, 3], [4, 5], [5, 6]]
The original list 2 is : [[7, 9], [3, 2], [3, 10]]
The modified zipped list is : [[1, 3, 7, 9], [4, 5, 3, 2], [5, 6, 3, 10]]

```