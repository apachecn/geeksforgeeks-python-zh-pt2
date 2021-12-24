# 从正方形矩阵中移除第一对角线元素的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-remove-first-对角元素-从正方形矩阵中删除/](https://www.geeksforgeeks.org/python-program-to-remove-first-diagonal-elements-from-a-square-matrix/)

给定一个 N*N 维的正方形矩阵，任务是编写一个 Python 程序来移除第一条对角线。

**示例:**

> **输入:** test_list = [[5，3，3，2，1]，[5，6，7，8，2]，[9，3，4，6，7]，[0，1，2，3，5]，[2，5，4，3，5]]
> 
> **输出:** [[3，3，2，1]，[5，7，8，2]，[9，3，6，7]，[0，1，2，5]，[2，5，4，3]]
> 
> **解释:**从列表中删除了 5、6、4、3、5，第 1 条对角线。
> 
> **输入:** test_list = [[5，3，3，2]，[5，6，7，8]，[9，3，4，6]，[0，1，2，3]]
> 
> **输出:** [[3，3，2]，[5，7，8]，[9，3，6]，[0，1，2]]
> 
> **解释:**从列表中删除了 5、6、4、3，第 1 条对角线。

**方法 1 :** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/) *和* [*枚举()*](https://www.geeksforgeeks.org/enumerate-in-python/)

在这种情况下，我们使用循环遍历每一行，并将元素的索引与行号进行比较，如果发现相等，则省略该元素。

**程序:**

## 蟒蛇 3

```py
# initializing list
test_list = [[5, 3, 3, 2, 1], [5, 6, 7, 8, 2], [
    9, 3, 4, 6, 7], [0, 1, 2, 3, 5], [2, 5, 4, 3, 5]]

# printing original list
print("The original list is : " + str(test_list))

res = []
for idx, ele in enumerate(test_list):

    # removing element whose index is equal to row index
    res.append([el for idxx, el in enumerate(ele) if idxx != idx])

# printing result
print("Filtered Matrix : " + str(res))
```

**输出:**

> 原来的名单是:[[5，3，3，2，1]，[5，6，7，8，2]，[9，3，4，6，7]，[0，1，2，3，5]，[2，5，4，3，5]]
> 
> 过滤矩阵:[[3，3，2，1]，[5，7，8，2]，[9，3，6，7]，[0，1，2，5]，[2，5，4，3]]

**方法二:** *使用* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) *和* [*枚举()*](https://www.geeksforgeeks.org/enumerate-in-python/)

在本文中，我们使用列表理解来执行迭代任务，为上述方法提供了一个线性解。

**程序:**

## 蟒蛇 3

```py
# initializing list
test_list = [[5, 3, 3, 2, 1], [5, 6, 7, 8, 2], [
    9, 3, 4, 6, 7], [0, 1, 2, 3, 5], [2, 5, 4, 3, 5]]

# printing original list
print("The original list is : " + str(test_list))

# list comprehension to perform task as one liner
res = [[el for idxx, el in enumerate(ele) if idxx != idx]
       for idx, ele in enumerate(test_list)]

# printing result
print("Filtered Matrix : " + str(res))
```

**输出:**

> 原来的名单是:[[5，3，3，2，1]，[5，6，7，8，2]，[9，3，4，6，7]，[0，1，2，3，5]，[2，5，4，3，5]]
> 
> 过滤矩阵:[[3，3，2，1]，[5，7，8，2]，[9，3，6，7]，[0，1，2，5]，[2，5，4，3]]