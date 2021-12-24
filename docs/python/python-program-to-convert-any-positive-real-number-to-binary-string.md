# 将任意正实数转换为二进制字符串的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-convert-any-正数-实数-二进制-字符串/](https://www.geeksforgeeks.org/python-program-to-convert-any-positive-real-number-to-binary-string/)

给定作为浮点数传入的大于或等于零的任何实数，打印输入实数的二进制表示。

**示例:**

```
Input: 123.5
Output: 1 1 1 1 0 1 1 . 1

Input: 0.25
Output: .01
```

**数学逻辑以及编程步骤:**

任何实数都分为两部分:**整数部分和分数部分**。对于这两个部分，操作和逻辑是不同的，以将其转换为二进制表示。

*   **Integer Part:**

    **步骤 1:** 将整数部分除以 2，并记下它的余数(它将是 0 或 1)。
    **第二步:**再次将整数部分除以 2(从第一步开始的整数除以 2 得到的整数)并记下其余数。
    重复这些步骤，直到你的整数不变为零。
    **第三步:**现在颠倒你在每一步中注意到的余数的顺序。这是整数部分的二进制表示。

    **编程步骤:**

    ```
    def intpartbinary(m):

        a=[]
        n=int(m)

        while n!=0:
            a.append(n%2)
            n=n//2
        a.reverse()

        return a
    ```

    定义函数`intpartbinary()`将整数部分转换为二进制表示。定义一个空列表，取输入实数的整数部分，除以 2，每次`while n==0`将其余数存储到一个空列表中，反转列表，这将是整数部分的二进制表示。

*   **Fractional Part:**
    **Step 1:** Multiply fractional part by 2 and write its integer part only.
    **Step 2:** Subtract integer part from the number obtained in step 1(multiplying fraction part by 2) and again multiply fractional part by 2.
    Repeat these steps until the Fractional part does not become Zero. The sequence obtained is Binary representation of given fractional part.

    **编程步骤:**

    ```
    def decimalpartbinary(m):

        a=[]
        n=m-int(m)

        while n!=0:
            x=2*n
            y=int(x)
            a.append(y)
            n=x-y

        return a
    ```

    定义函数`decimalpartbinary()`将小数部分转换为二进制。再次定义一个空列表，通过从输入的实数中减去输入的实数的整数部分，从输入的实数中提取小数部分。现在将其乘以 2，只将结果数的整数部分存储到列表中，再取小数部分乘以 2，存储其整数部分。重复这个过程，直到小数部分不为零，这将是小数部分的二进制表示。

现在最后组合，下面给定格式的所有二进制转换将是输入实数的二进制表示。首先写出余数和一个点(点)的逆序，然后写出整数部分序列，这是我们通过将分数部分乘以 2 并只提取整数部分而得到的。

```
def binarycode(m):

    a = intpartbinary(m)
    b = decimalpartbinary(m)
    c = []

    for i in range(0, len(a)):
        c.append(a[i])

    c.append('.')

    for j in range(0, len(b)):
        c.append(b[j])

    print('Binary code of given function is\n')

    for k in range(0, len(c)):
        print(c[k], end=' ')
```

为此，我们将定义一个名为`binarycode()`的函数。定义一个空`list c=[]`，先存储整数部分每次除以 2 得到的余数的倒排表，然后在表 c 中存储一个小数，现在存储分数部分每次乘以 2 得到的整数部分的表，只存储整数部分。现在打印列表 c。最后，我们将把实数的二进制表示转换成二进制表示。

下面是实现。

```
# defining a function to convert 
# integer part to binary
def intpartbinary(m):

    a = []
    n = int(m)

    while n != 0:

        a.append(n % 2)
        n = n//2

    a.reverse()
    return a

# defining a function to convert 
# fractional part to binary
def decimalpartbinary(m):

    a = []
    n = m-int(m)

    while n != 0:

        x = 2 * n
        y = int(x)
        a.append(y)
        n = x-y

    return a
# arranging all data into suitable format
def binarycode(m):

    # arranging all data to our desired 
    # format
    a = intpartbinary(m)
    b = decimalpartbinary(m)
    c =[]

    for i in range(0, len(a)):
        c.append(a[i])

    c.append('.')

    for j in range(0, len(b)):
        c.append(b[j])

    print('Binary code of given function is\n')

    for k in range(0, len(c)):
        print(c[k], end =' ')

# Driver Code
binarycode(123.5)
```

**输出:**

```
Binary code of given function is

1 1 1 1 0 1 1 . 1 
```