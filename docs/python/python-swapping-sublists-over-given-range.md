# Python |在给定范围内交换子列表

> 原文:[https://www . geesforgeks . org/python-交换-子列表-超出给定范围/](https://www.geeksforgeeks.org/python-swapping-sublists-over-given-range/)

交换单个号码的问题可以扩展到拥有列表并在整个范围内执行交换的问题，这在一段时间内可能是有用的。这在各种领域的任何类型的数据操作中都有其应用。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表切片和交换**
列表的交换方式与 python 中变量的交换方式相同，但不同的是，我们传递的不是变量，而是要交换的切片列表。

```
# Python3 code to demonstrate
# swapping sublist
# using list swapping and slicing

# initializing list 
test_list = [1, 4, 5, 8, 3, 10, 6, 7, 11, 14, 15, 2]

# printing the original list
print ("The original list is : " + str(test_list))

# using list swapping and slicing 
# swapping sublist
test_list[1 : 3], test_list[6 : 8] = test_list[6 : 8], test_list[1 : 3]

# printing result
print ("The list after sublist swapping : " + str(test_list))
```

**Output:**

```
The original list is : [1, 4, 5, 8, 3, 10, 6, 7, 11, 14, 15, 2]
The list after sublist swapping : [1, 6, 7, 8, 3, 10, 4, 5, 11, 14, 15, 2]

```

**方法 2:使用`slice() + itertools.chain.from_iterable()`**
切片函数可以执行切片功能，从列表中提取子列表，from_iterable 函数有助于执行交换功能。

```
# Python3 code to demonstrate swapping 
# sublist using slice() + itertools.chain.from_iterable()
import itertools

# initializing list 
test_list = [1, 4, 5, 8, 3, 10, 6, 7, 11, 14, 15, 2]

# printing the original list
print ("The original list is : " + str(test_list))

# using slice() + itertools.chain.from_iterable()
# swapping sublist
slice_1 = test_list[1 : 3]
slice_2 = test_list[6 : 8]
slice_temp = [slice(0, 1), slice(6, 8), slice(3, 6),
              slice(1, 3), slice(8, len(test_list))]

res = list(itertools.chain.from_iterable([test_list[i]
                                for i in slice_temp]))

# printing result
print ("The list after sublist swapping : " + str(res))
```

**Output:**

```
The original list is : [1, 4, 5, 8, 3, 10, 6, 7, 11, 14, 15, 2]
The list after sublist swapping : [1, 6, 7, 8, 3, 10, 4, 5, 11, 14, 15, 2]

```