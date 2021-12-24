# Python 字符串 endswith()方法

> 原文:[https://www . geesforgeks . org/python-string-end swith-method/](https://www.geeksforgeeks.org/python-string-endswith-method/)

如果字符串以给定的后缀结束，Python String endswith()方法返回 True，否则返回 False。

> **语法:**
> 
> str . endswith(后缀、开始、结束)
> 
> **参数:**
> 
> *   **后缀:**后缀只不过是需要检查的字符串。
> *   **开始:**字符串中需要检查后缀的起始位置。
> *   **结束:**字符串中需要检查后缀的结束位置+ 1。
> 
> **注意:**如果没有提供开始和结束索引，那么默认情况下，它将 0 和 length -1 作为开始和结束索引，其中结束索引不包括在我们的搜索中。
> 
> **返回:**
> 如果字符串以给定的后缀结束，则返回真，否则返回假。

### 示例 1:不带开始和结束参数的 endswith()方法的工作

## 计算机编程语言

```py
# Python code shows the working of
# .endswith() function

text = "geeks for geeks."

# returns False
result = text.endswith('for geeks')
print (result)

# returns True
result = text.endswith('geeks.')
print (result)

# returns True
result = text.endswith('for geeks.')
print (result)

# returns True
result = text.endswith('geeks for geeks.')
print (result)
```

**输出:**

```py
False
True
True
True
```

### 示例 2:带开始和结束参数的 endswith()方法的工作

## 计算机编程语言

```py
# Python code shows the working of
# .endswith() function

text = "geeks for geeks."

# start parameter: 10
result = text.endswith('geeks.', 10)
print(result)

# Both start and end is provided
# start: 10, end: 16 - 1
# Returns False
result = text.endswith('geeks', 10, 16)
print result

# returns True
result = text.endswith('geeks', 10, 15)
print result
```

**输出:**

```py
True
True
False 
```