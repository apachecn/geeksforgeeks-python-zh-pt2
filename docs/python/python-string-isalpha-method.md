# Python 字符串 isalpha()方法

> 原文:[https://www.geeksforgeeks.org/python-string-isalpha-method/](https://www.geeksforgeeks.org/python-string-isalpha-method/)

Python String **isalpha()** 方法是用于字符串处理的内置方法。如果字符串中的所有字符都是字母，isalpha()方法返回“真”，否则返回“假”。该函数用于检查参数是否只包含字母字符(如下所述)。

> abcdefghijklmnopqrstuvwxyz abcdefghijklmnopqrstuvwxyz

> **语法:**
> 
> string.isalpha（）
> 
> **参数:**
> 
> isalpha()不接受任何参数
> 
> **返回:**
> 
> *   **True** :如果字符串中所有字符都是字母。
> *   **False** :如果字符串包含 1 个或多个非字母。
> 
> **错误和异常:**
> 
> 1.  它不包含参数，因此如果传递参数，就会发生错误
> 2.  大写字母和小写字母都返回“真”
> 3.  空间不被认为是字母表，因此它返回“假”

### 例子

```
Input : string = 'Ayush'
Output : True

Input : string = 'Ayush Saxena'
Output : False

Input : string = 'Ayush0212'
Output : False
```

### 示例 isalpha()的工作原理

## 蟒蛇 3

```
# Python code for implementation of isalpha()

# checking for alphabets
string = 'Ayush'
print(string.isalpha())

string = 'Ayush0212'
print(string.isalpha())

# checking if space is an alphabet
string = 'Ayush Saxena'
print( string.isalpha())
```

**输出:**

```
True
False
False
```

### 示例 2:实际应用

在 python 中给定一个字符串，计算字符串中字母的数量并打印字母。

```
Input : string = 'Ayush Saxena'
Output : 11
         AyushSaxena

Input : string = 'Ayush0212'
Output : 5
         Ayush
```

**算法:**

1.  将一个新的字符串和变量计数器初始化为 0。
2.  逐个字符遍历给定的字符串直到其长度，检查字符是否是字母表。
3.  如果它是一个字母表，将计数器加 1，并将其添加到新字符串中，否则遍历到下一个字符。
4.  打印计数器的值和新字符串。

## 蟒蛇 3

```
# Python program to illustrate
# counting number of alphabets 
# using isalpha()

# Given string
string='Ayush Saxena'
count=0

# Initialising new strings
newstring1 =""
newstring2 =""

# Iterating the string and checking for alphabets
# Incrementing the counter if an alphabet is found
# Finally printing the count
for a in string:
    if (a.isalpha()) == True:
        count+=1
        newstring1+=a
print(count)
print(newstring1)

# Given string
string='Ayush0212'
count=0
for a in string:
    if (a.isalpha()) == True:
        count+=1
        newstring2+=a
print(count)
print(newstring2)
```

**输出:**

```
11
AyushSaxena
5
Ayush
```