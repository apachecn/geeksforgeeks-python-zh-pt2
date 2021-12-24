# Python 字符串 istitle()方法

> 原文:[https://www.geeksforgeeks.org/python-string-istitle-method/](https://www.geeksforgeeks.org/python-string-istitle-method/)

如果字符串是有标题的字符串，方法返回真，否则返回假。**什么是标题？**每个单词中第一个字符为大写字母，其余字符为小写字母的字符串。

> **语法:**
> 
> string.istitle（）
> 
> **参数:**
> 
> istitle()方法不接受任何参数。
> 
> **返回:**
> 
> 如果字符串是标题大小写的字符串，则为 True，否则返回 False。

### 例 1

## 蟒蛇 3

```
# First character in each word is 
# uppercase and remaining lowercases
s = 'Geeks For Geeks'
print(s.istitle())

# First character in first
# word is lowercase
s = 'geeks For Geeks'
print(s.istitle())

# Third word has uppercase
# characters at middle
s = 'Geeks For GEEKs'
print(s.istitle())

s = '6041 Is My Number'
print(s.istitle())

# word has uppercase
# characters at middle
s = 'GEEKS'
print(s.istitle())
```

**输出:**

```
True
False
False
True
False
```

### 例 2

## 蟒蛇 3

```
s = 'I Love Geeks For Geeks'

if s.istitle() == True:
    print('Titlecased String')
else:
    print('Not a Titlecased String')

s = 'I Love geeks for geeks'

if s.istitle() == True:
    print('Titlecased String')
else:
    print('Not a Titlecased String')
```

**输出:**

```
Titlecased String
Not a Titlecased String
```