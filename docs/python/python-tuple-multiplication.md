# Python |元组乘法

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python 元组-乘法/

有时，在处理记录时，我们可能会遇到一个问题，即我们可能需要执行元组乘法。这个问题可能发生在日常编程中。让我们讨论执行这项任务的某些方法。

**方法#1:使用 zip() +生成器表达式**
以上函数的组合可以用来执行这个任务。在本例中，我们使用生成器表达式执行乘法任务，每个元组的映射索引由 zip()完成。

```
# Python3 code to demonstrate working of
# Tuple multiplication
# using zip() + generator expression

# initialize tuples
test_tup1 = (10, 4, 5, 6)
test_tup2 = (5, 6, 7, 5)

# printing original tuples
print("The original tuple 1 : " + str(test_tup1))
print("The original tuple 2 : " + str(test_tup2))

# Tuple multiplication
# using zip() + generator expression
res = tuple(ele1 * ele2 for ele1, ele2 in zip(test_tup1, test_tup2))

# printing result
print("The multiplied tuple : " + str(res))
```

**Output :**

```
The original tuple 1 : (10, 4, 5, 6)
The original tuple 2 : (5, 6, 7, 5)
The multiplied tuple : (50, 24, 35, 30)

```