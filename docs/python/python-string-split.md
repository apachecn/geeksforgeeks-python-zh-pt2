# Python 字符串| split()

> 原文:[https://www.geeksforgeeks.org/python-string-split/](https://www.geeksforgeeks.org/python-string-split/)

**Python 中的 split()** 方法通过指定的分隔符断开给定的字符串后，将字符串拆分为字符串列表。

> **语法:** str.split(分隔符，maxsplit)
> 
> **参数:**
> **分隔符:**这是一个分隔符。字符串在指定的分隔符处拆分。如果未提供，则任何空格都是分隔符。
> 
> **maxsplit :** 是一个数字，告诉我们把字符串拆分成最大提供次数。如果未提供，则默认值为-1，这意味着没有限制。
> 
> **返回:**通过指定的分隔符断开给定字符串后，返回字符串列表。

**示例 1:** 演示 split()函数工作原理的示例

```
text = 'geeks for geeks'

# Splits at space
print(text.split())

word = 'geeks, for, geeks'

# Splits at ','
print(word.split(','))

word = 'geeks:for:geeks'

# Splitting at ':'
print(word.split(':'))

word = 'CatBatSatFatOr'

# Splitting at t
print(word.split('t'))
```

**输出:**

```
['geeks', 'for', 'geeks']
['geeks', ' for', ' geeks']
['geeks', 'for', 'geeks']
['Ca', 'Ba', 'Sa', 'Fa', 'Or']
```

**示例 2:** 演示当指定 maxsplit 时 split()函数如何工作的示例

```
word = 'geeks, for, geeks, pawan'

# maxsplit: 0
print(word.split(', ', 0))

# maxsplit: 4
print(word.split(', ', 4))

# maxsplit: 1
print(word.split(', ', 1))
```

**输出:**

```
['geeks, for, geeks, pawan']
['geeks', 'for', 'geeks', 'pawan']
['geeks', 'for, geeks, pawan']
```