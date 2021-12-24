# Python 程序将两个整数值连接成一个

> 原文:[https://www . geesforgeks . org/python-program-to-concatenate-two-integer-values-in-one/](https://www.geeksforgeeks.org/python-program-to-concatenate-two-integer-values-into-one/)

给定两个整数 a 和 b，任务是将这两个整数连接成一个整数。

**示例:**

```
Input : a = 806, b = 91
Output : 80691

Input : a = 5, b = 1091
Output : 51091

```

**方法 1:** 实现这一点的一种方法可以是计算第二个数字的位数。然后将第一个数字与 10^digits 相乘，并将两个数字相加。下面是实现。

```
# Python program to concatenate
# two numbers

def numConcat(num1, num2):

     # find number of digits in num2
     digits = len(str(num2))

     # add zeroes to the end of num1
     num1 = num1 * (10**digits)

     # add num2 to num1
     num1 += num2

     return num1

# Driver's code
a = 906
b = 91
print(numConcat(a, b))
```

**Output:**

```
90691

```

**方法 2:** 另一种方法是将两个数字都转换成字符串。然后将它们连接起来并转换回整数。下面是实现。

```
# Python program to concatenate
# two numbers

def numConcat(num1, num2):

        # Convert both the numbers to
        # strings
        num1 = str(num1)
        num2 = str(num2)

        # Concatenate the strings
        num1 += num2

        return int(num1)

# Driver's code
a = 906
b = 91
print(numConcat(a, b))
```

**输出:**

```
90691

```