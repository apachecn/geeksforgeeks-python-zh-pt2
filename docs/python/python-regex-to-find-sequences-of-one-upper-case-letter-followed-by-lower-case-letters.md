# Python 正则表达式查找一个大写字母后跟小写字母的序列

> 原文:[https://www . geeksforgeeks . org/python-regex-to-find-一个大写字母后跟小写字母的序列/](https://www.geeksforgeeks.org/python-regex-to-find-sequences-of-one-upper-case-letter-followed-by-lower-case-letters/)

写一个 Python 程序来查找一个大写字母后跟小写字母的序列。如果找到，打印“是”，否则打印“否”。

**例:**

```
Input : Geeks
Output : Yes

Input : geeksforgeeks
Output : No

```

**方法:**使用[搜索()](https://www.geeksforgeeks.org/pattern-matching-python-regex/)

为了检查一个大写字母后跟小写字母的顺序，我们使用正则表达式“`[A-Z]+[a-z]+$`”。

```
# Python3 code to find sequences of one upper
# case letter followed by lower case letters
import re

# Function to match the string
def match(text):

        # regex
        pattern = '[A-Z]+[a-z]+{content}apos;

        # searching pattern
        if re.search(pattern, text):
                return('Yes')
        else:
                return('No')

# Driver Function
print(match("Geeks"))
print(match("geeksforGeeks"))
print(match("geeks"))
```

**输出:**

```
Yes
Yes
No
```