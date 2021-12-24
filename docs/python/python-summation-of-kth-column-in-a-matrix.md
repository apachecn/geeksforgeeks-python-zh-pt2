# Python–矩阵中第 kth 列的求和

> 原文:[https://www . geeksforgeeks . org/python-矩阵中第 k 列求和/](https://www.geeksforgeeks.org/python-summation-of-kth-column-in-a-matrix/)

有时，在使用 Python Matrix 时，我们可能会遇到一个问题，即我们需要找到特定列的总和。这在日常编程和竞争性编程中可能有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`sum() + zip()`**
这个任务可以使用以上功能的组合来解决。在这种情况下，我们在 zip()中传递列表，以访问所有列，并使用 sum()获取列的总和。

```
# Python3 code to demonstrate working of
# Matrix Kth column summation
# using sum() + zip()

# initialize list
test_list = [[5, 6, 7],
            [9, 10, 2], 
            [10, 3, 4]]

# printing original list
print("The original list is : " + str(test_list))

# initialize K
K = 2

# Matrix Kth column summation
# using sum() + zip()
res = [sum(idx) for idx in zip(*test_list)][K] 

# printing result
print("Sum of Kth column is : " + str(res))
```

**Output :**

```
The original list is : [[5, 6, 7], [9, 10, 2], [10, 3, 4]]
Sum of Kth column is : 13

```