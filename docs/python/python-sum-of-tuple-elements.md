# Python–元组元素之和

> 原文:[https://www.geeksforgeeks.org/python-sum-of-tuple-elements/](https://www.geeksforgeeks.org/python-sum-of-tuple-elements/)

有时，在编程时，我们会遇到一个问题，即我们可能需要在元组元素之间执行求和。这是一个必不可少的工具，因为我们多次遇到求和操作，元组是不可变的，因此需要处理。让我们讨论执行这项任务的某些方法。

**方法#1:使用`list() + sum()`**
以上功能可以组合执行此任务。我们可以用 sum()来累加求和逻辑的结果。list()函数用于执行相互转换。

```
# Python3 code to demonstrate working of 
# Tuple summation
# Using list() + sum()

# initializing tup 
test_tup = (7, 8, 9, 1, 10, 7) 

# printing original tuple
print("The original tuple is : " + str(test_tup)) 

# Tuple elements inversions
# Using list() + sum()
res = sum(list(test_tup))

# printing result 
print("The summation of tuple elements are : " + str(res)) 
```

**Output :**

```
The original tuple is : (7, 8, 9, 1, 10, 7)
The summation of tuple elements are : 42

```