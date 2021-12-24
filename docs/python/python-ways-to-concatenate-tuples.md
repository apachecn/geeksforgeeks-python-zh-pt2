# Python |连接元组的方法

> 原文:[https://www . geesforgeks . org/python-连接元组的方法/](https://www.geeksforgeeks.org/python-ways-to-concatenate-tuples/)

很多时候，在处理记录时，我们可能会遇到一个问题，我们需要添加两个记录并将其存储在一起。这需要串联。由于元组是不可变的，这个任务变得不太复杂。让我们讨论执行这项任务的某些方法。

**方法#1:使用`+ operator`**
这是执行这个特殊任务最皮托尼克和推荐的方法。在这种情况下，我们添加两个元组并返回连接的元组。在此过程中，先前的元组不会改变。

```py
# Python3 code to demonstrate working of
# Ways to concatenate tuples
# using + operator

# initialize tuples
test_tup1 = (1, 3, 5)
test_tup2 = (4, 6)

# printing original tuples
print("The original tuple 1 : " + str(test_tup1))
print("The original tuple 2 : " + str(test_tup2))

# Ways to concatenate tuples
# using + operator
res = test_tup1 + test_tup2

# printing result
print("The tuple after concatenation is : " + str(res))
```

**Output :**

```py
The original tuple 1 : (1, 3, 5)
The original tuple 2 : (4, 6)
The tuple after concatenation is : (1, 3, 5, 4, 6)

```