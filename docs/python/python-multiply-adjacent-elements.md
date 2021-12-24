# Python |相乘相邻元素

> 原文:[https://www . geesforgeks . org/python-乘法-相邻元素/](https://www.geeksforgeeks.org/python-multiply-adjacent-elements/)

有时，在处理数据时，我们可能会遇到需要寻找累积结果的问题。这可以是任何类型、乘积或总和。这里我们将讨论相邻元素乘法。让我们讨论执行这项任务的某些方法。

**方法#1:使用`zip()` +生成器表达式+ `tuple()`**
上述功能的组合可用于执行该任务。在这种情况下，我们使用生成器表达式来提供乘法逻辑，同时元素配对由`zip()`完成。使用`tuple()`将结果转换为元组形式。

```
# Python3 code to demonstrate working of
# Adjacent element multiplication
# using zip() + generator expression + tuple

# initialize tuple
test_tup = (1, 5, 7, 8, 10)

# printing original tuple
print("The original tuple : " + str(test_tup))

# Adjacent element multiplication
# using zip() + generator expression + tuple
res = tuple(i * j for i, j in zip(test_tup, test_tup[1:]))

# printing result
print("Resultant tuple after multiplication : " + str(res))
```

**Output :**

```
The original tuple : (1, 5, 7, 8, 10)
Resultant tuple after multiplication : (5, 35, 56, 80)

```