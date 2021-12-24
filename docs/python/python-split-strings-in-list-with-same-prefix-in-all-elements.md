# Python |拆分列表中所有元素前缀相同的字符串

> 原文:[https://www . geeksforgeeks . org/python-列表中所有元素前缀相同的拆分字符串/](https://www.geeksforgeeks.org/python-split-strings-in-list-with-same-prefix-in-all-elements/)

有时，我们会遇到这样一个问题，即我们有一个字符串列表，在其前缀或后缀或统一指定的位置有一些垃圾/不需要的字母，即这扩展到列表中的所有字符串。让我们讨论一下解决这个问题的某些方法。

**方法一:使用列表理解+列表切片**

这个任务可以使用列表理解和列表切片来执行。列表切片可用于删除不需要的字母，列表理解可用于将逻辑扩展到整个字符串。

```
# Python3 code to demonstrate
# Split strings in list
# Using list comprehension + list slicing

# initializing list
test_list = ['Rs.25', 'Rs.100', 'Rs.143', 'Rs.12', 'Rs.4010']

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + list slicing
# Split strings in list
res = [sub[3:] for sub in test_list]

# print result
print("The list after string slicing : " + str(res))
```

**Output :**

```
The original list : ['Rs.25', 'Rs.100', 'Rs.143', 'Rs.12', 'Rs.4010']
The list after string slicing : ['25', '100', '143', '12', '4010']

```

**方法 2:使用`map()` +切片+λ**

这个特殊的任务也可以使用 map 函数来执行。对每个字符串执行相同操作的任务由 lambda 函数和 map 函数处理。

```
# Python3 code to demonstrate
# Split strings in list
# Using map() + slicing + lambda

# initializing list
test_list = ['Rs.25', 'Rs.100', 'Rs.143', 'Rs.12', 'Rs.4010']

# printing original list
print("The original list : " + str(test_list))

# using map() + slicing + lambda
# Split strings in list
res = list(map(lambda sub: sub[3:], test_list))

# print result
print("The list after string slicing : " + str(res))
```

**Output :**

```
The original list : ['Rs.25', 'Rs.100', 'Rs.143', 'Rs.12', 'Rs.4010']
The list after string slicing : ['25', '100', '143', '12', '4010']

```