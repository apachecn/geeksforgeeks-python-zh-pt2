# Python 程序，用于从给定列表中创建元组列表，该列表在每个元组中都有编号及其立方体

> 原文:[https://www . geeksforgeeks . org/python-program-to-create-list-of-tuples-from-给定列表-每个 tuple 中有数字及其立方/](https://www.geeksforgeeks.org/python-program-to-create-a-list-of-tuples-from-given-list-having-number-and-its-cube-in-each-tuple/)

给定列表的数字列表，编写一个 Python 程序来创建一个元组列表，其中第一个元素作为数字，第二个元素作为数字的立方。

**例:**

```py
Input: list = [1, 2, 3]
Output: [(1, 1), (2, 8), (3, 27)]

Input: list = [9, 5, 6]
Output: [(9, 729), (5, 125), (6, 216)]
```

我们可以使用列表理解来创建元组列表。第一个元素只是一个元素，第二个元素是这个数的立方。

下面是 Python 实现:

```py
# Python program to create a list of tuples
# from given list having number and
# its cube in each tuple

# creating a list
list1 = [1, 2, 5, 6]

# using list comprehension to iterate each
# values in list and create a tuple as specified
res = [(val, pow(val, 3)) for val in list1]

# print the result
print(res)
```

**输出:**

```py
[(1, 1), (2, 8), (5, 125), (6, 216)]
```