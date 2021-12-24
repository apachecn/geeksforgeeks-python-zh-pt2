# Python |列表中的切片产品

> 原文:[https://www . geesforgeks . org/python-切片产品列表/](https://www.geeksforgeeks.org/python-sliced-product-in-list/)

访问列表中的元素有许多类型和变体。这些是 Python 编程的重要部分，人们必须知道如何执行同样的操作。本文讨论了获取初始 K 元素并进行乘法运算的方法。让我们讨论执行此任务的特定解决方案。
**方法#1:使用列表切片+循环**
这个问题可以在一行中执行，而不是使用 Python 提供的列表切片功能使用循环，然后使用循环来执行产品。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# Sliced Product in List
# using list slicing + loop

# getting Product
def prod(val) :
    res = 1
    for ele in val:
        res *= ele
    return res

# initializing list
test_list = [4, 5, 2, 6, 7, 8, 10]

# printing original list
print("The original list : " + str(test_list))

# initializing K
K = 5

# Sliced Product in List
# using list slicing + loop
res = prod(test_list[:K])

# print result
print("The first K elements product of list is : " + str(res))
```

**Output : **

```py
The original list : [4, 5, 2, 6, 7, 8, 10]
The first K elements product of list is : 1680
```

**方法 2:使用 islice() + loop**
内置的功能也可以用来执行这个特定的任务。islice 函数可用于获取切片列表，然后 prod()可用于执行产品。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# Sliced Product in List
# using islice() + loop
from itertools import islice

# getting Product
def prod(val) :
    res = 1
    for ele in val:
        res *= ele
    return res

# initializing list
test_list = [4, 5, 2, 6, 7, 8, 10]

# printing original list
print("The original list : " + str(test_list))

# initializing K
K = 5

# Sliced Product in List
# using islice() + loop
res = list(islice(test_list, 0, K))
res = prod(res)

# print result
print("The first K elements product of list is : " + str(res))
```

**Output : **

```py
The original list : [4, 5, 2, 6, 7, 8, 10]
The first K elements product of list is : 1680
```