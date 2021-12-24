# Python |元组列表中的位置求和

> 原文:[https://www . geesforgeks . org/python-元组列表中的位置求和/](https://www.geeksforgeeks.org/python-position-summation-in-list-of-tuples/)

有时，我们收到的数据是元组的形式，包含来自不同来源的数据，我们通常会有一个用例，在这个用例中，我们需要处理元组的每个索引的总和以进行累积。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解**
这是执行这个特定任务最天真的方法，在这个方法中我们计算元组的所有可能索引的每个索引的总和。

```py
# Python3 code to demonstrate 
# position summation in list of tuples
# using list comprehension

# initializing list 
test_list = [(1, 6), (3, 4), (5, 8)]

# printing original list 
print ("The original list is : " + str(test_list))

# position Summation in List of Tuples
# using list comprehension
res = sum(i[0] for i in test_list), sum(i[1] for i in test_list)

# printing summation
print ("The position summation of tuples  : " + str(res))
```

**输出:**

```py
The original list is : [(1, 6), (3, 4), (5, 8)]
The position summation of tuples  : (9, 18)

```

**方法 2:使用`zip() + sum()`**
这是执行这一特定任务最优雅、最具腐解性的方式。在这种情况下，我们使用`zip()`组合元素的所有指数，并使用和函数组合求和的性能。

```py
# Python3 code to demonstrate 
# position summation in list of tuples
# using zip() + sum()

# initializing list 
test_list = [(1, 6), (3, 4), (5, 8)]

# printing original list 
print ("The original list is : " + str(test_list))

# position Summation in List of Tuples
# using zip() + sum()
res = [sum(i) for i in zip(*test_list)]

# printing summation
print ("The position summation of tuples  : " + str(res))
```

**输出:**

```py
The original list is : [(1, 6), (3, 4), (5, 8)]
The position summation of tuples  : [9, 18]

```