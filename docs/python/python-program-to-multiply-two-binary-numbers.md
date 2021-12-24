# 两个二进制数相乘的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序-二进制数乘二/](https://www.geeksforgeeks.org/python-program-to-multiply-two-binary-numbers/)

给定两个二进制数，任务是编写一个 Python 程序将两个数相乘。

**示例:**

```py
firstnumber = 110
secondnumber = 10
Multiplication Result = 1100
```

我们可以使用 python 以两种方式将两个二进制数相乘，它们是:

1.  使用 bin()函数和
2.  不使用预定义的函数

## **方法 1:使用仓功能**

现在，让我们使用预定义函数编写一个程序:

## 蟒蛇 3

```py
firstnumber = 110
secondnumber = 10

firstnumber = str(firstnumber)
secondnumber = str(secondnumber)

Multiplication = int(firstnumber, 2) * int(secondnumber, 2)
binaryMul = bin(Multiplication)

print("\nResult = " + binaryMul)
```

**输出:**

```py
Result = 0b1100
```

## **方法 2:不使用任何预定义函数**

我们也可以在不使用任何预定义函数或用户定义函数的情况下，将任意两个二进制数相乘。

## 计算机编程语言

```py
def binaryProduct(binaryOne, binaryTwo):
    i = 0
    remainder = 0
    sum = []
    binaryProd = 0

    # if firstBinary number or second Binary number is not
    # zero then calculate the product of two Binary numbers
    while binaryOne != 0 or binaryTwo != 0:
        sum.insert(i, (((binaryOne % 10) + (binaryTwo % 10) + remainder) % 2))
        remainder = int(((binaryOne % 10) + (binaryTwo % 10) + remainder) / 2)
        binaryOne = int(binaryOne/10)
        binaryTwo = int(binaryTwo/10)
        i = i+1

    # if remainder value is not equal to
    # zero then insert the digit to sum array
    if remainder != 0:
        sum.insert(i, remainder)
        i = i+1
    i = i-1
    while i >= 0:
        binaryProd = (binaryProd * 10) + sum[i]
        i = i-1
    return binaryProd

binaryMultiply = 0
factor = 1
firstBinary = 110

secondBinary = 10

# Now check if secondbinary number have any
# digit or not and continue multiplying
# each digit of the second binary number with
# first binary number till the last digit of
# second binary number
while secondBinary != 0:
    digit = secondBinary % 10
    if digit == 1:
        firstBinary = firstBinary * factor
        binaryMultiply = binaryProduct(firstBinary, binaryMultiply)
    else:
        firstBinary = firstBinary * factor
    secondBinary = int(secondBinary/10)
    factor = 10
print("\nMultiplication Result = " + str(binaryMultiply))
```

**输出:**

```py
Multiplication Result = 1100
```