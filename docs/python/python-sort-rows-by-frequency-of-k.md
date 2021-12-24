# Python–按 K 的频率排序行

> 原文:[https://www . geesforgeks . org/python-按 k 的频率对行进行排序/](https://www.geeksforgeeks.org/python-sort-rows-by-frequency-of-k/)

给定一个矩阵，的任务是编写一个 Python 程序根据 k 的频率对行进行排序。

> **输入** : test_list = [[10，2，3，2，3]，[5，5，4，7，7，4]，[1，2]，[1，1，2，2，2，2]]，K = 2
> **输出** : [[5，5，4，7，7，4]，[1，2]，[10，2，3，2，3]，[1，1，2，2，]
> **解释**:
> 
> **输入** : test_list = [[5，5，4，7，7，4]，[1，2]，[1，1，2，2，2]]，K = 2
> **输出** : [[5，5，4，7，7，4]，[1，2]，[1，1，2，2]]
> **解释** : 0 < 1 < 3、矩阵顺序 K 的计数。

**方法#1:使用** [**排序()**](https://www.geeksforgeeks.org/sort-in-python/) **+** [**计数()**](https://www.geeksforgeeks.org/python-list-function-count/)

在本例中，我们使用 *sort()* 执行就地排序任务，使用 *count()* 完成捕获频率。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort rows by Frequency of K
# Using sort() + count()

def get_Kfreq(row):

    # return Frequency
    return row.count(K)

# initializing list
test_list = [[10, 2, 3, 2, 3], [5, 5, 4, 7, 7, 4], [1, 2], [1, 1, 2, 2, 2]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 2

# performing inplace sort
test_list.sort(key=get_Kfreq)

# printing result
print("Sorted List : " + str(test_list))
```

**输出:**

> 原始列表为:[[10，2，3，2，3]，[5，5，4，7，7，4]，[1，2]，[1，1，2，2，2]]
> 排序列表:[[5，5，4，7，7，4]，[1，2]，[10，2，3，2，3]，[1，1，2，2，2，2]]

**方法 2:使用** [**排序()**](https://www.geeksforgeeks.org/sorted-function-python/)**+**[**λ**](https://www.geeksforgeeks.org/python-lambda/)**+**[**计数()**](https://www.geeksforgeeks.org/python-list-function-count/)

在这种情况下，我们使用 *sorted()* 和 *lambda* 执行排序任务，消除了用于计算的外部函数调用和 *lambda* 函数。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort rows by Frequency of K
# Using sorted() + lambda + count()

# initializing list
test_list = [[10, 2, 3, 2, 3], [5, 5, 4, 7, 7, 4], [1, 2], [1, 1, 2, 2, 2]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 2

# performing inplace sort
res = sorted(test_list, key=lambda row: row.count(K))

# printing result
print("Sorted List : " + str(res))
```

**输出:**

> 原始列表为:[[10，2，3，2，3]，[5，5，4，7，7，4]，[1，2]，[1，1，2，2，2]]
> 排序列表:[[5，5，4，7，7，4]，[1，2]，[10，2，3，2，3]，[1，1，2，2，2，2]]