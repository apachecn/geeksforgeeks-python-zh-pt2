# Python |将字符串转换为列表的程序

> 原文:[https://www . geesforgeks . org/python-program-convert-string-list/](https://www.geeksforgeeks.org/python-program-convert-string-list/)

在这个程序中，我们将尝试把一个给定的字符串转换成一个列表，根据用户的选择，这个列表中会出现空格或任何其他特殊字符。为此，我们使用 split()方法。
**语法:**

```
string.split("delimiter")
```

示例:

```
Input : "Geeks for Geeks"
Output : ['Geeks', 'for', 'Geeks']

Input : "Geeks-for-Geeks"
Output : ['Geeks', 'for', 'Geeks']

```

split 方法用于拆分字符串并将它们存储在列表中。内置方法返回字符串中的单词列表，使用“分隔符”作为分隔符字符串。如果未指定分隔符或分隔符为“无”，则应用不同的拆分算法:连续空格的运行被视为单个分隔符，如果字符串有前导或尾随空格，则结果在开头或结尾不包含空字符串。
实施例 1:

```
# Python code to convert string to list

def Convert(string):
    li = list(string.split(" "))
    return li

# Driver code    
str1 = "Geeks for Geeks"
print(Convert(str1))
```

输出:

```
['Geeks', 'for', 'Geeks']

```

例 2:

```
# Python code to convert string to list
def Convert(string):
    li = list(string.split("-"))
    return li

# Driver code    
str1 = "Geeks-for-Geeks"
print(Convert(str1))
```

输出:

```
['Geeks', 'for', 'Geeks']

```

例 3:

```
# Python code to convert string to list character-wise
def Convert(string):
    list1=[]
    list1[:0]=string
    return list1
# Driver code
str1="ABCD"
print(Convert(str1))
```

输出:

```
['A','B','C','D']

```