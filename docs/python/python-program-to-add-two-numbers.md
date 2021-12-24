# Python 程序添加两个数字

> 原文:[https://www . geesforgeks . org/python-程序添加两个数字/](https://www.geeksforgeeks.org/python-program-to-add-two-numbers/)

给定两个数字 num1 和 num2。任务是编写一个 Python 程序来寻找这两个数字的加法。

**示例:**

```py
Input: num1 = 5, num2 = 3
Output: 8

Input: num1 = 13, num2 = 6
Output: 19
```

在下面添加两个数字的程序中，首先要求用户输入两个数字，然后使用 input()函数扫描输入并存储在变量 number1 和 number2 中。然后，使用算术运算符+将变量 number1 和 number2 相加，并将结果存储在变量 sum 中。

下面是添加两个数字的 Python 程序:

例 1:

```py
# Python3 program to add two numbers

num1 = 15
num2 = 12

# Adding two nos
sum = num1 + num2

# printing values
print("Sum of {0} and {1} is {2}" .format(num1, num2, sum))
```

输出:

```py
Sum of 15 and 12 is 27
```

**例 2:** 将用户输入的两个数字相加

```py
# Python3 program to add two numbers

number1 = input("First number: ")
number2 = input("\nSecond number: ")

# Adding two numbers
# User might also enter float numbers
sum = float(number1) + float(number2)

# Display the sum
# will print value in float
print("The sum of {0} and {1} is {2}" .format(number1, number2, sum))
```

输出:

```py
First number: 13.5 Second number: 1.54
The sum of 13.5 and 1.54 is 15.04
```