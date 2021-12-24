# Python Regex–re。MatchObject.start()和 re。MatchObject.end()函数

> 原文:[https://www . geesforgeks . org/python-regex-re-match object-start-and-re-match object-end-functions/](https://www.geeksforgeeks.org/python-regex-re-matchobject-start-and-re-matchobject-end-functions/)

在这篇文章中，我们将看到 **re。MatchObject.start()** 和 **re。MatchObject.end()** 正则表达式方法。

## re。MatchObject.start()

该方法返回*组匹配的子串的第一个索引。*

> **语法:** re。MatchObject.start([group])
> 
> **参数:**
> 
> *   **组:(可选)** *组*默认为零(表示整个匹配的子串)。返回-1 如果*组*存在但没有为比赛做出贡献。
> 
> **返回:*组匹配的子串开始的***索引。
> 
> **属性错误:**如果找不到匹配的模式，则会引发属性错误。

## 国王！国王！MatchObject.end()

该方法返回*组匹配的子串的最后一个索引。*

> **语法:** re。match object . end([组])
> 
> **参数:**
> 
> *   **组:(可选)** *组*默认为零(表示整个匹配的子串)。返回-1 如果*组*存在但没有为比赛做出贡献。
> 
> **返回:*组匹配的子串末尾的***索引。
> 
> **属性错误:**如果找不到匹配的模式，则会引发属性错误。

考虑下面的例子:

**例 1:**

## 蟒蛇 3

```
import re

# getting the match of the the string
search_pattern = re.search('\d+',
                           '1234')

""" 
d: stands for integer
+: means a consecutive set of 
characters satisfying a condition. 
Hence d+ will match consecutive 
integer string 
"""

print(search_pattern.string)

print(search_pattern.start())

print(search_pattern.end())
```

**输出:**

```
1234
0
4
```

让我们理解代码。在代码的第三行，我们使用 **re.search()** 方法在给定的字符串中查找匹配项(**1234**)“**d**“**表示我们在搜索一个数字字符，而“ **+** ”表示我们在给定的字符串中搜索连续的数字字符。我们得到的结果是一个 **re。存储在 search_pattern 中的 MatchObject** 。如果您打印 **search_pattern.string** ，您将获得“1234”作为输出。**

**在上例中， **search_pattern.start()** 返回值 **0** ，因为给定字符串中匹配字符串的第一个元素的索引为 0， **search_pattern.end()** 返回 **4** ，即字符串结束后的结束索引。**

****例 2:****

## **蟒蛇 3**

```
import re

# getting the match of the the string
search_pattern = re.search('\d+',
                           'abcd')
""" 
d: stands for integer
+: means a consecutive set of characters 
satisfying a condition. 
Hence d+ will match consecutive 
integer string 
"""

print(search_pattern.start())

print(search_pattern.end())
```

****输出:****

```
Traceback (most recent call last):
  File "/home/4f904f4b53a786e10faa03122533f96b.py", line 13, in 
    print(search_pattern.start())
AttributeError: 'NoneType' object has no attribute 'start' 
```