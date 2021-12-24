# Python String | strip()

> 原文:[https://www.geeksforgeeks.org/python-string-strip-2/](https://www.geeksforgeeks.org/python-string-strip-2/)

Python 的 ***strip()方法*** 内置函数用于移除字符串中的所有前导和尾随空格。

> **语法:** string.strip([chars])
> 
> **参数:**
> 
> **字符(可选):**需要从字符串中删除的字符或一组字符。
> 
> **返回:**字符串的一个副本，去掉了前导和尾随字符。

#### 使用条带()方法:

*   如果左边字符串的字符与*字符*参数中的字符不匹配，该方法将停止删除前导字符。
*   如果右侧字符串的字符与*字符*参数中的字符不匹配，该方法将停止删除尾部字符。

**示例#1:**

## 蟒蛇 3

```
# Python code to illustrate the working of strip()
string = '   Geeks for Geeks   '

# Leading spaces are removed
print(string.strip())

# Geeks is removed
print(string.strip('   Geeks'))

# Not removed since the spaces do not match
print(string.strip('Geeks'))
```

**输出:**

```
Geeks for Geeks
for
   Geeks for Geeks   
```

**例 2:**

## 蟒蛇 3

```
# Python code to illustrate the working of strip()
string = '@@@@Geeks for Geeks@@@@@'

# Strip all '@' from beginning and ending
print(string.strip('@'))

string = 'www.Geeksforgeeks.org'

# '.grow' removes 'www' and 'org' and '.'
print(string.strip('.grow'))
```

**输出:**

```
Geeks for Geeks
Geeksforgeeks
```

**示例#3:**
下面的代码展示了 python 中 strip()的一个应用。

## 蟒蛇 3

```
# Python code to check for identifiers
def Count(string):

    print("Length before strip()")
    print(len(string))

    # Using strip() to remove white spaces
    str = string.strip()
    print("Length after removing spaces")
    return str

# Driver Code
string = "  Geeks for Geeks   "
print(len(Count(string)))
```

**输出:**

```
Length before strip()
17
Length after removing spaces
15
```