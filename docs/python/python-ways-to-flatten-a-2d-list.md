# Python |展平 2D 列表的方法

> 原文:[https://www . geesforgeks . org/python-展平方式-a-2d-list/](https://www.geeksforgeeks.org/python-ways-to-flatten-a-2d-list/)

给定一个 2D 列表，编写一个 Python 程序将给定的列表转换成一个扁平列表。

**方法#1:使用 chain . iterable()**

## python 3

```
# Python code to demonstrate
# converting 2d list into 1d list
# using chain.from_iterables

# import chain
from itertools import chain

ini_list = [[1, 2, 3],
            [3, 6, 7],
            [7, 5, 4]]

# printing initial list
print ("initial list ", str(ini_list))

# converting 2d list into 1d
# using chain.from_iterables
flatten_list = list(chain.from_iterable(ini_list))

# printing flatten_list
print ("final_result", str(flatten_list))
```

**输出:**

```
initial list  [[1, 2, 3], [3, 6, 7], [7, 5, 4]]
final_result [1, 2, 3, 3, 6, 7, 7, 5, 4]
```