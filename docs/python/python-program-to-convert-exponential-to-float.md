# Python 程序将指数转换为浮点

> 原文:[https://www . geesforgeks . org/python-程序到转换-指数到浮点/](https://www.geeksforgeeks.org/python-program-to-convert-exponential-to-float/)

给定一个指数格式的数字，任务是编写一个 Python 程序，将数字从指数格式转换为浮点数。指数是一种表示数字的方式。

**例:**

```
Input: 1.900000e+01
Output: 19.0

Input: 2.002000e+03
Output: 2002.0

Input: 1.101020e+05
Output: 110102.0
```

**进场:**

*   首先，我们将声明一个指数，并将其保存在一个变量中。
*   然后我们将使用 [**float()函数**](https://www.geeksforgeeks.org/float-in-python/) 将其转换为 float 数据类型。
*   然后我们将打印转换后的号码。

**语法:**

```
float(x)
```

**float()方法**用于从数字或字符串中返回浮点数。

**例:**

## 蟒 3

```
# Python program to convert exponential to float

# Declaring the exponential number
exp_number = "{:e}".format(110102)

# Converting it to float data type
float_number = float(exp_number)

# Printing the converted number
print("Exponent Number:",exp_number)
print("Float Number:",float_number)
```

**输出:**

```
Exponent Number: 1.101020e+05
Float Number: 110102.0
```