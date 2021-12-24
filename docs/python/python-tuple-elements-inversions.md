# Python–元组元素反转

> 原文:[https://www . geesforgeks . org/python-tuple-elements-inversion/](https://www.geeksforgeeks.org/python-tuple-elements-inversions/)

有时，在编程时，我们会遇到一个问题，即我们可能需要在元组元素之间执行某些按位运算。这是一个必不可少的工具，因为我们会多次遇到按位运算。让我们讨论执行这项任务的某些方法。

**方法#1:使用`map() + list() + tuple() + lambda + "~" operator`**
以上功能可以组合执行此任务。我们可以使用 map()来累加 lambda 函数指定的反转逻辑的结果。list()和 tuple()函数用于执行相互转换。

```py
# Python3 code to demonstrate working of 
# Tuple elements inversions
# Using map() + list() + tuple() + lambda + "~" operator 

# initializing tup 
test_tup = (7, 8, 9, 1, 10, 7) 

# printing original tuple
print("The original tuple is : " + str(test_tup)) 

# Tuple elements inversions
# Using map() + list() + tuple() + lambda + "~" operator 
res = tuple(list(map(lambda x: ~x, list(test_tup)))) 

# printing result 
print("The Bitwise Inversions of tuple elements are : " + str(res)) 
```

**Output :**

```py
The original tuple is : (7, 8, 9, 1, 10, 7)
The Bitwise Inversions of tuple elements are : (-8, -9, -10, -2, -11, -8)

```