# Python 字符串是 digit()方法

> 原文:[https://www.geeksforgeeks.org/python-string-isdigit-method/](https://www.geeksforgeeks.org/python-string-isdigit-method/)

Python String **isdigit()** 方法是用于字符串处理的内置方法。如果字符串中的所有字符都是数字，则 isdigit()方法返回“**真**，否则返回“假”。该功能用于检查参数是否包含数字，如 **0123456789**

> **语法:**
> 
> string.isdigit（）
> 
> **参数:**
> 
> isdigit()不接受任何参数
> 
> **返回:**
> 
> *   如果字符串中的所有字符都是数字，则为 True。
> *   false–如果字符串包含 1 个或多个非数字。
> 
> **错误和异常:**
> 
> 1.  它不接受任何参数，因此如果传递参数，它将返回一个错误
> 2.  上标和下标与十进制字符一起被认为是数字字符，因此，isdigit()返回“真”。
> 3.  罗马数字、货币记数器和分数不被认为是数字。因此，isdigit()返回“假”

### **例 1:**

```py
Input : string = '15460'
Output : True

Input : string = '154ayush60'
Output : False
```

## 蟒蛇 3

```py
# Python code for implementation of isdigit()

# checking for digit
string = '15460'
print(string.isdigit())

string = '154ayush60'
print(string.isdigit())
```

**输出:**

```py
True
False
```

### 例 2:

**应用:**使用字符的 **ASCII 值**，使用 isdigit()功能统计并打印所有数字。

**算法:**

1.  初始化一个新字符串，变量计数=0。
2.  使用 ASCII 值遍历每个字符，检查该字符是否为数字。
3.  如果它是一个数字，将计数增加 1，并将其添加到新字符串中，否则遍历到下一个字符。
4.  打印计数器的值和新字符串。

## 蟒蛇 3

```py
# Python program to illustrate 
# application of isdigit()
# initialising Empty string
newstring =''

# Initialising the counters to 0
count = 0

# Incrementing the counter if a digit is found 
# and adding the digit to a new string
# Finally printing the count and the new string

for a in range(53):
    b = chr(a)
    if b.isdigit() == True:
        count+= 1
        newstring+= b

print("Total digits in range :", count)
print("Digits :", newstring)
```

**输出:**

```py
Total digits in range : 5
Digits : 01234
```

在 Python 中，上标和下标(通常使用 Unicode 编写)也被认为是数字字符。因此，如果字符串包含这些字符和十进制字符，isdigit()将返回 True。罗马数字、货币记数器和分数(通常使用 Unicode 书写)被认为是数字字符，而不是数字。如果字符串包含这些字符，isdigit()将返回 False。若要检查字符是否为数字字符，可以使用 isnumeric()方法。

### **例 3:**

包含数字和数字字符的字符串

## 蟒蛇 3

```py
s = '23455'
print(s.isdigit())

# s = '²3455'
# subscript is a digit
s = '\u00B23455'

print(s.isdigit())

# s = '½'
# fraction is not a digit
s = '\u00BD'

print(s.isdigit())
```

**输出:**

```py
True
True
False
```