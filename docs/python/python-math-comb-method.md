# Python–math . comb()方法

> 原文:[https://www.geeksforgeeks.org/python-math-comb-method/](https://www.geeksforgeeks.org/python-math-comb-method/)

**Python 中的数学模块**包含许多数学运算，使用该模块可以轻松执行。`***math.comb()***`Python 中的方法用于获取 n 个项目中不重复、不排序地选择 k 个项目的方式数。基本评价为 *n！/ (k！*(n–k)！)*当 k n .它也被称为二项式系数，因为它相当于表达式(1 + x) <sup>n</sup> 的多项式展开中的第 k 项系数。
这个方法在 Python 版本中是新的。

> **语法:** math.comb(n，k)
> 
> **参数:**
> **n** :非负整数
> **k** :非负整数
> 
> **返回:**一个整数值，表示从 n 个项目中不重复、不排序地选择 k 个项目的方式数。

**代码#1:** 使用`***math.comb()***`方法

```
# Python Program to explain math.comb() method

# Importing math module
import math

n = 10
k = 2

# Get the number of ways to choose
# k items from n items without
# repetition and without order
nCk = math.comb(n, k)
print(nCk)

n = 5
k = 3

# Get the number of ways to choose
# k items from n items without
# repetition and without order
nCk = math.comb(n, k)
print(nCk)
```

**Output:**

```
45
10

```

**代码#2:** 当 k > n

```
# Python Program to explain math.comb() method

# Importing math module
import math

# When k > n 
# math.comb(n, k) returns 0.
n = 3
k = 5

# Get the number of ways to choose
# k items from n items without
# repetition and without order
nCk = math.comb(n, k)
print(nCk)
```

**Output:**

```
0

```

**代码#3:** 使用`***math.comb()***`方法求表达式(1 + x) <sup>n</sup> 二项式展开式中第 k 项的系数

```
# Python Program to explain math.comb() method

# Importing math module
import math

n = 5
k = 2

# Find the coefficient of k-th
# term in the expansion of 
# expression (1 + x)^n
nCk = math.comb(n, k)
print(nCk)

n = 8
k = 3

# Find the coefficient of k-th
# term in the expansion of 
# expression (1 + x)^n
nCk = math.comb(n, k)
print(nCk)
```

**Output:**

```
10
56

```

**参考:** [Python 数学库](https://docs.python.org/3/library/math.html#math.comb)