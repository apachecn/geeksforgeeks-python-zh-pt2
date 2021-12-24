# Python 中 re.fullmatch()函数

> 原文:[https://www . geesforgeks . org/re-full match-function-in-python/](https://www.geeksforgeeks.org/re-fullmatch-function-in-python/)

**re.fullmatch()** 当且仅当整个字符串与模式匹配时，返回匹配对象。否则，它将返回无。结尾的标志是可选的，可以用来忽略案例等。

> **语法:** re.fullmatch(模式、字符串、标志=0)
> 
> **参数:**
> 
> *   **模式:**要匹配的正则表达式模式。
> *   **字符串:**要搜索模式的字符串。
> *   **标志(可选参数):**一个更高级的修饰符，允许您自定义函数的行为。

**例 1:**

## 蟒蛇 3

```
import re

string = 'geeks'
pattern = 'g...s'

print(re.fullmatch(pattern, string))
```

**Output**

```
<_sre.SRE_Match object; span=(0, 5), match='geeks'>
```

## re.match()和 re.fullmatch()之间的差异

**re.fullmatch()** 和 **re.match()** 都是 python 中 re 模块的功能。这些函数对于搜索字符串非常有效和快速。两个函数都试图在字符串的开头匹配。但是 re.match()和 re.fullmatch()的区别在于，re.match()只在开头匹配，但 re.fullmatch()也会尝试在结尾匹配。

**示例:**

## 蟒蛇 3

```
import re

string = "Geeks for geeks"
pattern = "Geeks"

print(re.match(pattern, string))
print(re.fullmatch(pattern, string))
```

**Output**

```
<_sre.SRE_Match object; span=(0, 5), match='Geeks'>
None
```