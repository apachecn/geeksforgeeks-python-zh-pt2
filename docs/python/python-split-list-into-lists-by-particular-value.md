# Python |按特定值将列表拆分成列表

> 原文:[https://www . geesforgeks . org/python-按特定值将列表拆分为列表/](https://www.geeksforgeeks.org/python-split-list-into-lists-by-particular-value/)

列表拆分是当今非常常见的实用程序，并且可以有许多相同的应用程序和用例。伴随着这些变化的总是变化。一个这样的变化可以是按特定值分割列表。让我们讨论一种可以执行列表拆分的特定方式。

**方法:使用列表理解+ `zip() + slicing + enumerate()`**

这个问题可以分两个部分来解决，第一部分我们得到索引列表，通过这个列表，我们可以使用枚举函数来执行拆分。然后我们可以根据索引使用 zip 和列表切片来连接这些值。

```py
# Python3 code to demonstrate
# Split list into lists by particular value
# Using list comprehension + zip() + slicing + enumerate()

# initializing list
test_list = [1, 4, 5, 6, 4, 5, 6, 5, 4]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + zip() + slicing + enumerate()
# Split list into lists by particular value
size = len(test_list)
idx_list = [idx + 1 for idx, val in
            enumerate(test_list) if val == 5]

res = [test_list[i: j] for i, j in
        zip([0] + idx_list, idx_list + 
        ([size] if idx_list[-1] != size else []))]

# print result
print("The list after splitting by a value : " + str(res))
```

**输出:**

```py
The original list : [1, 4, 5, 6, 4, 5, 6, 5, 4]
The list after splitting by a value : [[1, 4, 5], [6, 4, 5], [6, 5], [4]]

```