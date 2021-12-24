# Python Regex:re . search()VS re . findall()

> 原文:[https://www . geesforgeks . org/python-regex-re-search-vs-re-find all/](https://www.geeksforgeeks.org/python-regex-re-search-vs-re-findall/)

**先决条件:** [正则表达式带示例| Python](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)
A [正则表达式](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)(有时称为 Rational 表达式)是定义搜索模式的字符序列，主要用于与字符串的模式匹配，或字符串匹配，即类似“查找和替换”的操作。正则表达式是一种将模式与字符序列相匹配的通用方法。
模块*正则表达式(RE)* 指定与之匹配的一组字符串(模式)。为了理解 re 类比，元字符是有用的、重要的，并且将用于模块 RE 的函数中。
共有 14 个元字符，将在它们进入函数时进行讨论:

```py
\   Used to drop the special meaning of character
    following it (discussed below)
[]  Represent a character class
^   Matches the beginning
$   Matches the end
.   Matches any character except newline
?   Matches zero or one occurrence.
|   Means OR (Matches with any of the characters
    separated by it.
*   Any number of occurrences (including 0 occurrences)
+   One or more occurrences
{}  Indicate number of occurrences of a preceding RE 
    to match.
()  Enclose a group of REs 
```

#### re.search()

re.search()方法要么返回 None(如果模式不匹配)，要么返回 re。包含字符串匹配部分信息的 MatchObject。此方法在第一次匹配后停止，因此这比提取数据更适合测试正则表达式。
**例:**

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
    print("Match at index % s, % s" % (match.start(), match.end()))

    # We us group() method to get all the matches and
    # captured groups. The groups contain the matched values.
    # In particular:
    # match.group(0) always returns the fully matched string
    # match.group(1) match.group(2), ... return the capture
    # groups in order from left to right in the input string
    # match.group() is equivalent to match.group(0)

    # So this will print "June 24"
    print("Full match: % s" % (match.group(0)))

    # So this will print "June"
    print("Month: % s" % (match.group(1)))

    # So this will print "24"
    print("Day: % s" % (match.group(2)))

else:
    print("The regex pattern does not match.")
```

**输出:**

```py
Match at index 14, 21
Full match: June 24
Month: June
Day: 24
```

#### re . findall()

以字符串列表的形式返回字符串中所有不重叠的模式匹配项。从左到右扫描字符串，并按照找到的顺序返回匹配项。
**例:**

## 蟒蛇 3

```py
# A Python program to demonstrate working of
# findall()
import re

# A sample text string where regular expression 
# is searched.
string = """Hello my Number is 123456789 and
             my friend's number is 987654321"""

# A sample regular expression to find digits.
regex = '\d+'            

match = re.findall(regex, string)
print(match)
```

**输出:**

```py
['123456789', '987654321']
```