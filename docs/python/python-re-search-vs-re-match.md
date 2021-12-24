# Python | re . search()vs . re . match()

> 原文:[https://www.geeksforgeeks.org/python-re-search-vs-re-match/](https://www.geeksforgeeks.org/python-re-search-vs-re-match/)

**先决条件:**[Python 中的 Regex](https://www.geeksforgeeks.org/regular-expressions-python-set-1-search-match-find/)

**re.search()** 和 **re.match()** 都是 python 中 re 模块的功能。这些函数对于搜索字符串非常有效和快速。该函数在字符串中搜索一些子字符串，如果找到，则返回一个匹配对象，否则不返回任何对象。

这两种功能的使用是有区别的。两者都返回在字符串中找到的子字符串的第一个匹配项，但是 **re.match()** 仅从字符串的开头开始搜索，如果找到匹配项，则返回 match 对象。但是，如果在字符串中间的某个地方找到匹配的子字符串，它将返回 none。
而 **re.search()** 即使字符串包含多行，也会搜索整个字符串，并尝试在字符串的所有行中找到子字符串的匹配项。

**示例:**

## 蟒蛇 3

```
# import re module
import re

Substring ='string'

String1 ='''We are learning regex with geeksforgeeks
         regex is very useful for string matching.
          It is fast too.'''
String2 ='''string We are learning regex with geeksforgeeks
         regex is very useful for string matching.
          It is fast too.'''

# Use of re.search() Method
print(re.search(Substring, String1, re.IGNORECASE))
# Use of re.match() Method
print(re.match(Substring, String1, re.IGNORECASE))

# Use of re.search() Method
print(re.search(Substring, String2, re.IGNORECASE))
# Use of re.match() Method
print(re.match(Substring, String2, re.IGNORECASE))
```

**输出:**

```
<re.Match object; span=(75, 81), match='string'>
None
<re.Match object; span=(0, 6), match='string'>
<re.Match object; span=(0, 6), match='string'>
```

**结论:**

1.  **re.search()** 正在返回匹配对象，这意味着在索引 69 处找到了第一个匹配。
2.  **re.match()** 不返回任何值，因为匹配存在于字符串的第二行，并且 re.match()仅在字符串开头找到匹配时有效。
3.  **re。IGNORECASE** 用于忽略字符串中的区分大小写。
4.  **re.search()** 和 **re.match()** 都只返回字符串中第一个出现的子字符串，而忽略其他子字符串。