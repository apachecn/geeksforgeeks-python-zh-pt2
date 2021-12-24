# Python 字符串| strip()

> 原文:[https://www.geeksforgeeks.org/python-string-strip/](https://www.geeksforgeeks.org/python-string-strip/)

**strip()** 是 Python 编程语言中的一个内置函数，它返回一个字符串的副本，并删除前导和尾随字符(基于传递的字符串参数)。
**语法:**

```py
string.strip([chars])
Parameter: 
There is only one optional parameter in it:
1)chars - a string specifying 
the set of characters to be removed. 

If the optional chars parameter is not given, all leading 
and trailing whitespaces are removed from the string.
Return Value:
Returns a copy of the string with both leading and trailing characters removed.
```

## 蟒蛇 3

```py
# Python3 program to demonstrate the use of
# strip() method 

string = """    geeks for geeks    """

# prints the string without stripping
print(string)

# prints the string by removing leading and trailing whitespaces
print(string.strip())  

# prints the string by removing geeks
print(string.strip(' geeks'))
```

**Output:** 

```py
    geeks for geeks     
geeks for geeks
for
```

## 蟒蛇 3

```py
# Python Program to demonstrate use of strip() method

str1 = 'geeks for geeks'
# Print the string without stripping.
print(str1)

# String whose set of characters are to be
# remove from original string at both its ends.
str2 = 'ekgs'

# Print string after stripping str2 from str1 at both its end.
print(str1.strip(str2))
```

**Output:** 

```py
geeks for geeks
 for
```