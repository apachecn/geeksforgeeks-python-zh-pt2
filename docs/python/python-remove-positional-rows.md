# Python–删除位置行

> 原文:[https://www . geesforgeks . org/python-remove-positional-rows/](https://www.geeksforgeeks.org/python-remove-positional-rows/)

给定一个矩阵，任务是编写一个 Python 程序来移除具有特定位置的行。

**示例:**

```py
Input: test_list = [[3, 5, 2], [1, 8, 9], 
                [5, 3, 1], [0, 1, 6], 
            [9, 4, 1], [1, 2, 10], 
            [0, 1, 2]]; idx_lis = [1, 2, 5]
Output: [[3, 5, 2], [0, 1, 6], [9, 4, 1], [0, 1, 2]]
Explanation: 1st, 2nd and 5th rows are removed.

Input: test_list = [[3, 5, 2], [1, 8, 9], 
             [5, 3, 1], [0, 1, 6], 
             [9, 4, 1], [1, 2, 10], 
             [0, 1, 2]]; idx_lis = [1, 3, 5]
Output: [[3, 5, 2], [5, 3, 1], [9, 4, 1], [0, 1, 2]]
Explanation: 1st, 3rd and 5th rows are removed.
```

**方法#1:使用** [**循环**](https://www.geeksforgeeks.org/loops-in-python/)**+**[**pop()**](https://www.geeksforgeeks.org/python-list-pop/)**+**[**反迭代**](https://www.geeksforgeeks.org/backward-iteration-in-python/)

在这种情况下，移除是使用 pop()处理的，并且需要反向迭代来确保由于删除时的重排，不会移除错误的位置行。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove positional rows
# Using loop + pop() + back iteration

# initializing list
test_list = [[3, 5, 2], [1, 8, 9], [5, 3, 1], 
             [0, 1, 6], [9, 4, 1], [1, 2, 10], 
             [0, 1, 2]]

# printing original list
print("The original list is: " + str(test_list))

# initializing indices
idx_lis = [1, 2, 5]

# back iteration
for idx in idx_lis[::-1]:

    # pop() used for removal
    test_list.pop(idx)

# printing result
print("Matrix after removal: " + str(test_list))
```

**输出:**

> 原始列表为:[[3，5，2]，[1，8，9]，[5，3，1]，[0，1，6]，[9，4，1]，[1，2，10]，[0，1，2]]
> 
> 移除后的矩阵:[[3，5，2]，[0，1，6]，[9，4，1]，[0，1，2]]

**方法二:使用** [**枚举()**](https://www.geeksforgeeks.org/enumerate-in-python/) **+** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

在这种情况下，我们不是按索引删除行，而是只添加不属于删除索引列表的行。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove positional rows
# Using enumerate() + list comprehension

# initializing list
test_list = [[3, 5, 2], [1, 8, 9], [5, 3, 1], 
             [0, 1, 6], [9, 4, 1], [1, 2, 10], 
             [0, 1, 2]]

# printing original list
print("The original list is: " + str(test_list))

# initializing indices
idx_lis = [1, 2, 5]

# using enumerate() to get index and value of each row
res = [sub[1] for sub in enumerate(test_list) if sub[0] not in idx_lis]

# printing result
print("Matrix after removal: " + str(res))
```

**输出:**

> 原始列表为:[[3，5，2]，[1，8，9]，[5，3，1]，[0，1，6]，[9，4，1]，[1，2，10]，[0，1，2]]
> 
> 移除后的矩阵:[[3，5，2]，[0，1，6]，[9，4，1]，[0，1，2]]