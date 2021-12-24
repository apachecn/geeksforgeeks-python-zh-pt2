# Python–从列表

中的第 Kth 索引排序

> 原文:[https://www . geesforgeks . org/python-sort-from-kth-index-in-list/](https://www.geeksforgeeks.org/python-sort-from-kth-index-in-list/)

给定一个元素列表，从列表的第 k 个索引执行排序。

> **输入** : test_list = [7，3，7，6，4，9]，K = 2
> 
> **输出**:【7，3，4，6，7，9】
> 
> **说明**:列表未排序到 3(第一个索引)，从第二个索引开始，排序。
> 
> **输入** : test_list = [5，4，3，2，1]，K= 3
> 
> **输出**:【5，4，3，1，2】
> 
> **说明**:只排序最后两个元素 1、2。

**方法#1:使用循环+列表切片**

这是执行这项任务的方法之一。在这种情况下，我们提取列表中 K 之前的每个元素，然后使用切片符号执行列表切片，并对提取的切片列表执行排序。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Perform sort from Kth index
# Using loop + list slicing

# initializing list
test_list = [8, 4, 7, 3, 2, 14, 6]

# printing original list
print("The original list : " + str(test_list))

# initializing K
K = 3

# Using loop + list slicing
res = []

# Using loop to extract elements till K
for idx, ele in enumerate(test_list):
    if idx < K:
        res.append(ele)

# join sorted and unsorted segments
res = res + sorted(test_list[K:])

# printing result
print("Partially sorted list : " + str(res))
```

**Output**

```
The original list : [8, 4, 7, 3, 2, 14, 6]
Partially sorted list : [8, 4, 7, 2, 3, 6, 14]
```

**方法 2:使用双列表切片**

这是我们执行这项任务的另一种方式。在这种情况下，我们执行列表切片任务，以便对非排序部分进行切片，并执行串联，从而提供一个线性替代方案来解决这个问题。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Perform sort from Kth index
# Using Using double List slicing

# initializing list
test_list = [8, 4, 7, 3, 2, 14, 6]

# printing original list
print("The original list : " + str(test_list))

# initializing K
K = 3

# Using loop + list slicing
res = []

# Using loop to extract elements till K
# Concatenating unsort and sorted part as one liner
res = test_list[:K] + sorted(test_list[K:])

# printing result
print("Partially sorted list : " + str(res))
```

**Output**

```
The original list : [8, 4, 7, 3, 2, 14, 6]
Partially sorted list : [8, 4, 7, 2, 3, 6, 14]
```