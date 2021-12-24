# Python 程序交换两个变量

> 原文:[https://www . geesforgeks . org/python-程序到交换-双变量/](https://www.geeksforgeeks.org/python-program-to-swap-two-variables/)

给定两个变量 x 和 y，编写一个 Python 程序来交换它们的值。让我们看看 Python 中完成这项任务的不同方法。

![python-swap-two-variable](img/d94b2d2c16a683cb3abb29a0544c29e1.png)

**方法 1:** 使用朴素方法
最朴素的方法是将一个变量(比如 x)的值存储在一个临时变量中，然后将变量 y 的值赋给变量 x，最后将临时变量的值赋给变量 y。

## 蟒蛇 3

```
# Python program to demonstrate
# swapping of two variables

x = 10
y = 50

# Swapping of two variables
# Using third variable
temp = x
x = y
y = temp

print("Value of x:", x)
print("Value of y:", y)
```

**Output**

```
Value of x: 50
Value of y: 10
```

**方法 2:** 使用逗号运算符
使用逗号运算符，变量的值可以交换，而无需使用第三个变量。

## 蟒蛇 3

```
# Python program to demonstrate
# swapping of two variables

x = 10
y = 50

# Swapping of two variables
# without using third variable
x, y = y, x

print("Value of x:", x)
print("Value of y:", y)
```

**Output**

```
Value of x: 50
Value of y: 10
```

**方法 3:** 使用异或
按位异或运算符可用于交换两个变量。两个数字 x 和 y 的异或运算返回一个数字，无论 x 和 y 的位在哪里不同，该数字的所有位都是 1。例如，10(二进制 1010)和 5(二进制 0101)的异或是 1111，7 (0111)和 5 (0101)的异或是(0010)。

## 蟒蛇 3

```
# Python program to demonstrate
# Swapping of two variables

x = 10
y = 50

# Swapping using xor
x = x ^ y
y = x ^ y
x = x ^ y

print("Value of x:", x)
print("Value of y:", y)
```

**Output**

```
Value of x: 50
Value of y: 10
```

**方法 4:** 使用算术运算符，我们可以通过两种方式执行交换。

*   **使用加减运算符:**

这个想法是得到两个给定数字中的一个的和。然后，可以使用求和和从求和中减去来交换数字。

## 蟒蛇 3

```
# Python program to demonstrate
# swapping of two variables

x = 10
y = 50

# Swapping of two variables
# using arithmetic operations
x = x + y  
y = x - y 
x = x - y

print("Value of x:", x)
print("Value of y:", y)
```

**Output**

```
Value of x: 50
Value of y: 10
```

*   **使用乘除运算符:**

这个想法是让两个给定的数字相乘。这些数字可以通过除法计算出来。

## 蟒蛇 3

```
# Python program to demonstrate
# swapping of two variables

x = 10
y = 50

# Swapping of two numbers
# Using multiplication operator

x = x * y
y = x / y
x = x / y

print("Value of x : ", x)
print("Value of y : ", y)
```

**Output**

```
Value of x :  50.0
Value of y :  10.0
```

**方法 5:** 使用按位加减进行交换。

## 蟒蛇 3

```
#Python program to demonstrate
#swapping of two numbers
a = 5
b = 1
a = (a & b) + (a | b)
b = a + (~b) + 1
a = a + (~b) + 1
print("a after swapping: ", a)
print("b after swapping: ", b)
```

**Output**

```
a after swapping:  1
b after swapping:  5
```