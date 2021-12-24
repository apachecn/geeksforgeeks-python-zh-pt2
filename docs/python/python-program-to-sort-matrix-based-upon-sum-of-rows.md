# Python 程序根据行的总和对矩阵进行排序

> 原文:[https://www . geeksforgeeks . org/python-基于行总和的程序到排序矩阵/](https://www.geeksforgeeks.org/python-program-to-sort-matrix-based-upon-sum-of-rows/)

给定一个矩阵，根据行的总和进行排序。

> **输入** : test_list = [[4，5]，[2，5，7]，[2，1]，[4，6，1]]
> **输出** : [[2，1]，[4，5]，[4，6，1]，[2，5，7]]
> **解释** : 3 < 9 < 11 < 14。排序总和。
> 
> **输入** : test_list = [[4，5]，[2，5，7]，[4，6，1]]
> **输出** : [[4，5]，[4，6，1]，[2，5，7]]
> **解释** : 9 < 11 < 14。排序总和。

**方法#1:使用 sort() + sum()**

在这种情况下，排序的任务是使用 sort()完成的，求和的计算是通过 sum()完成的，并作为键 fnc 传递。对()进行排序。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort Matrix by row sum
# Using sort() + sum()

# helper_fnc
def sum_sort(row):

    # getting sum
    return sum(row)

# initializing list
test_list = [[4, 5], [2, 5, 7], [2, 1], [4, 6, 1]]

# printing original list
print("The original list is : " + str(test_list))

# using sort() to perform sort
test_list.sort(key = sum_sort)

# printing result
print("Sum sorted Matrix : " + str(test_list))
```

**输出:**

> 原始列表为:[[4，5]，[2，5，7]，[2，1]，[4，6，1]]
> 求和排序矩阵:[[2，1]，[4，5]，[4，6，1]，[2，5，7]]

**方法 2:使用** [**排序()**](https://www.geeksforgeeks.org/sorted-function-python/)**+sum()+**[**λ**](https://www.geeksforgeeks.org/python-lambda/)

在这种情况下，排序任务是使用 sorted()完成的，lambda 用来代替键的外部函数调用。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort Matrix by row sum
# Using sorted() + sum() + lambda

# initializing list
test_list = [[4, 5], [2, 5, 7], [2, 1], [4, 6, 1]]

# printing original list
print("The original list is : " + str(test_list))

# using lambda function preventing fnc. call
res = sorted(test_list, key=lambda row: sum(row))

# printing result
print("Sum sorted Matrix : " + str(res))
```

**输出:**

> 原始列表为:[[4，5]，[2，5，7]，[2，1]，[4，6，1]]
> 求和排序矩阵:[[2，1]，[4，5]，[4，6，1]，[2，5，7]]