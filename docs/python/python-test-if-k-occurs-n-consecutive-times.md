# Python–测试 K 是否连续出现 N 次

> 原文:[https://www . geesforgeks . org/python-test-if-k-occurs-n-continuous-times/](https://www.geeksforgeeks.org/python-test-if-k-occurs-n-consecutive-times/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们需要检查某个特定的数字是否连续出现了 N 次。这可以应用于许多领域，包括日常编程。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解**
这是一种可以执行该任务的方式。在本文中，我们迭代列表，并使用一行中的乘法运算符检查列表中的出现。

```
# Python3 code to demonstrate 
# Test if K occurs N consecutive times
# using list comprehension

# Initializing list
test_list = [1, 3, 4, 4, 4, 3, 3, 2, 2, 1]

# printing original list
print("The original list is : " + str(test_list))

# Initializing K 
K = 4

# Initializing N 
N = 3

# Test if K occurs N consecutive times
# using list comprehension
res = [K] * N in (test_list[i : i + N] for i in range(len(test_list) - N))

# printing result 
print ("Does K occur N consecutive times ? : " + str(res))
```

**Output :**

```
The original list is : [1, 3, 4, 4, 4, 3, 3, 2, 2, 1]
Does K occur N consecutive times ? : True

```