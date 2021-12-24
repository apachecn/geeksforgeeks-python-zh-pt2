# Python String – removespostix（）

> 原文:[https://www.geeksforgeeks.org/python-string-removesuffix/](https://www.geeksforgeeks.org/python-string-removesuffix/)

如果字符串以后缀结尾，并且后缀不为空，**str . remove 后缀(后缀，/)** 函数将删除后缀并返回字符串的其余部分。如果找不到后缀字符串，则返回原始字符串。它是在 Python 3.9.0 版本中引入的。

> **语法:** str.removesuffix(后缀，/)
> 
> **参数:**
> 
> **后缀**–我们正在检查的后缀字符串。
> 
> **返回值:**
> 
> **如果字符串以后缀字符串结尾，并且该后缀不为空，则返回:**字符串[:–len(后缀)]。否则它返回原始字符串的副本。

**例 1:**

## 蟒蛇 3

```py
# Python 3.9 code explaining
# str.removesuffix()

# suffix exists
print('ComputerScience'.removesuffix('Science'))

# suffix doesn't exist
print('GeeksforGeeks'.removesuffix('for'))
```

**输出:**

```py
Computer
GeeksforGeeks

```

**例 2:**

## 蟒蛇 3

```py
# Python 3.9 code explaining
# str.removesuffix()

# String for removesuffix()
# If suffix exists then
# then it remove suffix from the string
# otherwise return original string

string1 = "Welcome to python 3.9"
print("Original String 1 : ", string1)

# suffix exists
result = string1.removesuffix("3.9")
print("New string : ", result)

string2 = "Welcome Geek"
print("Original String 2 : ", string2)

# suffix doesn't exist
result = string2.removesuffix("Welcome")
print("New string : ", result)
```

**输出:**

```py
Original String 1 :  Welcome to python 3.9
New string :  Welcome to python 
Original String 2 :  Welcome Geek
New string :  Welcome Geek

```