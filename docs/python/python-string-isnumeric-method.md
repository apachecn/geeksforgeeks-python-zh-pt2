# Python 字符串是 numeric()方法

> 原文:[https://www . geesforgeks . org/python-string-is numeric-method/](https://www.geeksforgeeks.org/python-string-isnumeric-method/)

Python String **isnumeric()** 方法是用于字符串处理的内置方法。如果字符串中的所有字符都是数字字符，issnumeric()方法返回“真”，否则返回“假”。该函数用于检查参数是否包含所有数字字符，如**整数、分数、下标、上标、罗马数字**、**等。(全部用 Unicode 编写)**

> **语法:**
> 
> *弦*。isnumeric()
> 
> **参数:**
> 
> isnumeric()不接受任何参数
> 
> **返回:**
> 
> *   如果字符串中的所有字符都是数字字符，则为 True。
> *   false–如果字符串包含 1 个或多个非数字字符。
> 
> **错误和异常:**
> 
> 1.  它不包含任何参数，因此，如果传递参数，它将返回一个错误。
> 2.  空格不被认为是数字，因此，它返回“假”
> 3.  下标、上标、分数、罗马数字(都是用 Unicode 写的)都被认为是数字，因此，它返回“真”

### 例 1:

```py
Input : string = '1889345'
Output : True

Input : string = '\u00BD'
Output : True

Input : string = '123ayu456'
Output : False
```

## 蟒蛇 3

```py
# Python code for implementation of isnumeric()

# checking for numeric characters
string = '123ayu456'
print(string.isnumeric())

string = '123456'
print( string.isnumeric())
```

**输出:**

```py
False
True
```

### 例 2:

**应用:**在 python 中给定一个字符串，统计该字符串中数字字符的个数并从字符串中删除，然后打印该字符串。

```py
Input : string = '123geeks456for789geeks'
Output : 9
         geeksforgeeks

Input : string = '123ayu456'
Output : 6
         ayu
```

**算法:**

1.  初始化一个空的新闻字符串，变量计数为 0。
2.  逐个字符遍历给定的字符串直到其长度，检查该字符是否为数字字符。
3.  如果是数字字符，将计数器增加 1，不要将其添加到新字符串中，否则遍历到下一个字符，如果不是数字，则继续将字符添加到新字符串中。
4.  打印计数器和新闻字符串的值。

## 蟒蛇 3

```py
# Python implementation to count numeric characters
# in a string and print non numeric characters
# Given string
# Initialising the counter to 0
string ='123geeks456for789geeks'
count = 0

newstring1 =""
newstring2 =""

# Iterating the string and checking for numeric characters
# Incrementing the counter if a numeric character is found
# And adding the character to new string if not numeric
# Finally printing the count and the newstring
for a in string:
    if (a.isnumeric()) == True:
        count+= 1
    else:
        newstring1+= a
print(count)
print(newstring1)

string ='123ayu456'
count = 0
for a in string:
    if (a.isnumeric()) == True:
        count+= 1
    else:
        newstring2+= a
print(count)
print(newstring2)
```

**输出:**

```py
9
geeksforgeeks
6
ayu
```