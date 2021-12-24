# Python 程序打印特定行数的最大和

> 原文:[https://www . geesforgeks . org/python-program-to-print-特定行数最大和/](https://www.geeksforgeeks.org/python-program-to-print-a-specific-number-of-rows-with-maximum-sum/)

给定一个矩阵，下面的文章提取一个具有最大和的指定行数。

> **输入** : test_list = [[3，4，5，6]，[1，4，6]，[199]，[2，3，4，5，6]，[7，3，1]]，K = 3
> **输出** : [[199]，[2，3，4，5，6]，[3，4，5，6]]
> **解释** : 199 > 20 > 18，3 最大
> **输入** : test_list = [[3，4，5，6]，[1，4，6]，[199]，[2，3，4，5，6]，[7，3，1]]，K = 2
> **输出** : [[199]，[2，3，4，5，6]]
> **解释** : 199 > 20，最多提取 2 个元素行。

**方法 1 :** *使用* [*排序()，*](https://www.geeksforgeeks.org/sorting-algorithms/) [*反转，*](https://www.geeksforgeeks.org/python-list-reverse/) [*切片*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) *和* [*求和()*](https://www.geeksforgeeks.org/sum-function-python/)

在本文中，我们使用 sorted()执行排序任务，并使用 sum()获取 sum。反向键用于执行行的反向，以获得顶部的最大求和行，然后对顶部的 K(特定行数)行进行切片。

## 蟒蛇 3

```py
# initializing list
test_list = [[3, 4, 5, 6], [1, 4, 6], [199], [2, 3, 4, 5, 6], [7, 3, 1]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 3

# sorted gets reverse sorted matrix by sum
# K rows extracted using slicing
res = sorted(test_list, key=lambda row: sum(row), reverse=True)[:K]

# printing result
print("The filtered rows : " + str(res))
```

**输出:**

> 原来的名单是:[[3，4，5，6]，[1，4，6]，[199]，[2，3，4，5，6]，[7，3，1]]
> 
> 筛选的行:[[199]，[2，3，4，5，6]，[3，4，5，6]]

**方法二:** *利用* [*排序()*](https://www.geeksforgeeks.org/sort-in-python/)*[*反*](https://www.geeksforgeeks.org/python-list-reverse/)*[*切片*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) *和* [*求和()*](https://www.geeksforgeeks.org/sum-function-python/)**

**在本文中，我们使用 sort()执行就地排序的任务，使用 reverse 作为关键字。切片是使用切片操作完成的。sum()用于求和，调用一个外部函数来计算列表行的总和。**

## **蟒蛇 3**

```py
**# row sum util.
def row_sum(row):
    return sum(row)

# initializing list
test_list = [[3, 4, 5, 6], [1, 4, 6], [199], [2, 3, 4, 5, 6], [7, 3, 1]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 3

# sort() used to sort
# K rows extracted using slicing
test_list.sort(key=row_sum, reverse=True)
res = test_list[:K]

# printing result
print("The filtered rows : " + str(res))**
```

****输出:****

> **原来的名单是:[[3，4，5，6]，[1，4，6]，[199]，[2，3，4，5，6]，[7，3，1]]**
> 
> **筛选的行:[[199]，[2，3，4，5，6]，[3，4，5，6]]**