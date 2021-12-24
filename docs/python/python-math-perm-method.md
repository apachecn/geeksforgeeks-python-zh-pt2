# Python–math . perm()方法

> 原文:[https://www.geeksforgeeks.org/python-math-perm-method/](https://www.geeksforgeeks.org/python-math-perm-method/)

**Python 中的数学模块**包含许多数学运算，使用该模块可以轻松执行。`***math.perm()***`Python 中的方法用于获取 n 个项目中不重复、有顺序地选择 k 个项目的方式数。评估为 *n！/(n–k)！*当 *k < = n* 且当 *k > n* 时评估为 0。
这个方法在 Python 版本中是新的。

> **语法:** math.perm(n，k =无)
> 
> **参数:**
> **n** :非负整数
> **k** :非负整数。如果未指定 k，则默认为无
> 
> **返回:**一个整数值，代表从 n 个项目中不重复、有顺序地选择 k 个项目的方式数。如果 k 为 none，则方法返回 n！。

**代码#1:** 使用`***math.perm()***`方法

```py
# Python Program to explain math.perm() method

# Importing math module
import math

n = 10
k = 2

# Get the number of ways to choose
# k items from n items without
# repetition and with order
nPk = math.perm(n, k)
print(nPk)

n = 5
k = 3

# Get the number of ways to choose
# k items from n items without
# repetition and with order
nPk = math.perm(n, k)
print(nPk)
```

**Output:**

```py
90
60

```

**代码#2:** 当 k > n

```py
# Python Program to explain math.perm() method

# Importing math module
import math

# When k > n 
# math.perm(n, k) returns 0.
n = 3
k = 5

# Get the number of ways to choose
# k items from n items without
# repetition and with order
nPk = math.perm(n, k)
print(nPk)
```

**Output:**

```py
0

```

**代码#3:** 如果未指定 k

```py
# Python Program to explain math.perm() method

# Importing math module
import math

# When k is not specified
# It defaults to n and 
# math.perm(n, k) returns n ! n = 5

nPk = math.perm(n)
print(nPk)
```

**Output:**

```py
120

```

**参考:** [Python 数学库](https://docs.python.org/3/library/math.html#math.perm)