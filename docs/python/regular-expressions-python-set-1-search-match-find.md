# Python 中的正则表达式–集合 2(搜索、匹配和全部查找)

> 原文:[https://www . geesforgeks . org/正则表达式-python-set-1-search-match-find/](https://www.geeksforgeeks.org/regular-expressions-python-set-1-search-match-find/)

[Python 中的正则表达式示例|第 1 集](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)
模块 **re** 为 Python 中的正则表达式提供支持。以下是本模块中的主要方法。

**搜索模式的出现**

**re.search() :** 这个方法要么返回 None(如果模式不匹配)，要么返回 re。包含字符串匹配部分信息的 MatchObject。此方法在第一次匹配后停止，因此这比提取数据更适合测试正则表达式。

## 蟒蛇 3

```py
# A Python program to demonstrate working of re.match(). 
import re 

# Lets use a regular expression to match a date string 
# in the form of Month name followed by day number 
regex = r"([a-zA-Z]+) (\d+)"

match = re.search(regex, "I was born on June 24") 

if match != None: 

    # We reach here when the expression "([a-zA-Z]+) (\d+)" 
    # matches the date string. 

    # This will print [14, 21), since it matches at index 14 
    # and ends at 21. 
    print ("Match at index %s, %s" % (match.start(), match.end())) 

    # We us group() method to get all the matches and 
    # captured groups. The groups contain the matched values. 
    # In particular: 
    # match.group(0) always returns the fully matched string 
    # match.group(1) match.group(2), ... return the capture 
    # groups in order from left to right in the input string 
    # match.group() is equivalent to match.group(0) 

    # So this will print "June 24" 
    print ("Full match: %s" % (match.group(0))) 

    # So this will print "June" 
    print ("Month: %s" % (match.group(1))) 

    # So this will print "24" 
    print ("Day: %s" % (match.group(2)))

else: 
    print ("The regex pattern does not match.")
```

**输出:**

```py
Match at index 14, 21
Full match: June 24
Month: June
Day: 24 
```

**将模式与文本匹配**

**re.match() :** 此函数尝试将模式与整个字符串进行匹配。re.match 函数成功时返回一个匹配对象，失败时返回无。

```py
re.match(pattern, string, flags=0)

pattern : Regular expression to be matched.
string : String where pattern is searched
flags : We can specify different flags 
        using bitwise OR (|). 
```

## 蟒蛇 3

```py
# A Python program to demonstrate working
# of re.match().
import re

# a sample function that uses regular expressions
# to find month and day of a date.
def findMonthAndDate(string):

    regex = r"([a-zA-Z]+) (\d+)"
    match = re.match(regex, string)

    if match == None: 
        print ("Not a valid date")
        return

    print ("Given Data: %s" % (match.group()))
    print ("Month: %s" % (match.group(1)))
    print ("Day: %s" % (match.group(2)))

# Driver Code
findMonthAndDate("Jun 24")
print("")
findMonthAndDate("I was born on June 24")
```

**输出:**

```py
Given Data: Jun 24
Month: Jun
Day: 24

Not a valid date
```

**查找模式的所有出现**

**re.findall() :** 返回字符串中所有不重叠的模式匹配，作为字符串列表。从左到右扫描字符串，并按照找到的顺序返回匹配项(来源: [Python 文档](https://docs.python.org/2/library/re.html))。

## 蟒蛇 3

```py
# A Python program to demonstrate working of
# findall()
import re

# A sample text string where regular expression 
# is searched.
string  = """Hello my Number is 123456789 and
             my friend's number is 987654321"""

# A sample regular expression to find digits.
regex = '\d+'            

match = re.findall(regex, string)
print(match)

# This example is contributed by Ayush Saluja.
```

**输出:**

```py
['123456789', '987654321']
```

正则表达式是一个广阔的话题。这是一个完整的图书馆。正则表达式可以做很多事情。您可以匹配、搜索、替换、提取大量数据。例如，下面的小代码非常强大，它可以从文本中提取电子邮件地址。因此，我们可以轻松地用 python 制作自己的网络爬虫和剪贴器。看看下面的正则表达式。

```py
# extract all email addresses and add them into the resulting set
new_emails = set(re.findall(r"[a-z0-9\.\-+_]+@[a-z0-9\.\-+_]+\.[a-z]+", 
                           text, re.I))
```

我们将很快讨论更多关于正则表达式的方法。

本文由 **Shwetanshu Rohatgi** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如发现任何不正确的地方，请写评论，或者您想分享更多关于上述话题的信息