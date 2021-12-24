# Python–多尺寸矩阵中的后柱

> 原文:[https://www . geesforgeks . org/python-多尺寸矩阵中的后柱/](https://www.geeksforgeeks.org/python-rear-column-in-multi-sized-matrix/)

给定具有可变长度行的矩阵，提取最后一列。

> **输入** : test_list = [[3，4，5]，[7]，[8，4，6]，[10，3]]
> **输出** : [5，7，6，3]
> **解释**:过滤行的最后一个元素。
> 
> **输入** : test_list = [[3，4，5]，[7]，[8，4，6]]
> **输出** : [5，7，6]
> **解释**:过滤行的最后一个元素。

**方法#1:使用循环**

这是一种解决这个问题的暴力方法，我们使用“-1”访问最后一个元素，对每一行进行迭代。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Rear column in Multisized Matrix
# Using loop

# initializing list
test_list = [[3, 4, 5], [7], [8, 4, 6, 1], [10, 3]]

# printing original list
print("The original list is : " + str(test_list))

res = []
for sub in test_list:

    # getting rear element using "-1"
    res.append(sub[-1])

# printing results
print("Filtered column : " + str(res))
```

**Output**

```py
The original list is : [[3, 4, 5], [7], [8, 4, 6, 1], [10, 3]]
Filtered column : [5, 7, 1, 3]

```

**方法 2:使用列表理解**

这是解决这个问题的另一种方法，在这种情况下，我们以类似的方式执行上述任务，只是作为一种速记。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Rear column in Multisized Matrix
# Using list comprehension

# initializing list
test_list = [[3, 4, 5], [7], [8, 4, 6, 1], [10, 3]]

# printing original list
print("The original list is : " + str(test_list))

# one-liner to solve this problem
res = [sub[-1] for sub in test_list]

# printing results
print("Filtered column : " + str(res))
```

**Output**

```py
The original list is : [[3, 4, 5], [7], [8, 4, 6, 1], [10, 3]]
Filtered column : [5, 7, 1, 3]

```