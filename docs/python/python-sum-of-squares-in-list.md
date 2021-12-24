# Python |列表中的平方和

> 原文:[https://www . geesforgeks . org/python-列表中的平方和/](https://www.geeksforgeeks.org/python-sum-of-squares-in-list/)

Python 作为魔术师的语言，可以用来以一种简单而简洁的方式执行许多繁琐而重复的任务，拥有充分利用这种工具的知识总是有用的。一个这样的小应用程序可以在一行中找到列表的平方和。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`reduce()`+lambda**
lambda 函数在一行中执行冗长任务的能力，允许它与用于累积子问题的 reduce 相结合来执行该任务。仅适用于 Python 2。

```py
# Python code to demonstrate  
# sum of squares 
# using reduce() + lambda

# initializing list
test_list = [3, 5, 7, 9, 11]

# printing original list 
print ("The original list is : " + str(test_list))

# using reduce() + lambda
# sum of squares 
res = reduce(lambda i, j: i + j * j, [test_list[:1][0]**2]+test_list[1:])

# printing result
print ("The sum of squares of list is : " + str(res))
```

**Output :**

```py
The original list is : [3, 5, 7, 9, 11]
The sum of squares of list is : 285

```