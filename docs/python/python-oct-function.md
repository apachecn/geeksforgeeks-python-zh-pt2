# Python 中的 oct()函数

> 原文:[https://www.geeksforgeeks.org/python-oct-function/](https://www.geeksforgeeks.org/python-oct-function/)

**Python oct()函数**是内置方法之一，它取一个整数，以字符串格式返回八进制表示。

> **语法:** oct(x)
> 
> **参数:**
> 
> *   **x**–必须是整数，可以是二进制、十进制或十六进制格式。
> 
> **返回:**值的八进制表示。
> 
> **错误和异常:**
> 
> *   **类型错误:**当整数类型常量以外的任何内容作为参数传递时，返回类型错误。

### **示例 1:功能示例** f **oct()**

## 蟒蛇 3

```
# Python3 program to demonstrate
# the use of oct() function

print("The octal representation of 23 is " + oct(23))

print("The octal representation of the"
      " ascii value of 'z' is " + oct(ord('z')))

# Binary representation of a number
# can be passed as a parameter

# For 23, Binary is 0b10111
print("The octal representation of the binary"
      " of 23 is " + oct(0b10111))

# For 23, Hexadecimal is 0x17
print("The octal representation of the binary"
      " of 23 is " + oct(0x17))
```

**输出:**

```
The octal representation of 23 is 0o27
The octal representation of the ascii value of 'z' is 0o172
The octal representation of the binary of 23 is 0o27
The octal representation of the binary of 23 is 0o27
```

### 示例 2 **:** 演示 oct()方法中的类型错误

## 蟒蛇 3

```
# Python3 program demonstrating TypeError

print("The Octal representation of 29.5 is " + oct(29.5))

'''
# Python doesn't have anything like float.oct()
# to directly convert a floating type constant
# to its octal representation. Conversion of a
# floating-point value to it's octal is done manually.
'''
```

**输出:**

```
Traceback (most recent call last):
  File "/home/5bf02b72de26687389763e9133669972.py", line 3, in 
    print("The Octal representation of 29.5 is "+oct(29.5))
TypeError: 'float' object cannot be interpreted as an integer
```

**应用:** oct()用于所有类型的**标准转换**。例如，从十进制到八进制的转换，二进制到八进制的转换，十六进制到八进制的转换。

### **示例 3:** 使用 oct()函数从十进制和二进制进行类型转换

## **蟒蛇 3**

```
# TypeConversions from decimal and binary
# to their respective octal representations

# The choices present to the user
print("a. Hexadecimal to Octal ")
print("b. Decimal to Octal")
print("c. Binary to Octal")

# Function generates octal representation
# from it's binary from
def bin_to_oct():

    print("Enter your input in BIN format :-")

    # taking user input as binary string and
    # then using int() to convert it into it's
    # respective decimal format
    x = int(input(), 2)
    print("Octal form of " + str(x) + " is " + oct(x))

# Function generates octal representation
#  of it's hexadecimal form passed as value.
def hex_to_oct():
    print("Enter your input in HEX format :-")

    # taking user input as hexadecimal string and
    # then using int() to convert it into it's
    # respective decimal format
    x = int(input(), 16)
    print("Octal form of " + str(x) + " is " + oct(x))

# Function converts decimal form to it's
# respective octal representation
def decimal_to_oct():

    print("Enter a number with base-10 format :-")

    # taking a simple user input and
    # converting it to an integer
    x = int(input())
    print("Octal form of " + str(x) + " is " + oct(x))

# Driver Code
ch = input("Enter your choice :-\n")

if ch is 'a':
    hex_to_oct()
elif ch is 'b':
    decimal_to_oct()
elif ch is 'c':
    bin_to_oct()
```

****输出:****

```
a. Hexadecimal to Octal 
b. Decimal to Octal
c. Binary to Octal
Enter your choice :-
a
Enter your input in HEX format :-
0x13
Octal form of 19 is 0o23
```

### **示例 4:用于自定义对象的 Python oct()**

## **蟒蛇 3**

```
class math:
    num = 76
    def __index__(self):
        return self.num
    def __int__(self):
        return self.num
obj = math()
print(oct(obj))
```

****输出:****

```
0o114
```