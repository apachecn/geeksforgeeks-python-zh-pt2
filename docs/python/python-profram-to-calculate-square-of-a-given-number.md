# Python 程序计算给定数字的平方

> 原文:[https://www . geesforgeks . org/python-profiram-计算给定数字的平方/](https://www.geeksforgeeks.org/python-profram-to-calculate-square-of-a-given-number/)

给定一个数字，任务是编写一个 Python 程序来计算给定数字的平方。

**示例:**

```
Input: 4
Output: 16

Input: 3
Output: 9

Input: 10
Output: 100
```

我们将提供这个数字，我们将得到这个数字的平方作为输出。我们有三种方法可以做到这一点:

*   将数字相乘得到平方 **(N * N)**
*   使用指数算子
*   使用数学幂()方法

**方法一:乘法**

在这种方法中，我们将把这个数乘以另一个数，得到这个数的平方。

**示例:**

## 蟒蛇 3

```
# Declaring the number.
n = 4

# Finding square by multiplying them
# with each other
square = n * n

# Printing square
print(square)
```

**输出:**

```
16
```

**方法二:使用指数算子**

在这种方法中，我们使用指数算子来求数字的平方。

> **指数运算符:** **
> 
> **返回:** a ** b 将 a 升到 b 次方返回作为输出。

**示例:**

## 蟒蛇 3

```
# Declaring the number.
n = 4

# Finding square by using exponent operator
# This will yield n power 2 i.e. square of n
square = n ** 2

# Printing square
print(square)
```

**输出:**

```
16
```

**方法三:使用 pow()方法**

在这种方法中，我们将使用 pow()方法来求数字的平方。该函数计算 x**y，并返回一个浮点值作为输出。

> **语法:**浮点幂(x，y)
> 
> **参数:**
> 
> **x :** 必须计算其幂的数。
> 
> **y :** 提升到计算能力的值。
> 
> **返回值:**
> 以浮点形式返回 x**y 值。

**示例:**

## 蟒蛇 3

```
# Declaring the number.
n = 4

# Finding square by using pow method
# This will yield n power 2 i.e. square of n
square = pow(n, 2)

# Printing square
print(square)
```

**输出:**

```
16.0
```