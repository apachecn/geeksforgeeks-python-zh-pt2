# Python |列表列表中第 kth 列的乘积

> 原文:[https://www . geesforgeks . org/python-产品列表中的第 k 列/](https://www.geeksforgeeks.org/python-product-of-kth-column-in-list-of-lists/)

有时，在使用 Python Matrix 时，我们可能会遇到一个问题，即我们需要找到特定列的乘积。这在日常编程和竞争性编程中可能有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `zip()`**
这个任务可以使用以上功能的组合来解决。在这种情况下，我们在 zip()中传递列表，以访问所有列，并显式地使用 product 函数来获取列的乘积。

```
# Python3 code to demonstrate working of
# Column Product in List of Lists
# using loop + zip()

# getting Product
def prod(val) :
    res = 1 
    for ele in val:
        res *= ele
    return res 

# initialize list
test_list = [[5, 6, 7],
            [9, 10, 2], 
            [10, 3, 4]]

# printing original list
print("The original list is : " + str(test_list))

# initialize K
K = 2

# Column Product in List of Lists
# using loop + zip()
res = [prod(idx) for idx in zip(*test_list)][K] 

# printing result
print("Product of Kth column is : " + str(res))
```

**Output :**

```
The original list is : [[5, 6, 7], [9, 10, 2], [10, 3, 4]]
Product of Kth column is : 56

```