# 根据主索引和次索引对矩阵行进行排序的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序-排序-矩阵-行-按主索引和次索引/](https://www.geeksforgeeks.org/python-program-to-sort-matrix-rows-according-to-primary-and-secondary-indices/)

给定 Matrix，这里的任务是编写一个 Python 程序，根据主索引和次索引对行进行排序。首先使用主索引，将根据每行在指定主索引处的元素来排列行。现在，如果两行在给定的主索引处具有相同的元素，将使用辅助索引再次执行排序。

> **输入:** test_list = [[2，5，7，4]，[8，1，3，10]，[9，1，9，4]，[10，1，1，4]]，pri，sec = 3，2
> 
> **输出:** [[10，1，1，4]，[2，5，7，4]，[9，1，9，4]，[8，1，3，10]]
> 
> **说明:**按第三索引排序，第三索引元素相等时按第二索引排序。
> 
> **输入:** test_list = [[2，5，7，4]，[8，1，3，10]，[9，1，9，4]，[10，1，1，4]]，pri，sec = 1，2
> 
> **输出:** [[10，1，1，4]，[8，1，3，10]，[9，1，9，4]，[2，5，7，4]]
> 
> **说明:**按第一索引排序，第一索引元素相等时按第二索引排序。

**方法 1 :** *使用* [*排序()*](https://www.geeksforgeeks.org/sort-in-python/) *和*[*λ*](https://www.geeksforgeeks.org/python-lambda/)

这将使用 sort()执行就地排序，lambda 函数用于使用 lambda 函数的关键字中顺序定义的排序顺序执行排序。

**程序:**

## 蟒蛇 3

```
# initializing list
test_list = [[2, 5, 7, 4], [8, 1, 3, 10], [9, 1, 9, 4], [10, 1, 1, 4]]

# printing original list
print("The original list is : " + str(test_list))

# initializing pri, sec
pri, sec = 3, 2

# inplace sorting using sort()
test_list.sort(key=lambda ele: (ele[pri], ele[sec]))

# printing result
print("Matrix after sorting : " + str(test_list))
```

**输出:**

> 原来的名单是:[[2，5，7，4]，[8，1，3，10]，[9，1，9，4]，[10，1，1，4]]
> 
> 排序后的矩阵:[[10，1，1，4]，[2，5，7，4]，[9，1，9，4]，[8，1，3，10]]

**方法二:** *使用* [*排序()*](https://www.geeksforgeeks.org/sorted-function-python/) *和*[*item getter()*](https://www.geeksforgeeks.org/ways-sort-list-dictionaries-values-python-using-itemgetter/)

在本例中，我们使用 sorted()执行排序任务，itemgetter()用于根据需要执行获取索引的任务。

**程序:**

## 蟒蛇 3

```
import operator

# initializing list
test_list = [[2, 5, 7, 4], [8, 1, 3, 10], [9, 1, 9, 4], [10, 1, 1, 4]]

# printing original list
print("The original list is : " + str(test_list))

# initializing pri, sec
pri, sec = 3, 2

# inplace sorting using sort()
res = sorted(test_list, key=operator.itemgetter(pri, sec))

# printing result
print("Matrix after sorting : " + str(res))
```

**输出:**

> 原来的名单是:[[2，5，7，4]，[8，1，3，10]，[9，1，9，4]，[10，1，1，4]]
> 
> 排序后的矩阵:[[10，1，1，4]，[2，5，7，4]，[9，1，9，4]，[8，1，3，10]]