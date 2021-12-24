# 将矩阵转换为字符串的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序-转换-矩阵-字符串/](https://www.geeksforgeeks.org/python-program-to-convert-matrix-to-string/)

给定一个矩阵，我们的任务是编写一个 Python 程序来转换成矩阵，元素和行的分隔使用不同的分隔符。

**示例:**

> **输入:** test_list = test_list = [[1，3，“gfg”]，[2，“is”，4]，[“best”，9，5]]，in_del，out_del =“，”
> 
> **输出:** 1，3，gfg 2，is，4 最佳，9，5
> 
> **说明:**列表中以“，”分隔的元素，以及以“”分隔的列表。
> 
> **输入:** test_list = test_list = [[1，3，" gfg"]，[2，" is "，4]，["best "，9，5]]，in_del，out_del = "，"，"-"
> 
> **输出:** 1，3，gfg-2，is，4-best，9，5
> 
> **说明:**列表中的元素用“，”分隔，列表用“-”分隔。

**方法一:使用** [**加入()**](https://www.geeksforgeeks.org/join-function-python/) **+** [**列表理解**](https://www.geeksforgeeks.org/comprehensions-in-python/)

在本文中，我们使用列表理解来执行迭代每行的每个元素的任务。使用 join()对具有不同分隔符的元素和行进行内部和外部联接。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert Matrix to String
# Using list comprehension + join()

# initializing list
test_list = [[1, 3, "gfg"], [2, "is", 4], ["best", 9, 5]]

# printing original list
print("The original list is : " + str(test_list))

# initializing delims
in_del, out_del = ",", " "

# nested join using join()
res = out_del.join([in_del.join([str(ele) for ele in sub]) for sub in test_list])

# printing result
print("Conversion to String : " + str(res))
```

**输出:**

> 原始列表为:[[1，3，' gfg']，[2，' is '，4]，['best '，9，5]]
> 
> 转换为字符串:1，3，gfg 2，is，4 最佳，9，5

**方法 2:使用** [**地图()**](https://www.geeksforgeeks.org/python-map-function/) **+** [**加入()**](https://www.geeksforgeeks.org/join-function-python/)

在这种情况下，元素内部连接的任务是使用 map()扩展到每个字符。其余所有功能都类似于上位法。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert Matrix to String
# Using map() + join()

# initializing list
test_list = [[1, 3, "gfg"], [2, "is", 4], ["best", 9, 5]]

# printing original list
print("The original list is : " + str(test_list))

# initializing delims
in_del, out_del = ",", " "

# nested join using join()
# map() for joining inner elements
res = out_del.join(in_del.join(map(str, sub)) for sub in test_list)

# printing result
print("Conversion to String : " + str(res))
```

**输出:**

> 原始列表为:[[1，3，' gfg']，[2，' is '，4]，['best '，9，5]]
> 
> 转换为字符串:1，3，gfg 2，is，4 最佳，9，5