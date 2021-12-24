# Python–元组的并集

> 原文:[https://www.geeksforgeeks.org/python-union-of-tuples/](https://www.geeksforgeeks.org/python-union-of-tuples/)

有时，在处理元组时，我们会遇到一个问题，即我们需要两个记录的并集。这种类型的应用可以出现在数据科学领域。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用集合()+“+”运算符**
该任务可以使用集合上+运算符提供的并集功能来执行。到 set 的转换由 set()完成。

```py
# Python3 code to demonstrate working of
# Union of Tuples
# Using set() + "+" operator

# initialize tuples
test_tup1 = (3, 4, 5, 6)
test_tup2 = (5, 7, 4, 10)

# printing original tuples
print("The original tuple 1 : " + str(test_tup1))
print("The original tuple 2 : " + str(test_tup2))

# Union of Tuples
# Using set() + "+" operator
res = tuple(set(test_tup1 + test_tup2))

# printing result
print("The union elements from tuples are : " + str(res))
```

**Output : **

```py
The original tuple 1 : (3, 4, 5, 6)
The original tuple 2 : (5, 7, 4, 10)
The union elements from tuples are : (3, 4, 5, 6, 7, 10)

```

**方法#2:使用 union() + set()**
这是一个类似于上面方法的方法，不同的是，我们使用内置函数来执行过滤不同元素的任务，而不是+运算符。

```py
# Python3 code to demonstrate working of
# Union of Tuples
# Using union() + set()

# initialize tuples
test_tup1 = (3, 4, 5, 6)
test_tup2 = (5, 7, 4, 10)

# printing original tuples
print("The original tuple 1 : " + str(test_tup1))
print("The original tuple 2 : " + str(test_tup2))

# Union of Tuples
# Using union() + set()
res = tuple(set(test_tup1).union(set(test_tup2)))

# printing result
print("The union elements from tuples are : " + str(res))
```

**Output : **

```py
The original tuple 1 : (3, 4, 5, 6)
The original tuple 2 : (5, 7, 4, 10)
The union elements from tuples are : (3, 4, 5, 6, 7, 10)

```