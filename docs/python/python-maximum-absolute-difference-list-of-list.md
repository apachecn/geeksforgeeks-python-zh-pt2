# Python |列表最大绝对差列表

> 原文:[https://www . geesforgeks . org/python-最大绝对差异-列表列表/](https://www.geeksforgeeks.org/python-maximum-absolute-difference-list-of-list/)

这篇特别的文章集中在一个在竞争和日常编程中都有用的问题上。有时，当与下一个列表进行比较时，我们需要得到相似索引之间的最大差异。返回该索引中相似元素之间的最大差异。让我们讨论执行这项任务的某些方法。

**方法一:使用`max() + abs() + zip()` +列表理解**
这个特殊问题也可以通过以上 4 个操作的组合来解决。这里，zip 函数完成了配对列表和配对相似索引的双重任务，通过`abs` 函数计算差异，然后使用`max` 函数找到最大值，所有这些都受列表理解的限制。

```py
# Python3 code to demonstrate
# Maximum absolute difference list of list
# using max() + abs() + zip() + list comprehension

# initializing list 
test_list = [[3, 4, 5], [4, 6, 8], [1, 9, 2], [3, 7, 10]]

# printing original list 
print("The original list : " + str(test_list))

# using max() + abs() + zip() + list comprehension
# Maximum absolute difference list of list
res = [max(abs(i - j) for i, j in zip(*ele))
       for ele in zip(test_list, test_list[1:])]

# print result
print("The maximum difference sublist : " + str(res))
```

**Output :**

```py
The original list : [[3, 4, 5], [4, 6, 8], [1, 9, 2], [3, 7, 10]]
The maximum difference sublist : [3, 6, 8]

```