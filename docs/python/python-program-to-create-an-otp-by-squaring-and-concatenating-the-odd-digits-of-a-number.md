# Python 程序，通过平方和连接一个数字的奇数位来创建一个 OTP

> 原文:[https://www . geeksforgeeks . org/python-通过平方和连接数字的奇数位来创建 otp 的程序/](https://www.geeksforgeeks.org/python-program-to-create-an-otp-by-squaring-and-concatenating-the-odd-digits-of-a-number/)

给定一个数字 n，任务是通过平方和连接该数字的奇数位来创建一个动态口令。

**例:**

```
Input: 4365188
Output: 9256

Input: 123456
Output: 4163

```

**说明:**在第一个例子中，奇数位的整数是 3、5、8。所以我们必须通过平方这些数字来返回一个 4 位数的动态口令。以上数字的平方是 9、25、65，所以要返回的 OTP 是前四位数字 9256。

**方法:**迭代字符串(数字)的长度，起始索引为 1，步长为 2。初始化一个空字符串，然后将奇数的平方连接到该字符串。最后，将字符串的前四个字符作为动态口令返回。

下面是实现。

```
# python program to generate
# an OTP from the squares of the
# odd digits

def OTP(number):

    # Finding the length 
    # of the string
    length = len(number)

    # Declaring an empty string 
    # for storing otp
    otp = ''

    # Iterating from index 1 
    # with step as 2
    for odd in range(1, length, 2):

        # Concatenating the output
        # to the string 
        otp+= str(int(number[odd])**2)

    print(otp[0:4])

# Driver code
number = '4365188'
OTP(number)
```

**输出:**

```
9256

```