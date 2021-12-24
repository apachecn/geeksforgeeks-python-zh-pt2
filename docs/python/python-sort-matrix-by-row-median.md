# Python–按行中间值排序矩阵

> 原文:[https://www . geeksforgeeks . org/python-排序-逐行矩阵-中位数/](https://www.geeksforgeeks.org/python-sort-matrix-by-row-median/)

给定一个矩阵，按每行的中位数排序。

> **输入** : test_list = [[3，4，7]，[1，7，2]，[10，2，4]，[8，6，5]]
> **输出** : [[1，7，2]，[3，4，7]，[10，2，4]，[8，6，5]]
> **解释** : 2 < 3 < 4 < 6，按中值元素排序越来越多。
> 
> **输入** : test_list = [[3，4，7]，[1，7，2]，[8，6，5]]
> **输出** : [[1，7，2]，[3，4，7]，[8，6，5]]
> **解释** : 2 < 3 < 6，越来越按中值元素排序。

**方法#1:使用 sort() +中位数()**

在这种情况下，我们使用 *sort()* 执行排序，并且使用计算中值的统计函数*中值()*来计算中值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sort Matrix by Row Median
# Using sort() + median()
from statistics import median

def med_comp(row):

    # computing median
    return median(row)

# initializing list
test_list = [[3, 4, 7], [1, 7, 2], [10, 2, 4], [8, 6, 5]]

# printing original list
print("The original list is : " + str(test_list))

# inplace sorting using sort()
test_list.sort(key = med_comp)

# printing result 
print("Sorted Matrix : " + str(test_list))
```

**Output**

```py
The original list is : [[3, 4, 7], [1, 7, 2], [10, 2, 4], [8, 6, 5]]
Sorted Matrix : [[1, 7, 2], [3, 4, 7], [10, 2, 4], [8, 6, 5]]

```

**方法 2:使用排序的()+λ+中位数()**

在这种情况下，我们使用 *sorted()* 执行排序任务， *lambda* 函数用作键函数，而不是外部函数。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sort Matrix by Row Median
# Using sorted() + lambda + median()
from statistics import median

# initializing list
test_list = [[3, 4, 7], [1, 7, 2], [10, 2, 4], [8, 6, 5]]

# printing original list
print("The original list is : " + str(test_list))

# inplace sorting using sort()
res = sorted(test_list, key = lambda row : median(row))

# printing result 
print("Sorted Matrix : " + str(res))
```

**Output**

```py
The original list is : [[3, 4, 7], [1, 7, 2], [10, 2, 4], [8, 6, 5]]
Sorted Matrix : [[1, 7, 2], [3, 4, 7], [10, 2, 4], [8, 6, 5]]

```