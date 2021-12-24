# 使用特定对和过滤行的 Python 程序

> 原文:[https://www . geeksforgeeks . org/python-程序-用特定对-和筛选行/](https://www.geeksforgeeks.org/python-program-to-filter-rows-with-a-specific-pair-sum/)

给定 Matrix，下面的程序显示了如何提取具有一对的所有行，使得它们的和等于一个特定的数，这里表示为 k

> **输入** : test_list = [[1，5，3，6]，[4，3，2，1]，[7，2，4，5]，[6，9，3，2]]，k = 8
> **输出** : [[1，5，3，6]，[6，9，3，2]]
> **解释** : 5 + 3 = 8 和 6 + 2 = 8。
> **输入** : test_list = [[1，5，4，6]，[4，3，2，1]，[7，2，4，5]，[6，9，3，7]]，k = 8
> **输出** : []
> **解释**:没有以 8 为对求和的列表。

**方法一:** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/) *和* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，我们执行的任务是使用外部函数获取其和等于给定值的所有对，并且使用列表理解来完成列表的过滤。

## 蟒蛇 3

```
# get pair sum
def pair_sum(x, k):

    # checking pair sum
    for idx in range(len(x)):
        for ix in range(idx + 1, len(x)):
            if x[idx] + x[ix] == k:
                return True
    return False

# initializing list
test_list = [[1, 5, 3, 6], [4, 3, 2, 1], [7, 2, 4, 5], [6, 9, 3, 2]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
k = 8

# checking for pair sum
res = [ele for ele in test_list if pair_sum(ele, k)]

# printing result
print("Filtered Rows : " + str(res))
```

**输出:**

> 原来的名单是:[[1，5，3，6]，[4，3，2，1]，[7，2，4，5]，[6，9，3，2]]
> 
> 筛选的行:[[1，5，3，6]，[6，9，3，2]]

**方法二:** *使用* [*滤镜()*](https://www.geeksforgeeks.org/filter-in-python/) *和*[*λ*](https://www.geeksforgeeks.org/python-lambda/)

在本文中，我们使用 filter()和 lambda 函数执行过滤任务。

## 蟒蛇 3

```
# get pair sum
def pair_sum(x, k):

    # checking pair sum
    for idx in range(len(x)):
        for ix in range(idx + 1, len(x)):
            if x[idx] + x[ix] == k:
                return True
    return False

# initializing list
test_list = [[1, 5, 3, 6], [4, 3, 2, 1], [7, 2, 4, 5], [6, 9, 3, 2]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
k = 8

# checking for pair sum
# filtering using filter() and lambda
res = list(filter(lambda ele: pair_sum(ele, k), test_list))

# printing result
print("Filtered Rows : " + str(res))
```

**输出:**

> 原来的名单是:[[1，5，3，6]，[4，3，2，1]，[7，2，4，5]，[6，9，3，2]]
> 
> 筛选的行:[[1，5，3，6]，[6，9，3，2]]