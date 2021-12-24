# Python |保留 K 前后元素

> 原文:[https://www . geesforgeks . org/python-retain-k-前后元素/](https://www.geeksforgeeks.org/python-retain-k-front-and-rear-elements/)

有时，我们要求通过删除列表的某些元素来缩小列表。用于执行该特定任务的方法之一是前后元件保持和其余元件的删除。这是一个很好的工具，它的解决方案可能是有用的。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表切片+ del 操作符**
del 操作符可以通过切片操作来删除列表中除前后元素之外的所有元素，从而获得列表的裁剪版本。

```py
# Python3 code to demonstrate 
# Retain K Front and Rear elements
# using del operator + list slicing

# initializing list 
test_list = [2, 3, 5, 7, 9, 10, 8, 6]

# printing original list
print ("The original list is : " + str(test_list))

# initializing K 
K = 2

# using del operator + list slicing
# Retain K Front and Rear elements 
N = len(test_list)
del test_list[K : N - K]

# printing result 
print ("The cropped list is : " + str(test_list))
```

**Output :**

```py
The original list is : [2, 3, 5, 7, 9, 10, 8, 6]
The cropped list is : [2, 3, 8, 6]

```