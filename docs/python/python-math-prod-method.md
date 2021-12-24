# Python–math . prod()方法

> 原文:[https://www.geeksforgeeks.org/python-math-prod-method/](https://www.geeksforgeeks.org/python-math-prod-method/)

**Python 中的数学模块**包含许多数学运算，使用该模块可以轻松执行。Python 中的`***math.prod()***`方法用于计算给定*可迭代*中存在的所有元素的乘积。Python 中的大多数内置容器，比如 list、tuple，都是可迭代的。iterable 必须包含数值，否则非数值类型可能会被拒绝。
这个方法在 Python 版本中是新的。

> **语法:** math.prod(可迭代，* start = 1)
> 
> **参数:**
> **可迭代**:包含数值
> **start** 的可迭代:代表起始值的整数。start 是一个命名(仅关键字)参数，其默认值为 1。
> 
> **返回:**给定可迭代表中所有元素的计算乘积。

**代码#1:** 使用`***math.prod()***`方法

```
# Python Program to explain math.prod() method

# Importing math module
import math

# list
arr = [1, 2, 3, 4, 5]

# Calculate the product of
# of all elements present
# in the given list
product = math.prod(arr)
print(product)

# tuple
tup = (0.5, 0.6, 0.7)

# Calculate the product 
# of all elements present
# in the given tuple
product = math.prod(tup)
print(product)

# range
seq = range(1, 11)

# Calculate the product 
# of all elements present
# in the given range
product = math.prod(seq)
print(product)

# As the start value is not specified 
# it will default to 1
```

**Output:**

```
120
0.21
3628800

```

**代码#2:** 如果明确指定了开始参数

```
# Python Program to explain math.prod() method

# Importing math module
import math

# By default start value is 1
# but can be explicitly provided
# as a named (keyword-only) parameter

# list
arr = [1, 2, 3, 4, 5]

# Calculate the product of
# of all elements present
# in the given list
product = math.prod(arr, start = 2)
print(product)
```

**Output:**

```
240

```

**代码#3:** 当给定的可重复项为空时

```
# Python Program to explain math.prod() method

# Importing math module
import math

# If the given input iterable
# is empty, then this method
# returns the start value 

# list
arr = []

# Calculate the product of
# of all elements present
# in the given list
product = math.prod(arr)
print(product)

# Tuple
tup = ()

# Calculate the product of
# of all elements present
# in the given tuple
product = math.prod(tup, start = 5)
print(product)
```

**Output:**

```
1
5

```

**参考:** [Python 数学库](https://docs.python.org/3/library/math.html#math.prod)