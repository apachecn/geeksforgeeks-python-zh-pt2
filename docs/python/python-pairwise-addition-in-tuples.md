# Python–元组中的成对加法

> 原文:[https://www . geesforgeks . org/python-成对元组加法/](https://www.geeksforgeeks.org/python-pairwise-addition-in-tuples/)

有时，在处理数据时，我们可能会遇到需要寻找累积结果的问题。这可以是任何类型、乘积或总和。这里我们将讨论相邻元素加法。让我们讨论执行这项任务的某些方法。

**方法一:使用 `zip()` +生成器表达式+`tuple()`+T3】**

上述功能的组合可用于执行该任务。在本文中，我们使用生成器表达式来提供加法逻辑，同时元素配对由 zip()完成。使用元组()将结果转换为元组形式。

```
# Python3 code to demonstrate working of
# Pairwise Addition in Tuples
# using zip() + generator expression + tuple

# initialize tuple
test_tup = (1, 5, 7, 8, 10)

# printing original tuple
print("The original tuple : " + str(test_tup))

# Pairwise Addition in Tuples
# using zip() + generator expression + tuple
res = tuple(i + j for i, j in zip(test_tup, test_tup[1:]))

# printing result
print("Resultant tuple after addition : " + str(res))
```

**Output :**

```
The original tuple : (1, 5, 7, 8, 10)
Resultant tuple after addition : (6, 12, 15, 18)

```

**方法 2:使用`tuple() + map()`+λ**

上述功能的组合也有助于执行此任务。在本文中，我们使用 lambda 函数执行加法和绑定逻辑。map()用于迭代每个元素，最终结果由 tuple()转换。

```
# Python3 code to demonstrate working of
# Pairwise Addition in Tuples
# using tuple() + map() + lambda

# initialize tuple
test_tup = (1, 5, 7, 8, 10)

# printing original tuple
print("The original tuple : " + str(test_tup))

# Pairwise Addition in Tuples
# using tuple() + map() + lambda
res = tuple(map(lambda i, j : i + j, test_tup[1:], test_tup[:-1]))

# printing result
print("Resultant tuple after addition : " + str(res))
```

**Output :**

```
The original tuple : (1, 5, 7, 8, 10)
Resultant tuple after addition : (6, 12, 15, 18)

```