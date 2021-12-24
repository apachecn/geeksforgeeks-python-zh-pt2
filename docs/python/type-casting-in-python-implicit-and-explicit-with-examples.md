# Python 中的类型转换(隐式和显式)示例

> 原文:[https://www . geeksforgeeks . org/python 中的类型转换-隐式-显式-带示例/](https://www.geeksforgeeks.org/type-casting-in-python-implicit-and-explicit-with-examples/)

**先决条件:** [Python 数据类型](https://www.geeksforgeeks.org/python-data-types/)

类型转换是为了用户需要执行的操作，将变量数据类型转换为某个数据类型的方法。在本文中，我们将看到各种类型转换技术。

Python 中可以有两种类型的类型铸造–

*   隐式类型铸造
*   显式铸造

## 隐式类型转换

在这种方法中，Python 自动将数据类型转换为另一种数据类型。在这个过程中，用户不必参与这个过程。

## 蟒 3

```
# Python program to demonstrate
# implicit type Casting

# Python automatically converts
# a to int
a = 7
print(type(a))

# Python automatically converts
# b to float
b = 3.0
print(type(b))

# Python automatically converts
# c to float as it is a float addition
c = a + b
print(c)
print(type(c))

# Python automatically converts
# d to float as it is a float multiplication
d = a * b
print(d)
print(type(d))
```

**输出:**

```
<class 'int'>
<class 'float'>
10.0
<class 'float'>
21.0
<class 'float'>
```

## 显式类型转换

在这种方法中，Python 需要用户参与将变量数据类型转换成特定的数据类型，以便进行所需的操作。

主要在类型铸造中可以用这些数据完成类型函数:

*   **Int ():** The int () function takes float or string as a parameter and returns an int object.
*   **float ():** The float () function takes int or string as a parameter and returns an object of type float.
*   **str ():** The str () function takes float or int as a parameter and returns a string object.

### 让我们看一些类型转换的例子:

**类型铸造 int 浮动:**

这里，我们使用 **float()** 函数将整数对象转换为 float 对象。

## 蟒 3

```
# Python program to demonstrate
# type Casting

# int variable
a = 5

# typecast to float
n = float(a)

print(n)
print(type(n))
```