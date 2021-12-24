# Python 程序打印所有元素频率大于 K 的行

> 原文:[https://www . geesforgeks . org/python-程序-打印-行-其中所有元素-频率-大于-k/](https://www.geeksforgeeks.org/python-program-to-print-rows-where-all-its-elements-frequency-is-greater-than-k/)

给定矩阵，提取所有元素的频率大于 k 的所有行

> **输入** : test_list = [[1，1，2，3，2，3]，[4，4，5，6，6]，[1，1，1，1]，[4，5，6，8]]，K = 2
> **输出** : [[1，1，1，1]]
> :这里，1 的频率为 4 > 2，因此保留行。
> 
> **输入** : test_list = [[1，1，2，3，2，3]，[4，4，5，6，6]，[1，3，4，1]，[4，5，6，8]]，K = 2
> **输出** : []
> **解释**:结果未过滤列表。

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) **+** [**全部()**](https://www.geeksforgeeks.org/any-all-in-python/) **+** [**计数()**](https://www.geeksforgeeks.org/python-list-function-count/)

在本例中，我们使用列表理解执行元素迭代任务，并且 all()用于检查使用 count()提取的每个元素 count()。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Rows with all Elements frequency greater than K
# Using list comprehension + count() + all()

def freq_greater_K(row, K) :

    # checking for all elements occurrence greater than K 
    return all(row.count(ele) > K for ele in row)

# initializing list
test_list = [[1, 1, 2, 3, 2, 3], [4, 4, 5, 6, 6], [1, 1, 1, 1], [4, 5, 6, 8]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 1

# checking for each row 
res = [ele for ele in test_list if freq_greater_K(ele, K)]

# printing result 
print("Filtered rows : " + str(res))
```

**输出:**

> 原始列表为:[[1，1，2，3，2，3]，[4，4，5，6，6]，[1，1，1，1]，[4，5，6，8]]
> 筛选行:[[1，1，2，3，2，3]，[1，1，1]]

**方法 2:使用** [**滤镜()**](https://www.geeksforgeeks.org/filter-in-python/)**+**[**λ**](https://www.geeksforgeeks.org/python-lambda/)**+all()+count()**

在这种情况下，过滤任务是使用 filter() + lambda 完成的，all()用于检查每个元素，count()用于计算计数。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Rows with all Elements frequency greater than K
# Using filter() + lambda + all() + count()

def freq_greater_K(row, K) :

    # checking for all elements occurrence greater than K 
    return all(row.count(ele) > K for ele in row)

# initializing list
test_list = [[1, 1, 2, 3, 2, 3], [4, 4, 5, 6, 6], [1, 1, 1, 1], [4, 5, 6, 8]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 1

# checking for each row 
res = list(filter(lambda ele : freq_greater_K(ele, K), test_list))

# printing result 
print("Filtered rows : " + str(res))
```

**输出:**

> 原始列表为:[[1，1，2，3，2，3]，[4，4，5，6，6]，[1，1，1，1]，[4，5，6，8]]
> 筛选行:[[1，1，2，3，2，3]，[1，1，1]]