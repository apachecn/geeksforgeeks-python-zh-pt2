# Python 程序将二进制转换为十六进制

> 原文:[https://www . geesforgeks . org/python-程序到转换-二进制到十六进制/](https://www.geeksforgeeks.org/python-program-to-convert-binary-to-hexadecimal/)

给定一个二进制数，任务是编写一个 Python 程序，将给定的二进制数转换成等价的十六进制数。即将基值为 2 的数字转换为基值 16。在十六进制表示法中，我们用 16 个值来表示一个数。数字 0-9 用数字 0-9 表示，10-15 用 A–f 的字符表示

**示例:**

```py
Input:  1111
Output: F

Input: 110101
Output: 35

Input: 100001111
Output: 10F
```

### 方法 1:将二进制转换为十六进制的用户定义代码

**第一步:**输入二进制数。

```py
Input: 111101111011
```

**第二步:**将你的二进制数分成四组，从右开始。

```py
111101111011 = (1111)(0111)(1011)
```

**第三步:**将一组 4 位二进制数转换为一个十六进制数。

```py
(1111)(0111)(1011) = F7B
```

**下面是上述方法的 Python 实现:**

## 蟒蛇 3

```py
# Python code to convert binary number
# into hexadecimal number

# function to convert
# binary to hexadecimal

def binToHexa(n):
    bnum = int(n)
    temp = 0
    mul = 1

    # counter to check group of 4
    count = 1

    # char array to store hexadecimal number
    hexaDeciNum = ['0'] * 100

    # counter for hexadecimal number array
    i = 0
    while bnum != 0:
        rem = bnum % 10
        temp = temp + (rem*mul)

        # check if group of 4 completed
        if count % 4 == 0:

            # check if temp < 10
            if temp < 10:
                hexaDeciNum[i] = chr(temp+48)
            else:
                hexaDeciNum[i] = chr(temp+55)
            mul = 1
            temp = 0
            count = 1
            i = i+1

        # group of 4 is not completed
        else:
            mul = mul*2
            count = count+1
        bnum = int(bnum/10)

    # check if at end the group of 4 is not
    # completed
    if count != 1:
        hexaDeciNum[i] = chr(temp+48)

    # check at end the group of 4 is completed
    if count == 1:
        i = i-1

    # printing hexadecimal number
    # array in reverse order
    print("\n Hexadecimal equivalent of {}:  ".format(n), end="")
    while i >= 0:
        print(end=hexaDeciNum[i])
        i = i-1

# Driver code
if __name__ == '__main__':
    binToHexa('1111')
    binToHexa('110101')
    binToHexa('100001111')
    binToHexa('111101111011')
```

**输出:**

```py
Hexadecimal equivalent of 1111:  F
Hexadecimal equivalent of 110101:  35
Hexadecimal equivalent of 100001111:  10F
Hexadecimal equivalent of 111101111011:  F7B
```

### 方法 2:首先将二进制转换为十进制，然后将十进制转换为十六进制

**第一步:**输入二进制数。

```py
Input: 111101111011 = (111101111011)2
```

**第二步:**将二进制数转换为十进制数。

```py
(111101111011)2 = (3963)10
```

**第三步:**将上述十进制数转换为十六进制数。

```py
(3963)10 = (F7B)16
```

**下图是上面** **方法的 Python 实现:**

## 蟒蛇 3

```py
# Python program to convert binary number
# into hexadecimal number

# Function calculates the decimal equivalent
# to given binary number
def binaryToDecimal(binary):

    binary1 = int(binary)
    decimal, i, n = 0, 0, 0

    while(binary1 != 0):
        dec = binary1 % 10
        decimal = decimal + dec * pow(2, i)
        binary1 = binary1//10
        i += 1
    return(decimal)

# function to convert
# decimal to hexadecimal
def decToHexa(n):

    # char array to store
    # hexadecimal number
    hexaDeciNum = ['0'] * 100

    # counter for hexadecimal
    # number array
    i = 0
    while(n != 0):

        # temporary variable
        # to store remainder
        temp = 0

        # storing remainder
        # in temp variable.
        temp = n % 16

        # check if temp < 10
        if(temp < 10):
            hexaDeciNum[i] = chr(temp + 48)
            i = i + 1
        else:
            hexaDeciNum[i] = chr(temp + 55)
            i = i + 1
        n = int(n / 16)

    # printing hexadecimal number
    # array in reverse order
    j = i - 1
    while(j >= 0):
        print((hexaDeciNum[j]), end="")
        j = j - 1
    print()

# function to convert binary to
# hexadecimal
def binToHexa(n):
    decimal = binaryToDecimal(n)
    print("Hexadecimal equivalent of {}: ".format(n))
    decToHexa(decimal)

# Driver code
if __name__ == '__main__':
    binToHexa('1111')
    binToHexa('110101')
    binToHexa('100001111')
    binToHexa('111101111011')
```

**输出:**

```py
Hexadecimal equivalent of 1111: 
F
Hexadecimal equivalent of 110101: 
35
Hexadecimal equivalent of 100001111: 
10F
Hexadecimal equivalent of 111101111011: 
F7B
```

### 方法 3:使用预定义函数

#### **示例 1:使用 int()和 hex()**

我们使用 int()和 hex()将一个二进制数转换为它的等价十六进制数。下面是使用 int()和 hex()的 Python 实现。

## 蟒蛇 3

```py
# Python code to convert from Binary
# to Hexadecimal using int() and hex()
def binToHexa(n):

    # convert binary to int
    num = int(n, 2)

    # convert int to hexadecimal
    hex_num = hex(num)
    return(hex_num)

# Driver code
if __name__ == '__main__':
    print(binToHexa('1111'))
    print(binToHexa('110101'))
    print(binToHexa('100001111'))
    print(binToHexa('111101111011'))
```

**输出:**

```py
0xf
0x35
0x10f
0xf7b
```

#### **示例 2:使用 int()和 format()**

我们使用 int()和 format()将二进制数转换为其等效的十六进制数。下面是使用 int()和 format()的 Python 实现。

## 蟒蛇 3

```py
# Python code to convert from Binary
# to hexadecimal using format()
def binToHexa(n):

    # convert binary to int
    num = int(n, 2)

    # convert int to hexadecimal
    hex_num = format(num, 'x')
    return(hex_num)

# Driver code
if __name__ == '__main__':
    print(binToHexa('1111'))
    print(binToHexa('110101'))
    print(binToHexa('100001111'))
    print(binToHexa('111101111011'))
```

**输出:**

```py
f
35
10f
f7b
```