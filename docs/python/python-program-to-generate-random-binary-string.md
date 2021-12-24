# 生成随机二进制字符串的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序生成-随机-二进制-字符串/](https://www.geeksforgeeks.org/python-program-to-generate-random-binary-string/)

给定一个数字 n，任务是生成一个长度为 n 的随机二进制字符串。
**示例:**

```
Input: 7
Output: Desired length random binary string is:  1000001

Input: 5
Output: Desired length random binary string is:  01001
```

**接近**

*   初始化一个空字符串，比如 key
*   使用随机包中的 randint 函数随机生成“0”或“1”。
*   将随机生成的“0”或“1”附加到字符串、键
*   重复第 2 步和第 3 步，获得所需的绳子长度

下面是实现。

## 蟒蛇 3

```
# Python program for random
# binary string generation

import random

# Function to create the
# random binary string
def rand_key(p):

    # Variable to store the
    # string
    key1 = ""

    # Loop to find the string
    # of desired length
    for i in range(p):

        # randint function to generate
        # 0, 1 randomly and converting
        # the result into str
        temp = str(random.randint(0, 1))

        # Concatenation the random 0, 1
        # to the final result
        key1 += temp

    return(key1)

# Driver Code
n = 7
str1 = rand_key(n)
print("Desired length random binary string is: ", str1)
```

**输出:**

```
Desired length random binary string is:  1000001
```