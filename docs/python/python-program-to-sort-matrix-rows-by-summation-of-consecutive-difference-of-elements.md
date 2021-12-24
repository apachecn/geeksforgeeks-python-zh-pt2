# Python 程序通过元素的连续差的总和对矩阵行进行排序

> 原文:[https://www . geesforgeks . org/python-程序-对矩阵进行排序-逐行对连续元素差求和/](https://www.geeksforgeeks.org/python-program-to-sort-matrix-rows-by-summation-of-consecutive-difference-of-elements/)

给定一个矩阵，下面的文章描述了如何根据一行中连续元素之间的差值总和对矩阵的行进行排序。

> **输入** : test_list = [[1，5，3，6]，[4，3，2，1]，[7，2，4，5]，[6，9，3，2]]，
> **输出** : [[4，3，2，1]，[7，2，4，5]，[1，5，3，6]，[6，9，3，2]]
> **解释**:4<8<9
> **输入** : test_list = [[1，5，3，6]，[7，2，4，5]，[6，9，3，2]]，
> **输出** : [[7，2，4，5]，[1，5，3，6]，[6，9，3，2]]
> **解释** : 8 < 9 < 10 为连续差求和。

**方法 1 :** *使用* [*排序()*](https://www.geeksforgeeks.org/sort-in-python/) *和* [*abs()*](https://www.geeksforgeeks.org/abs-in-python/)

在这种情况下，我们使用 sort()执行就地排序任务，并使用 abs()获得连续差值总和的绝对值。

## 蟒蛇 3

```
# get abs summation
def diff_sum(row):
    return sum([abs(row[idx + 1] - row[idx]) for idx in range(0, len(row) - 1)])

# initializing list
test_list = [[1, 5, 3, 6], [4, 3, 2, 1], [7, 2, 4, 5], [6, 9, 3, 2]]

# printing original list
print("The original list is : " + str(test_list))

# performing inplace sort
test_list.sort(key=diff_sum)

# printing result
print("Sorted Rows : " + str(test_list))
```

**输出:**

> 原来的名单是:[[1，5，3，6]，[4，3，2，1]，[7，2，4，5]，[6，9，3，2]]
> 
> 排序行:[[4，3，2，1]，[7，2，4，5]，[1，5，3，6]，[6，9，3，2]]

**方法二:** *使用* [*排序()*](https://www.geeksforgeeks.org/sorted-function-python/)*[*λ*](https://www.geeksforgeeks.org/python-lambda/)*[*ABS()*](https://www.geeksforgeeks.org/abs-in-python/)*和* [*求和()*](https://www.geeksforgeeks.org/sum-function-python/)**

**在这种情况下，排序是使用 sorted()完成的，lambda 函数用于在 sorted()中注入条件语句。**

## **蟒蛇 3**

```
**# initializing list
test_list = [[1, 5, 3, 6], [4, 3, 2, 1], [7, 2, 4, 5], [6, 9, 3, 2]]

# printing original list
print("The original list is : " + str(test_list))

# performing sort
res = sorted(test_list, key=lambda row: sum(
    [abs(row[idx + 1] - row[idx]) for idx in range(0, len(row) - 1)]))

# printing result
print("Sorted Rows : " + str(res))**
```

****输出:****

> **原来的名单是:[[1，5，3，6]，[4，3，2，1]，[7，2，4，5]，[6，9，3，2]]**
> 
> **排序行:[[4，3，2，1]，[7，2，4，5]，[1，5，3，6]，[6，9，3，2]]**