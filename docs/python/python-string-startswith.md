# python | string start with()

> 原文:[https://www.geeksforgeeks.org/python-string-startswith/](https://www.geeksforgeeks.org/python-string-startswith/)

如果字符串以给定的前缀开头，startswith()方法返回 True，否则返回 False。

**语法:**

```py
str.startswith(prefix, start, end)

```

**参数:**

```py
prefix : prefix ix nothing but a string which needs to be checked.
start : Starting position where prefix is needs to be checked within the string.
end : Ending position where prefix is needs to be checked within the string.

```

**注意:**如果没有提供开始和结束索引，那么默认情况下，它采用 0 和 length-1 作为开始和结束索引，其中结束索引不包括在我们的搜索中。

**返回:**

```py
It returns True if strings starts with the given
prefix otherwise returns False.

```

**例:**

```py
Input : text = "geeks for geeks."
        result = text.startswith('for geeks')
Output : False

Input : text = "geeks for geeks."
        result = text.startswith('geeks', 0)
Output : True

```

**错误:**值错误:在目标字符串

```py
# Python code shows the working of
# .startsswith() function

text = "geeks for geeks."

# returns False
result = text.startswith('for geeks')
print (result)

# returns True
result = text.startswith('geeks')
print (result)

# returns False
result = text.startswith('for geeks.')
print (result)

# returns True
result = text.startswith('geeks for geeks.')
print (result)
```

中找不到参数字符串的情况下会出现此错误

输出:

```py
False
True
False
True

```