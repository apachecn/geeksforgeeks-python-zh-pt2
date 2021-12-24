# Python 程序检查字符串中是否存在小写字母

> 原文:[https://www . geesforgeks . org/python-程序检查字符串中是否存在小写字母/](https://www.geeksforgeeks.org/python-program-to-check-if-lowercase-letters-exist-in-a-string/)

给定一个字符串，任务是编写一个 Python 程序来检查该字符串是否有小写字母。

**示例:**

```py
Input: "Live life to the fullest"
Output: false

Input: "LIVE LIFE TO THe FULLEST"
Output: false

Input: "LIVE LIFE TO THE FULLEST"
Output: true

```

**方法 1#:** 使用[伊斯洛()](https://www.geeksforgeeks.org/isupper-islower-lower-upper-python-applications/)

如果字符串中的所有大小写字符都是小写的并且至少有一个大小写字符，则返回真，否则返回假。

## 计算机编程语言

```py
# Python code to demonstrate working of
# is.lower()  method in strings

#Take any string
str = "Live life to the Fullest"

# Traversing Each character of
# the string to check whether
# it is in lowercase
for char in str:
    k = char.islower()  
    if k == True:
        print('True')

    # Break the Loop when you
    # get any lowercase character.
        break  

# Default condition if the string
# does not have any lowercase character.
if(k != 1):
    print('False')
```

**输出:**

```py
True

```

**方法 2#:** 使用 [isupper()](https://www.geeksforgeeks.org/python-string-isupper-method/)

如果字符串中所有大小写字符都是大写的并且至少有一个大小写字符，则返回真，否则返回假。

## 计算机编程语言

```py
# Python Program to demonstrate the
# is.upper() method in strings
#Take a string
str = "GEEKS"

# Traversing Each character
# to check whether it is in uppercase
for char in str:
    k = char.isupper()  
    if k == False:
        print('False')

        # Break the Loop
        # when you get any
        # uppercase character.
        break

# Default condition if the string
# does not have any uppercase character.
if(k == 1):
    print('True')
```

**输出:**

```py
True

```

**方法 3#:** 使用 [ASCII 值](https://www.geeksforgeeks.org/program-print-ascii-value-character/)检查给定字符是大写还是小写。

函数的作用是:返回一个代表 Unicode 字符的整数。

**示例:**

```py
print(ord('A'))    # 65
print(ord('a'))    # 97

```

## 蟒蛇 3

```py
# Python Program to Demonstrate the strings
# methods to check whether given Character
# is in uppercase or lowercase with the help
# of ASCII values

#Input by geeks
x = "GEeK"

# counter
counter = 0

for char in x:
    if(ord(char) >= 65 and ord(char) <= 90):

        counter = counter + 1

    # Check for the condition 
    # if the ASCII value is Between 97 and 122
    # if condition is True print the
    # corresponding result
    if(ord(char) >= 97 and ord(char) <= 122):
        print("Lower Character found")
        break
if counter == len(x):
    print(True)
```

**输出:**

```py
Lower Character found

```