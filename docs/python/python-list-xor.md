# Python–列表异或

> 原文:[https://www.geeksforgeeks.org/python-list-xor/](https://www.geeksforgeeks.org/python-list-xor/)

有时，在编程时，我们会遇到一个问题，即我们可能需要在列表元素之间执行某些按位运算。这是一个必不可少的工具，因为我们会多次遇到按位运算。让我们讨论一下执行异或运算的某些方法。

**方法#1:使用`reduce() + lambda + “^” operator`**
以上功能可以组合执行此任务。我们可以使用 reduce()来累加λ函数指定的异或逻辑的结果。仅适用于 Python2。

```py
# Python code to demonstrate working of
# List XOR
# Using reduce() + lambda + "^" operator

# initializing list
test_list = [4, 6, 2, 3, 8, 9]

# printing original list
print("The original list is : " + str(test_list))

# List XOR
# Using reduce() + lambda + "^" operator
res = reduce(lambda x, y: x ^ y, test_list)

# printing result 
print("The Bitwise XOR of list elements are : " + str(res))
```

**Output :**

```py
The original list is : [4, 6, 2, 3, 8, 9]
The Bitwise XOR of list elements are : 2

```