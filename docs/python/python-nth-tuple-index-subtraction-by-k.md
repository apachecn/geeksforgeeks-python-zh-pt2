# Python |第 n 元组索引减 K

> 原文:[https://www . geesforgeks . org/python-n 元组-索引-k 减/](https://www.geeksforgeeks.org/python-nth-tuple-index-subtraction-by-k/)

很多时候，在处理记录时，我们会遇到一个问题，那就是我们需要更改元组元素的值。这是使用元组时常见的问题。让我们讨论列表中元组的第 n 个元素可以减去 K 的某些方法。

**方法#1:使用循环**
使用循环可以执行该任务。在这种情况下，我们只需迭代列表，通过代码中的预定义值 K 来更改第 n 个元素。

```
# Python3 code to demonstrate working of
# Nth tuple element Subtraction by K
# Using loop

# Initializing list
test_list = [(4, 5, 6), (7, 4, 2), (9, 10, 11)]

# printing original list
print("The original list is : " + str(test_list))

# Initializing N 
N = 1

# Initializing K 
K = 3

# Nth tuple element Subtraction by K
# Using loop
res = []
for i in range(0, len(test_list)):
    res.append((test_list[i][0], test_list[i][N] - K, test_list[i][2]))

# printing result
print("The tuple after removing K from Nth element : " + str(res))
```

**Output :**

```
The original list is : [(4, 5, 6), (7, 4, 2), (9, 10, 11)]
The tuple after removing K from Nth element : [(4, 2, 6), (7, 1, 2), (9, 7, 11)]

```