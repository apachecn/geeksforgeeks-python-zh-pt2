# Python 字符串 rsplit()方法

> 原文:[https://www.geeksforgeeks.org/python-string-rsplit-method/](https://www.geeksforgeeks.org/python-string-rsplit-method/)

python String***rsplit()***方法通过指定的分隔符从右侧断开给定字符串后，返回字符串列表。

> **语法:**
> 
> str . rsplit(分隔符号，maxsplit)
> 
> **参数:**
> 
> *   **分隔符:**是分隔符。字符串从右侧开始在指定的分隔符处拆分。如果不提供，则任何空格都是分隔符。
> *   **maxsplit:** 是一个数字，它告诉我们将字符串拆分成最大提供次数。如果不提供，则没有限制。
> 
> **返回:**
> 
> 通过指定的分隔符从右侧断开给定字符串后，返回字符串的*列表*。
> 
> **错误:**
> 
> 即使我们不传递任何参数，我们也不会得到任何错误。

### 例 1

## 蟒蛇 3

```
# Python code to split a string
# using rsplit.

# Splits at space
word = 'geeks for geeks'
print(word.rsplit())

# Splits at 'g'. Note that we have
# provided maximum limit as 1\. So
# from right, one splitting happens
# and we get "eeks" and "geeks, for, "
word = 'geeks, for, geeks'
print(word.rsplit('g', 1))

# Splitting at '@' with maximum splitting
# as 1
word = 'geeks@for@geeks'
print(word.rsplit('@', 1))
```

**输出:**

```
['geeks', 'for', 'geeks']
['geeks, for, ', 'eeks']
['geeks@for', 'geeks']
```

### 例 2

## 蟒蛇 3

```
word = 'geeks, for, geeks, pawan'

# maxsplit: 0
print(word.rsplit(', ', 0))

# maxsplit: 4
print(word.rsplit(', ', 4))

word = 'geeks@for@geeks@for@geeks'

# maxsplit: 1
print(word.rsplit('@', 1))

# maxsplit: 2
print(word.rsplit('@', 2))
```

**输出:**

```
['geeks, for, geeks, pawan']
['geeks', 'for', 'geeks', 'pawan']
['geeks@for@geeks@for', 'geeks']
['geeks@for@geeks', 'for', 'geeks']
```

### 例 3

## 蟒蛇 3

```
word = 'geeks for geeks'

# Since separator is 'None', 
# so, will be splitted at space
print(word.rsplit(None, 1))

print(word.rsplit(None, 2))

# Also observe these
print('@@@@@geeks@for@geeks'.rsplit('@'))
print('@@@@@geeks@for@geeks'.rsplit('@', 1))
print('@@@@@geeks@for@geeks'.rsplit('@', 3))
print('@@@@@geeks@for@geeks'.rsplit('@', 5))
```

**输出:**

```
['geeks for', 'geeks']
['geeks', 'for', 'geeks']
['', '', '', '', '', 'geeks', 'for', 'geeks']
['@@@@@geeks@for', 'geeks']
['@@@@', 'geeks', 'for', 'geeks']
['@@', '', '', 'geeks', 'for', 'geeks']
```