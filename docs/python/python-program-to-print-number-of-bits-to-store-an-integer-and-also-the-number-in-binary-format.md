# Python 程序打印存储整数的位数以及二进制格式的数字

> 原文:[https://www . geesforgeks . org/python-程序-打印-位数-存储-整数-二进制格式的数字/](https://www.geeksforgeeks.org/python-program-to-print-number-of-bits-to-store-an-integer-and-also-the-number-in-binary-format/)

给定一个整数，任务是编写一个 Python 程序来打印存储该整数的位数，并以二进制格式打印相同的数字。

**示例:**

> **输入:** n = 10
> 
> **输出:**
> 
> 存储数字的位数:4
> 
> 二进制值:0b1010
> 
> **输入:** n = 120
> 
> **输出:**
> 
> 存储数字的位数:7
> 
> 二进制值:0b1111000

该任务可以通过 3 种方式完成，所有方式如下:

### **方法 1:使用循环**

在本文中，我们将使用最基本的方法将给定的数字转换为二进制形式，方法是将其除以 2，直到数字变为零，并在每次除法后存储余数。以这种方式继续，数组的大小将给出存储一个整数的位数，数组的反方向给出整数的二进制格式。

**接近**

*   声明或接受输入
*   继续除以 2，并存储得到的余数
*   在过程结束时，打印它的二进制等价物以及存储它所需的位数。

**示例:**

## 蟒蛇 3

```py
list1 = []
num = 10

while (num > 0):
    list1.append(num % 2)
    num = num//2

print("Number of bits required to store 10:", len(list1))
print("Binary Representatiaon:", end="")
for i in reversed(list1):
    print(list1[i], end="")
```

**输出:**

> 存储 10: 4 所需的位数
> 
> 二进制表示:1010

### **方法二:使用递归**

这段代码执行与方法 1 中给出的相同的任务，但是我们将使用递归来代替使用循环。

**进场:**

*   声明或接受输入
*   继续除以 2，并存储使用递归函数获得的余数
*   在过程结束时，打印它的二进制等价物以及存储它所需的位数。

**示例:**

## 蟒蛇 3

```py
def decimalToBinary(n, x):

    if n > 1:
        # divide with integral result
        # (discard remainder)
        x = decimalToBinary(n//2, x)

    print(n % 2, end="")
    return x+1

# Driver code
if __name__ == '__main__':
    x = 0
    print("Binary Representation of 17:", end=" ")

    x = decimalToBinary(17, x)

    print()
    print("Number of bits required to store 17:", end=" ")
    print(x)
```

**输出:**

> 17: 10001 的二进制表示
> 
> 存储 17: 5 所需的位数

### **方法三:使用内置功能**

Python 带有内置的复杂函数，只需几行就可以完成相同的任务。为了找到存储一个整数的总位数，我们使用 **bit_length()** 函数，用数字(一个整数值)调用它，返回存储给定数字的总位数。

> **语法:** int.bit_length(n)
> 
> **参数:** n，其中为整数
> 
> **返回:**用二进制表示整数所需的位数，不包括符号和前导零。

要打印给定整数的二进制值，我们使用 **bin()** 函数，它接受数字作为参数并返回二进制值。

> **语法:** bin(a)
> 
> **参数:**
> 
> a:要转换的整数
> 
> **返回值:**
> 整数或 int 对象的二进制字符串。
> 
> **异常:**
> 当在参数中发送浮点值时引发类型错误。

产生的输出将在一个数字前面有 0b，它只是一个指示符，跟随它的是一个二进制表示。如果你愿意，你可以把它拿走。

**示例:**

## 蟒蛇 3

```py
num = 120

s = bin(120)

print("Number of bits required to store 120:", end=" ")
print(num.bit_length())

print("Binary Representation", end=" ")
print(s)
```

**Output**

```py
Number of bits required to store 120: 7
Binary Representation 0b1111000

```

**输出:**

> 存储 120 所需的位数:7
> 
> 二进制表示 0b1111000