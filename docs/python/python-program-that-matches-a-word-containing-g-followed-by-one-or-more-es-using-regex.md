# Python |使用正则表达式

匹配一个包含“g”后跟一个或多个“e”的单词的程序

> 原文:[https://www . geesforgeks . org/python-program-match-a-word-containing-g-后跟一个或多个-es-use-regex/](https://www.geeksforgeeks.org/python-program-that-matches-a-word-containing-g-followed-by-one-or-more-es-using-regex/)

**先决条件:**正则表达式| [集 1](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/) 、[集 2](https://www.geeksforgeeks.org/regular-expressions-python-set-1-search-match-find/)

给定一个字符串，任务是检查该字符串中是否包含任何 *g* 后跟一个或多个*e*，否则，打印不匹配。

**示例:**

```
Input : geeks for geeks
Output : geeks 
         geeks

Input : graphic era
Output : No match 

```

**方法:**首先，创建一个正则表达式(regex)对象，该对象匹配一个包含“g”后跟一个或多个“e”的单词，然后在`findall` 方法中传递一个字符串。此方法返回匹配字符串的列表。循环浏览列表并打印每个匹配的单词。

> **\ w–**表示任何字母、数字或下划线字符。
> ***** 表示字符出现的次数为零或更多。
> **+** 表示字符的一次或多次出现。

下面是实现:

```
# Python program that matches a word
# containing ‘g’ followed by one or
# more e’s using regex

# import re packages
import re

# Function check if the any word of
# the string containing 'g' followed
# by one or more e's
def check(string) :

    # Regex \w * ge+\w * will match 
    # text that contains 'g', followed 
    # by one or more 'e'
    regex = re.compile("ge+\w*")

    # The findall() method returns all 
    # matching strings of the regex pattern
    match_object = regex.findall(string)

    # If length of match_object is not
    # equal to zero then it contains
    # matched string
    if len(match_object) != 0 :

        # looping through the list
        for word in match_object :
            print(word)

    else :
        print("No match")

# Driver Code     
if __name__ == '__main__' :

    # Enter the string
    string = "Welcome to geeks for geeks"

    # Calling check function
    check(string)
```

**输出:**

```
geeks
geeks
```