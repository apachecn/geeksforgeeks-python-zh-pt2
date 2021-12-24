# Python |矩阵第 n 列最大/最小值

> 原文:[https://www . geesforgeks . org/python-max-min-value-in-n-column-in-matrix/](https://www.geeksforgeeks.org/python-max-min-value-in-nth-column-in-matrix/)

有时，在使用 Python Matrix 时，我们可能会遇到一个问题，即我们需要找到特定列的最小值和最大值。这在日常编程和竞争性编程中可能有应用。让我们讨论一下执行这项任务的具体方法。

**方法:使用`max()/min()`+ `zip()`+**
这个任务可以使用以上功能的组合来解决。在这种情况下，我们在 zip()中传递列表，以访问所有列并`max()/min()`获取最大或最小列。

```
# Python3 code to demonstrate working of
# Max value in Nth Column in Matrix
# using max() + zip()

# initialize list
test_list = [[5, 6, 7],
             [9, 10, 2], 
             [10, 3, 4]]

# printing original list
print("The original list is : " + str(test_list))

# initialize N 
N = 2

# Max value in Nth Column in Matrix
# using max() + zip()
res = [max(i) for i in zip(*test_list)][N] 

# printing result
print("Max value of Nth column is : " + str(res))
```

**Output :**

```
The original list is : [[5, 6, 7], [9, 10, 2], [10, 3, 4]]
Max value of Nth column is : 7

```