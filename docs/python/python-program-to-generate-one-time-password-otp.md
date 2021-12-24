# Python 程序生成一次性密码(OTP)

> 原文:[https://www . geesforgeks . org/python-程序生成一次性密码-otp/](https://www.geeksforgeeks.org/python-program-to-generate-one-time-password-otp/)

一次性密码是一种只对计算机或数字设备中的一次登录会话或事务有效的密码。现在，OTP 几乎应用于所有服务，如网上银行、网上交易等。它们通常是 4 或 6 位数字或 6 位字母数字的组合。

random()函数可用于生成随机 OTP，该 OTP 是在随机库中预定义的。让我们看看如何使用 Python 生成动态口令。

> **已用函数:**
> **random.random():** 此函数返回 0 到 1 之间的任意随机数。
> **math.floor():** 返回任意浮点数的 floor 为整数值。
> 使用上述函数选择字符串数组的随机索引，该数组包含一次性密码特定数字的所有可能候选。

**示例#1 :** 生成 4 位数字 OTP

## 蟒蛇 3

```py
# import library
import math, random

# function to generate OTP
def generateOTP() :

    # Declare a digits variable 
    # which stores all digits
    digits = "0123456789"
    OTP = ""

   # length of password can be changed
   # by changing value in range
    for i in range(4) :
        OTP += digits[math.floor(random.random() * 10)]

    return OTP

# Driver code
if __name__ == "__main__" :

    print("OTP of 4 digits:", generateOTP())
```

**输出:**

```py
OTP of 4 digits: 3211
```

**示例#2:** 生成长度为 6 的字母数字 OTP

## 蟒蛇 3

```py
# import library
import math, random

# function to generate OTP
def generateOTP() :

    # Declare a string variable 
    # which stores all string
    string = '0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ'
    OTP = ""
    length = len(string)
    for i in range(6) :
        OTP += string[math.floor(random.random() * length)]

    return OTP

# Driver code
if __name__ == "__main__" :

    print("OTP of length 6:", generateOTP())
```

**输出:**

```py
OTP of length 6: pyelJl
```

**示例#3:** 使用字符串常量

## 蟒蛇 3

```py
# Importing random to generate
# random string sequence
import random

# Importing string library function
import string

def rand_pass(size):

    # Takes random choices from
    # ascii_letters and digits
    generate_pass = ''.join([random.choice( string.ascii_uppercase +
                                            string.ascii_lowercase +
                                            string.digits)
                                            for n in range(size)])

    return generate_pass

# Driver Code 
password = rand_pass(10)
print(password)
```

**输出:**

```py
2R8gaoDKqn
```