# Python–元组元素的模

> 原文:[https://www . geeksforgeeks . org/python-元组元素模/](https://www.geeksforgeeks.org/python-modulo-of-tuple-elements/)

有时，在处理记录时，我们可能会遇到一个问题，即我们可能需要对元组执行模运算。这个问题可能发生在日常编程中。让我们讨论执行这项任务的某些方法。

**方法#1:使用`zip()` +生成器表达式**
以上功能的组合可用于执行该任务。在这种情况下，我们使用生成器表达式执行取模任务，每个元组的映射索引由 zip()完成。

```py
# Python3 code to demonstrate working of
# Tuple modulo
# using zip() + generator expression

# initialize tuples
test_tup1 = (10, 4, 5, 6)
test_tup2 = (5, 6, 7, 5)

# printing original tuples
print("The original tuple 1 : " + str(test_tup1))
print("The original tuple 2 : " + str(test_tup2))

# Tuple modulo
# using zip() + generator expression
res = tuple(ele1 % ele2 for ele1, ele2 in zip(test_tup1, test_tup2))

# printing result
print("The modulus tuple : " + str(res))
```

**Output :**

```py
The original tuple 1 : (10, 4, 5, 6)
The original tuple 2 : (5, 6, 7, 5)
The modulus tuple : (0, 4, 5, 1)

```