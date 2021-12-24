# Python 程序将 Base 4 系统转换为二进制数

> 原文:[https://www . geesforgeks . org/python-program-convert-base-4-system-to-binary-number/](https://www.geeksforgeeks.org/python-program-to-convert-base-4-system-to-binary-number/)

给定一个基数为 4 的数字 N，任务是编写一个 python 程序来打印它的二进制等价物。

**转换表:**

![](img/259b122f34e36db81e72a6271a5fd058.png)

**示例:**

> **输入:** N=11002233
> 
> **输出:** 101000010101111
> 
> **说明:**从那个转换表中我们把 1 改成了 01，2 改成了 10，3 改成了 11，0 改成了 00。
> 
> **输入:** N=321321
> 
> **输出:** 111001111001

**进场:**

*   取一个空字符串，说 **resultstr。**
*   我们把十进制 [**数转换成字符串。**T3】](https://www.geeksforgeeks.org/convert-integer-to-string-in-python/)
*   遍历字符串并将每个字符转换为整数
*   如果整数是 **1 或 0** ，那么在转换为二进制之前，在**结果串**中加上‘0’(因为我们不能有整数中的 01，00)
*   现在将此 [**整数转换为二进制字符串**](https://www.geeksforgeeks.org/program-decimal-binary-conversion/)[**将结果二进制字符串**](https://www.geeksforgeeks.org/python-string-concatenation/) 连接为**结果字符串。**
*   将 **resultstr** 转换为整数(去除前导零)。
*   返回**结果串。**

下面是上述方法的实现。

## 蟒蛇 3

```py
# function which converts decimal to binary
def decToBin(num):

    # Using default binary conversion functions
    binary = bin(num)

    # removing first two character as the
    # result is always in the form 0bXXXXXXX
    # by taking characters after index 2
    binary = binary[2:]
    return binary

# function to convert base4 to binary
def convert(num):

    # Taking a empty string
    resultstr = ""

    # converting number to string
    numstring = str(num)

    # Traversing string
    for i in numstring:

        # converting this character to integer
        i = int(i)

        # if i is 1 or 0 then add '0' to result
        # string
        if(i == 1 or i == 0):
            resultstr = resultstr+'0'

        # passing this integer to get converted to
        # binary
        binary = decToBin(i)

        # print(binary)
        # Concatenating this binary string to result
        # string
        resultstr = resultstr+binary

    # Converting resultstr to integer
    resultstr = int(resultstr)

    # Return result string
    return resultstr

# Driver code
Number = 11002233

# Passing this number to convert function
print(convert(Number))
```

**输出:**

```py
101000010101111
```