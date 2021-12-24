# Python–列表元素组合中可能的最小整数

> 原文:[https://www . geeksforgeeks . org/python-最小可能整数列表元素组合/](https://www.geeksforgeeks.org/python-smallest-integer-possible-from-combination-of-list-elements/)

给定一个整数列表，任务是从列表元素的组合中获得可能的最小整数。从竞争的角度来看，这是一个至关重要的问题，本文讨论了用 Python 解决这个问题的各种方法。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`sorted()`+λ**
以上功能的组合可以用来执行此任务。sorted 函数执行转换为字符串的列表索引的排序，lambda 函数处理转换和迭代操作。

```
# Python code to demonstrate 
# Smallest number from list
# using sorted() + lambda
import functools

# initializing list 
test_list = [23, 65, 98, 3, 4]

# printing original list
print ("The original list is : " + str(test_list))

# lambda for custom operation
custom = lambda i, j: -1 if str(j) + str(i) > str(i) + str(j) else 1

# using sorted() + custom function
# Smallest number from list 
res = sorted(test_list, key = functools.cmp_to_key(custom))

# printing result 
print ("The smallest possible number : " + "".join(map(str, res)))
```

**Output :**

```
The original list is : [23, 65, 98, 3, 4]
The smallest possible number : 23346598

```