# Python 字符串分区()方法

> 原文:[https://www . geesforgeks . org/python-string-partition-method/](https://www.geeksforgeeks.org/python-string-partition-method/)

Python String partition()方法在第一次出现分隔符时拆分字符串，并返回一个元组，该元组包含分隔符之前的部分、分隔符和分隔符之后的部分。这里的分隔符是作为参数给出的字符串。

> **语法:**
> 
> 字符串.分区(分隔符)
> 
> **参数:**
> 
> partition()方法使用分隔符(字符串)作为参数，在字符串第一次出现时分隔字符串。
> 
> **返回:**
> 
> 返回一个元组，该元组包含分隔符之前的部分、分隔符参数以及分隔符之后的部分(如果在字符串中找到分隔符参数)。如果找不到分隔符参数，则返回包含字符串本身和两个空字符串的元组。

### 例 1

## 蟒蛇 3

```
string = "pawan is a good"

# 'is' separator is found
print(string.partition('is '))

# 'not' separator is not found
print(string.partition('bad '))

string = "pawan is a good, isn't it"

# splits at first occurrence of 'is'
print(string.partition('is'))
```

**输出:**

```
('pawan ', 'is ', 'a good')
('pawan is a good', '', '')
('pawan ', 'is', " a good, isn't it")
```

### 例 2

## 蟒蛇 3

```
string = "geeks is a good"

# 'is' separator is found
print(string.partition('is '))

# 'not' separator is not found
print(string.partition('bad '))

string = "geeks is a good, isn't it"

# splits at first occurrence of 'is'
print(string.partition('is'))
```

**输出:**

```
('geeks ', 'is ', 'a good')
('geeks is a good', '', '')
('geeks ', 'is', " a good, isn't it")
```