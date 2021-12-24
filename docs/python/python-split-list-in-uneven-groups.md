# Python |非均匀分组拆分列表

> 原文:[https://www . geesforgeks . org/python-拆分-非均匀分组列表/](https://www.geeksforgeeks.org/python-split-list-in-uneven-groups/)

有时，在使用 python 时，我们会遇到拆分列表的问题。这个问题很常见，也有很多变化。从长远来看，拥有流行变化的解决方案证明是好的。让我们讨论一些方法来将列表拆分成由其他列表定义的不均匀组。

**方法:使用`itertools.islice()` +列表理解**
以上功能的组合可用于执行此任务。在这种情况下，`islice()`用于执行切片列表的核心任务，列表理解用于执行将逻辑和迭代绑定在一起的任务。容器被转换为迭代器，以便更快地迭代。

```
# Python3 code to demonstrate working of
# Split list in uneven groups
# using itertools.islice() + list comprehension
from itertools import islice

# initialize list
test_list = [1, 4, 5, 7, 6, 5, 4, 2, 10]

# initialize split list
split_list = [3, 4, 2]

# printing original list
print("The original list is : " + str(test_list))

# printing split list 
print("The split list is : " + str(split_list))

# Split list in uneven groups
# using itertools.islice() + list comprehension
temp = iter(test_list)
res = [list(islice(temp, 0, ele)) for ele in split_list]

# printing result
print("The resultant split list is : " + str(res))
```

**Output :**

```
The original list is : [1, 4, 5, 7, 6, 5, 4, 2, 10]
The split list is : [3, 4, 2]
The resultant split list is : [[1, 4, 5], [7, 6, 5, 4], [2, 10]]

```