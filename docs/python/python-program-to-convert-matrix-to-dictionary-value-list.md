# 将矩阵转换为字典值列表的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序-转换-矩阵-字典-值-列表/](https://www.geeksforgeeks.org/python-program-to-convert-matrix-to-dictionary-value-list/)

给定 Matrix，任务是编写一个 Python 程序，将每个列的值映射为另一个列表中的自定义键。

> **输入:** test_list = [[4，5，6]，[1，3，5]，[3，8，1]，[10，3，5]]，map_list = [4，5，6]
> 
> **输出:** {4: [4，1，3，10]，5: [5，3，8，3]，6: [6，5，1，5]}
> 
> **说明:** 4 映射了列表的所有第 0 个索引，4，1，3，10。
> 
> **输入:** test_list = [[4，5，6]，[1，3，5]，[3，8，1]]，map_list = [4，5，6]
> 
> **输出:** {4: [4，1，3]，5: [5，3，8]，6: [6，5，1]}
> 
> **说明:** 4 映射了列表的所有第 0 个索引，4，1，3。

**方法一:使用** [**词典理解**](https://www.geeksforgeeks.org/python-dictionary-comprehension/)**+**[**zip()**](https://www.geeksforgeeks.org/zip-in-python/)

在这种情况下，列与自定义列表索引元素的映射是使用 zip()完成的，字典理解是将提取的键分配给映射值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Convert Matrix to Dictionary Value List
# Using dictionary comprehension + zip()
from collections import defaultdict

# initializing list
test_list = [[4, 5, 6], [1, 3, 5], [3, 8, 1], [10, 3, 5]]

# printing original list
print("The original list is : " + str(test_list))

# initializing map list 
map_list = [4, 5, 6]

# mapping column using zip(), dictionary comprehension for key
# converts to list of dictionary
temp = [{key : val for key, 
         val in zip(map_list, idx)} for idx in test_list]

# convert to dictionary value list 
res = defaultdict(list) 
{res[key].append(sub[key]) for sub in temp for key in sub}

# printing result
print("Converted Dictionary : " + str(dict(res)))
```

**输出:**

> 原来的名单是:[[4，5，6]，[1，3，5]，[3，8，1]，[10，3，5]]
> 
> 转换的字典:{4: [4，1，3，10]，5: [5，3，8，3]，6: [6，5，1，5]}

**方法二:使用**[**dict()**](https://www.geeksforgeeks.org/zip-in-python/)**+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)**+**[**zip()**](https://www.geeksforgeeks.org/zip-in-python/)

在这种情况下，将值映射到字典键和转换的任务是使用 dict()和 zip()以及字典理解来完成的。Rest 功能类似于上述方法。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Convert Matrix to Dictionary Value List
# Using dict() + list comprehension + zip()
from collections import defaultdict

# initializing list
test_list = [[4, 5, 6], [1, 3, 5], [3, 8, 1], [10, 3, 5]]

# printing original list
print("The original list is : " + str(test_list))

# initializing map list 
map_list = [4, 5, 6]

# mapping column using zip() and conversion using using dict()
# converts to list of dictionary
temp = [dict(zip(map_list, sub)) for sub in test_list]

# convert to dictionary value list 
res = defaultdict(list) 
{res[key].append(sub[key]) for sub in temp for key in sub}

# printing result
print("Converted Dictionary : " + str(dict(res)))
```

**输出:**

> 原来的名单是:[[4，5，6]，[1，3，5]，[3，8，1]，[10，3，5]]
> 
> 转换的字典:{4: [4，1，3，10]，5: [5，3，8，3]，6: [6，5，1，5]}