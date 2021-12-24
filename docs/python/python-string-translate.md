# Python | String translate()

> 原文:[https://www.geeksforgeeks.org/python-string-translate/](https://www.geeksforgeeks.org/python-string-translate/)

**translate()** 返回一个字符串，该字符串是根据给定的转换映射修改后的 givens 字符串。

有两种翻译方法:

**Providing a mapping as a dictionary**

**参数:**

> string.translate(映射)
> 
> `mapping`-两个字符之间有映射的字典。
> **返回:**返回修改后的字符串，其中每个字符根据提供的映射表映射到其对应的字符。

```py
# Python3 code to demonstrate 
# translations without 
# maketrans() 

# specifying the mapping 
# using ASCII 
table = { 119 : 103, 121 : 102, 117 : None } 

# target string 
trg = "weeksyourweeks"

# Printing original string 
print ("The string before translating is : ", end ="") 
print (trg) 

# using translate() to make translations. 
print ("The string after translating is : ", end ="") 
print (trg.translate(table)) 
```

**Output:**

```py
The string before translating is : weeksyourweeks
The string after translating is : geeksforgeeks

```

**再举一个例子:**

```py
# Python 3 Program to show working
# of translate() method

# specifying the mapping  
# using ASCII  
translation = {103: None, 101: None, 101: None}

string = "geeks"
print("Original string:", string)

# translate string
print("Translated string:", 
       string.translate(translation))
```

**Output:**

```py
Original string: geeks
Translated string: ks

```

**Providing a mapping using [maketrans()](https://www.geeksforgeeks.org/python-maketrans-translate-functions/)**

> 语法:maketrans(str1，str2，str3)
> 参数:
> str1:指定需要替换的字符列表。
> str2:指定需要替换字符的字符列表。
> str3:指定需要删除的字符列表。
> 
> 返回:返回指定 translate()可以使用的转换的转换表

```py
# Python 3 Program to show working
# of translate() method

# First String
firstString = "gef"

# Second String
secondString = "eks"

# Third String
thirdString = "ge"

# Original String
string = "geeks"
print("Original string:", string)

translation = string.maketrans(firstString, 
                               secondString, 
                               thirdString)

# Translated String
print("Translated string:", 
       string.translate(translation))
```

**Output:**

```py
Original string: geeks
Translated string: ks

```

**输出:**

```py
Original string: geeks
Translated string: ks
```