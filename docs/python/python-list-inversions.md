# Python |列表倒置

> 原文:[https://www.geeksforgeeks.org/python-list-inversions/](https://www.geeksforgeeks.org/python-list-inversions/)

有时，在编程时，我们会遇到一个问题，即我们可能需要在列表元素之间执行某些按位运算。这是一个必不可少的工具，因为我们会多次遇到按位运算。让我们讨论执行这项任务的某些方法。

**方法#1:使用`map() + lambda + "~" operator`**
以上功能可以组合执行此任务。我们可以使用 map()来累加 lambda 函数指定的反转逻辑的结果。

```
# Python3 code to demonstrate working of
# List Inversions
# Using map() + lambda + "~" operator

# initializing list
test_list = [7, 8, 9, 1, 10, 7]

# printing original list
print("The original list is : " + str(test_list))

# List Inversions
# Using map() + lambda + "~" operator
res = list(map(lambda x: ~x, test_list)) 

# printing result 
print("The Bitwise Inversions of list elements are : " + str(res))
```

**Output :**

```
The original list is : [7, 8, 9, 1, 10, 7]
The Bitwise Inversions of list elements are : [-8, -9, -10, -2, -11, -8]

```