# Python 程序添加两个二进制数

> 原文:[https://www . geesforgeks . org/python-程序添加二进制数/](https://www.geeksforgeeks.org/python-program-to-add-two-binary-numbers/)

给定两个二进制数，编写一个 Python 程序来计算它们的和。

**示例:**

```
Input:  a = "11", b = "1"
Output: "100"

Input: a = "1101", b = "100"
Output: 10001

```

**进场:**

*   **天真法:**思路是从两个字符串的最后一个字符开始，逐个计算数字和。如果总和大于 1，则存储下一位数的进位。
*   **使用内置函数:**使用内置的 [**bin()**](https://www.geeksforgeeks.org/bin-in-python/) 和 [**int()**](https://www.geeksforgeeks.org/python-int-function/) 函数计算结果。

**方法 1:** 天真方法:

这个想法是从两个字符串的最后一个字符开始，一个接一个地计算数字和。如果总和大于 1，则存储下一位数的进位。

## 蟒蛇 3

```
# Python program to add two binary numbers.

# Driver code
# Declaring the variables
a = "1101"
b = "100"
max_len = max(len(a), len(b))
a = a.zfill(max_len)
b = b.zfill(max_len)

# Initialize the result
result = ''

# Initialize the carry
carry = 0

# Traverse the string
for i in range(max_len - 1, -1, -1):
    r = carry
    r += 1 if a[i] == '1' else 0
    r += 1 if b[i] == '1' else 0
    result = ('1' if r % 2 == 1 else '0') + result

    # Compute the carry.
    carry = 0 if r < 2 else 1

if carry != 0:
    result = '1' + result

print(result.zfill(max_len))
```

**输出:**

```
10001

```

**方法 2:** 使用内置函数:

我们将首先使用 python 中的 [**int()**](https://www.geeksforgeeks.org/python-int-function/) 函数将二进制字符串转换为十进制。Python 和 Python3 中的 *int()* 函数将给定基数的数字转换为十进制。然后我们将它相加，然后再次使用 [**bin()**](https://www.geeksforgeeks.org/bin-in-python/) 函数将其转换为二进制数。

## 蟒蛇 3

```
# Python program to add two binary numbers.

# Driver code
# Declaring the variables
a = "1101"
b = "100"

# Calculating binary value using function
sum = bin(int(a, 2) + int(b, 2))

# Printing result
print(sum[2:])
```

**输出:**

```
10001

```