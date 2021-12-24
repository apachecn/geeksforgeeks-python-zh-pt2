# Python–将列表中的连续元素相乘

> 原文:[https://www . geeksforgeeks . org/python-列表中多个连续元素/](https://www.geeksforgeeks.org/python-multiply-consecutive-elements-in-list/)

在使用 python 时，我们通常会遇到许多我们需要在日常工作和开发中解决的问题。特别是在开发中，python 的小任务希望只在一行中执行。我们讨论一些方法来计算一个由列表中连续乘积的元素组成的列表。

**方法#1:使用列表理解**
天真的方法可以用来执行，但是由于本文讨论了这个特定问题的一个线性解决方案，我们从列表理解作为执行这个任务的方法开始。

```py
# Python3 code to demonstrate 
# Consecutive Product list
# using list comprehension

# initializing list 
test_list = [1, 4, 5, 3, 6]

# printing original list 
print ("The original list is : " + str(test_list))

# using list comprehension
# Consecutive Product list
res = [test_list[i] * test_list[i + 1] for i in range(len(test_list)-1)]

# printing result
print ("The computed successive product list is : " + str(res))
```

**Output :**

```py
The original list is : [1, 4, 5, 3, 6]
The computed successive product list is : [4, 20, 15, 18]

```