# Python–按范围包含排序

> 原文:[https://www . geesforgeks . org/python-按范围排序-包含/](https://www.geeksforgeeks.org/python-sort-by-range-inclusion/)

给定一个范围，按给定范围内覆盖的总范围对元组矩阵进行排序。[考虑完全位于范围内的元组]。

> **输入** : test_list = [[(1，5)，(6，10)，(10，15)]，[(3，16)]，[(2，4)，(6，8)，(9，14)]，[(1，3)，(9，13)]，I，j = 2，15
> **输出** : [[(3，16)]，[(1，5)，(6，10)，(10，15)]，[(1，3)，(9，13)]，[(10)
> 
> **输入**:test _ list =[(1，5)，(6，10)，(10，15)]，[(3，16)]，[(2，4)，(6，8)，(9，14)]，I，j = 2，15
> **输出** : [[(3，16)]，[(1，5)，(6，10)，(10，15)]，[(2，4)，(6，8)，(9，14)]
> **解释**:

**方法#1:使用 sort()+**[**sum()**](https://www.geeksforgeeks.org/sum-function-python/)

在这种情况下，使用 sort()执行就地排序，使用 sum()和带条件的列表理解执行给定范围内的范围求和。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort by range inclusion
# Using sort() + sum()

def range_sum(row):

    # summing in range element
    return sum([abs(sub[1] - sub[0]) for sub in row if sub[0] > i and sub[0] < j and sub[1] > i and sub[1] < j])

# initializing list
test_list = [[(1, 5), (6, 10), (10, 15)], [(3, 16)], [
    (2, 4), (6, 8), (9, 14)], [(1, 3), (9, 13)]]

# printing original list
print("The original list is : " + str(test_list))

# initializing range
i, j = 2, 15

# inplace sorting using sort()
test_list.sort(key=range_sum)

# printing result
print("Sorted List : " + str(test_list))
```

**输出:**

> 原列表为:[(1，5)，(6，10)，(10，15)]，[(3，16)]，[(2，4)，(6，8)，(9，14)]，[(1，3)，(9，13)]]
> 排序列表:[(3，16)]，[(1，5)，(6，10)，(10，15)]，[(1，3)，(9，13)]，[(2，4)，(6，8)，(9，14)]

**方法 2:使用** [**排序()**](https://www.geeksforgeeks.org/sorted-function-python/)**+**[**λ**](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)**+求和()**

在本文中，我们使用 sorted()执行排序任务，使用 lambda 函数执行效用注入，使用 sum()执行求和。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort by range inclusion
# Using sorted() + lambda + sum()

# initializing list
test_list = [[(1, 5), (6, 10), (10, 15)], [(3, 16)], [
    (2, 4), (6, 8), (9, 14)], [(1, 3), (9, 13)]]

# printing original list
print("The original list is : " + str(test_list))

# initializing range
i, j = 2, 15

# sorting using sorted() + lambda
res = sorted(test_list, key=lambda row: sum(
    [abs(sub[1] - sub[0]) for sub in row if sub[0] > i and sub[0] < j and sub[1] > i and sub[1] < j]))

# printing result
print("Sorted List : " + str(res))
```

**输出:**

> 原列表为:[(1，5)，(6，10)，(10，15)]，[(3，16)]，[(2，4)，(6，8)，(9，14)]，[(1，3)，(9，13)]]
> 排序列表:[(3，16)]，[(1，5)，(6，10)，(10，15)]，[(1，3)，(9，13)]，[(2，4)，(6，8)，(9，14)]