# Python 程序从其他元组列表中查找元组索引

> 原文:[https://www . geesforgeks . org/python-程序-查找-元组-索引-从其他元组-列表/](https://www.geeksforgeeks.org/python-program-to-find-tuple-indices-from-other-tuple-list/)

给定元组列表和由要搜索的元组组成的搜索列表，我们的任务是编写一个 Python 程序来提取匹配元组的索引。

> **输入:** test_list = [(4，5)，(7，6)，(1，0)，(3，4)]，search_tup = [(3，4)，(8，9)，(7，6)，(1，2)]
> 
> **输出:**【3，1】
> 
> **说明:** (3，4)来自搜索列表，位于 test_list 的第三个索引上，因此包含在结果中。
> 
> **输入:** test_list = [(4，5)，(7，6)，(1，0)，(3，4)]，search_tup = [(3，4)，(8，9)，(7，6)，(1，0)]
> 
> **输出:**【3，1，2】
> 
> **说明:** (3，4)来自搜索列表，位于 test_list 的第三个索引上，因此包含在结果中。

**方法一:使用** [**查找字典**](https://www.geeksforgeeks.org/using-dictionary-to-remap-values-in-pandas-dataframe-columns/) **+** [**枚举()**](https://www.geeksforgeeks.org/enumerate-in-python/) **+** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

在这种情况下，形成一个查找字典来映射所有具有匹配索引的元组。然后使用查找字典获得映射元组的索引，作为使用列表理解的结果。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Find tuple indices from other tuple list
# Using lookup dictionary + enumerate() + list comprehension

# initializing list
test_list = [(4, 5), (7, 6), (1, 0), (3, 4)]

# printing original list
print("The original list is : " + str(test_list))

# initializing search tuple 
search_tup = [(3, 4), (8, 9), (7, 6), (1, 2)]

# creating lookup_dict
lookup_dict = {val: key for key,val in enumerate(test_list)}

# creating result list
res = [lookup_dict[idx] for idx in search_tup if idx in lookup_dict]

# printing result
print("The match tuple indices : " + str(res))
```

**输出:**

```py
The original list is : [(4, 5), (7, 6), (1, 0), (3, 4)]
The match tuple indices : [3, 1]
```

**方法 2:使用列表理解+枚举()**

在这种情况下，我们使用 enumerate()执行获取索引的任务，列表理解用于元组所有元素的迭代和相等匹配的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Find tuple indices from other tuple list
# Using list comprehension + enumerate()

# initializing list
test_list = [(4, 5), (7, 6), (1, 0), (3, 4)]

# printing original list
print("The original list is : " + str(test_list))

# initializing search tuple 
search_tup = [(3, 4), (8, 9), (7, 6), (1, 2)]

# enumerate() gets all the indices 
res = [idx for idx, val in enumerate(test_list) for ele in search_tup if ele == val]

# printing result
print("The match tuple indices : " + str(res))
```

**输出:**

```py
The original list is : [(4, 5), (7, 6), (1, 0), (3, 4)]
The match tuple indices : [1, 3]
```