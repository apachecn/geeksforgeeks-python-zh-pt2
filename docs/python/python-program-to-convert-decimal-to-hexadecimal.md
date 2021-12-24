# Python 程序将十进制转换为十六进制

> 原文:[https://www . geesforgeks . org/python-程序转十进制转十六进制/](https://www.geeksforgeeks.org/python-program-to-convert-decimal-to-hexadecimal/)

在本文中，我们将学习如何在 Python 中将十进制值(以 10 为基数)转换为十六进制值(以 16 为基数)。

## **方法一:使用 hex()函数**

[hex()函数](https://www.geeksforgeeks.org/python-hex-function/)是 Python3 中的内置函数之一，用于将一个整数转换为其对应的十六进制形式。

> **语法** **:** 十六进制(x)
> 
> **参数**T2:
> 
> *   **x**–整数(int 对象)
> 
> **返回** **:** 返回十六进制字符串。
> 
> **错误和异常:**
> 
> **类型错误:**除以下情况外，返回类型错误
> 
> 整数类型常量作为参数传递。

**代码:**

## 蟒蛇 3

```
# Python3 program to illustrate
# hex() function

print("The hexadecimal form of 69 is "
      + hex(69))
```

**输出:**

```
The hexadecimal form of 69 is 0x45
```

## **方法 2:迭代方法**

将十进制转换为十六进制的传统方法是将其除以 16，直到它等于零。给定十进制数的十六进制版本是以十六进制形式从最后到第一的余数序列。要将余数转换为十六进制形式，请使用以下转换表:

<figure class="table">

| **余数** | **六角当量** |
| --- | --- |
| Zero | Zero |
| one | one |
| Two | Two |
| three | three |
| four | four |
| five | five |
| six | six |
| seven | seven |
| eight | eight |
| nine | nine |
| Ten | A |
| Eleven | B |
| Twelve | C |
| Thirteen | D |
| Fourteen | E |
| Fifteen | F |

</figure>

**代码:**

## 蟒蛇 3

```
# Conversion table of remainders to
# hexadecimal equivalent
conversion_table = {0: '0', 1: '1', 2: '2', 3: '3', 4: '4',
                    5: '5', 6: '6', 7: '7',
                    8: '8', 9: '9', 10: 'A', 11: 'B', 12: 'C',
                    13: 'D', 14: 'E', 15: 'F'}

# function which converts decimal value
# to hexadecimal value
def decimalToHexadecimal(decimal):
    hexadecimal = ''
    while(decimal > 0):
        remainder = decimal % 16
        hexadecimal = conversion_table[remainder] + hexadecimal
        decimal = decimal // 16

    return hexadecimal

decimal_number = 69
print("The hexadecimal form of", decimal_number,
      "is", decimalToHexadecimal(decimal_number))
```

**输出:**

```
The hexadecimal form of 69 is 45
```

## **方法 3:递归方法**

这个想法与迭代方法中使用的类似。

**代码:**

## 蟒蛇 3

```
# Conversion table of remainders to
# hexadecimal equivalent
conversion_table = {0: '0', 1: '1', 2: '2', 3: '3',
                    4: '4', 5: '5', 6: '6', 7: '7',
                    8: '8', 9: '9', 10: 'A', 11: 'B',
                    12: 'C', 13: 'D', 14: 'E', 15: 'F'}

# function which converts decimal value
# to hexadecimal value
def decimalToHexadecimal(decimal):
    if(decimal <= 0):
        return ''
    remainder = decimal % 16
    return decimalToHexadecimal(decimal//16) + conversion_table[remainder]

decimal_number = 69
print("The hexadecimal form of", decimal_number,
      "is", decimalToHexadecimal(decimal_number))
```

**输出:**

```
The hexadecimal form of 69 is 45
```