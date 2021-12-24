# Python–按 K 尺寸子阵列最大和排序矩阵

> 原文:[https://www . geesforgeks . org/python-sort-matrix-by-k-size-subarray-maximum-sum/](https://www.geeksforgeeks.org/python-sort-matrix-by-k-sized-subarray-maximum-sum/)

给定 Matrix，编写一个 Python 程序，根据 K 大小的子数组和的最大值对行进行排序。

**示例:**

> **输入** : test_list = [[4，3，5，2，3]，[6，4，2，1，1]，[4，3，9，3，9]，[5，4，3，2，1]]，K = 3
> **输出** : [[4，3，5，2，3]，[6，4，2，1，1]，[5，4，3，2，1]，[4，3，9，3，9]]
> 
> **输入** : test_list = [[4，3，5，2，3]，[4，3，9，3，9]，[5，4，3，2，1]]，K = 3
> **输出** : [[4，3，5，2，3]，[5，4，3，2，1]，[4，3，9，3，9]]
> **解释** : 12 = 12 < 21，为最大和 3 的阶

**方法#1:使用**[**max()**](https://www.geeksforgeeks.org/python-max-function/)**+**[**sum()**](https://www.geeksforgeeks.org/sum-function-python/)**+**[**切片**](https://www.geeksforgeeks.org/string-slicing-in-python/) **+排序()**

在这种情况下，使用 max()和 sum()计算 K 长度子阵列的最大值，使用外部函数进行切片，使用 sort()进行就地排序。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Sort Matrix by K Sized Subarray Maximum Sum
# Using max() + sum() + slicing + sort()

def max_ksub(row):

    # getting maximum K length sum
    return max(sum(row[idx: idx + K]) for idx in range(len(row) - K))

# initializing list
test_list = [[4, 3, 5, 2, 3], [6, 4, 2, 1, 1],
             [4, 3, 9, 3, 9], [5, 4, 3, 2, 1]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 3

# performing inplace sorting
test_list.sort(key=max_ksub)

# printing result
print("The sorted result : " + str(test_list))
```

**输出:**

> 原列表为:[[4，3，5，2，3]，[6，4，2，1，1]，[4，3，9，3，9]，[5，4，3，2，1]]
> 排序后的结果:[[4，3，5，2，3]，[6，4，2，1，1]，[5，4，3，2，1]，[4，3，9，3，9]]

**方法 2:使用** [**排序()**](https://www.geeksforgeeks.org/sorted-function-python/)**+**[**λ**](https://www.geeksforgeeks.org/python-lambda/)**+max()+sum()+切片**

在这种情况下，我们使用 sorted() + lambda 函数执行排序任务，该函数注入了比较器逻辑并避免调用外部函数。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Sort Matrix by K Sized Subarray Maximum Sum
# Using sorted() + lambda + max() + sum() + slicing

# initializing list
test_list = [[4, 3, 5, 2, 3], [6, 4, 2, 1, 1],
             [4, 3, 9, 3, 9], [5, 4, 3, 2, 1]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 3

# sorted() performs inplace sort
# lambda function injects comparison logic
res = sorted(test_list, key=lambda row: max(
    sum(row[idx: idx + K]) for idx in range(len(row) - K)))

# printing result
print("The sorted result : " + str(res))
```

**输出:**

> 原列表为:[[4，3，5，2，3]，[6，4，2，1，1]，[4，3，9，3，9]，[5，4，3，2，1]]
> 排序后的结果:[[4，3，5，2，3]，[6，4，2，1，1]，[5，4，3，2，1]，[4，3，9，3，9]]