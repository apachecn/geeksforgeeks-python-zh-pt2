# 从矩阵中打印给定长度的行的 Python 程序

> 原文:[https://www . geeksforgeeks . org/打印矩阵中给定长度行的 python 程序/](https://www.geeksforgeeks.org/python-program-that-prints-the-rows-of-a-given-length-from-a-matrix/)

给定一个矩阵，下面的文章展示了如何提取指定长度的所有行。

> **输入** : test_list = [[3，4，5，6]，[1，4，6]，[2，3，4，5，6]，[7，3，1]]，K = 3
> **输出** : [[1，4，6]，[7，3，1]]
> **解释**:提取的列表长度为 3。
> **输入** : test_list = [[3，4，5，6]，[1，4，6]，[2]，[2，3，4，5，6]，[7，3，1]]，K = 4
> **输出** : [[3，4，5，6]]
> **解释**:提取的列表长度为 4。

**方法一:** *使用* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) *和* [*len()*](https://www.geeksforgeeks.org/python-string-length-len/)

在这种情况下，我们使用 len()执行获取长度的任务，列表理解执行过滤具有指定长度的所有行的任务。

## 蟒蛇 3

```py
# initializing list
test_list = [[3, 4, 5, 6], [1, 4, 6], [2], [2, 3, 4, 5, 6], [7, 3, 1]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 3

# list comprehension is used for extracting K len rows
res = [sub for sub in test_list if len(sub) == K]

# printing result
print("The filtered rows : " + str(res))
```

**输出:**

> 原来的名单是:[[3，4，5，6]，[1，4，6]，[2]，[2，3，4，5，6]，[7，3，1]]
> 
> 筛选的行:[[1，4，6]，[7，3，1]]

**方法二:** *使用* [*滤镜()*](https://www.geeksforgeeks.org/filter-in-python/)*[*λ*](https://www.geeksforgeeks.org/python-lambda/)*和* [*len()*](https://www.geeksforgeeks.org/python-string-length-len/)*

*在本文中，我们使用 filter()和 lambda 执行过滤任务。len()用于查找行的长度。*

## *蟒蛇 3*

```py
*# initializing list
test_list = [[3, 4, 5, 6], [1, 4, 6], [2], [2, 3, 4, 5, 6], [7, 3, 1]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 3

# filter() + lambda to filter out rows of len K
res = list(filter(lambda sub: len(sub) == K, test_list))

# printing result
print("The filtered rows : " + str(res))*
```

***输出:***

> *原来的名单是:[[3，4，5，6]，[1，4，6]，[2]，[2，3，4，5，6]，[7，3，1]]*
> 
> *筛选的行:[[1，4，6]，[7，3，1]]*