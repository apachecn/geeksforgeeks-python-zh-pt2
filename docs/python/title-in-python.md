# Python 字符串标题方法

> 原文:[https://www.geeksforgeeks.org/title-in-python/](https://www.geeksforgeeks.org/title-in-python/)

python 中的 title()函数是 Python 字符串方法，用于将每个单词中的第一个字符转换为大写，并将字符串中的剩余字符转换为小写，并返回一个新字符串。

**语法:**

```py
str.title()
parameters:str is a valid string which we need to convert.
return: This function returns a string which 
has first letter in each word is uppercase and all 
remaining letters are lowercase.
```

## 计算机编程语言

```py
# Python title() Method Example

str1 = 'geeKs foR geEks'
str2 = str1.title()
print 'First Output after Title() method is = ', str2

# observe the original string
print 'Converted String is = ', str1.title()
print 'Original String is = ', str1

# Performing title() function directly
str3 = 'ASIPU pawan kuMAr'.title()
print 'Second Output after Title() method is = ', str3

str4 = 'stutya kUMari sHAW'.title()
print 'Third Output after Title() method is = ', str4

str5 = '6041'.title()
print 'Fourth Output after Title() method is = ', str5
```

输出:

```py
First Output after title() method is =  Geeks For Geeks
Converted String is =  Geeks For Geeks
Original String is =  geeKs foR geEks
Second Output after title() method is =  Asipu Pawan Kumar
Third Output after title() method is =  Stutya Kumari Shaw
Fourth Output after title() method is =  6041
```