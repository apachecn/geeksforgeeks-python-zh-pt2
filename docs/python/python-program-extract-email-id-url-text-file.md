# Python 程序从 URL 文本文件中提取 Email-id

> 原文:[https://www . geesforgeks . org/python-program-extract-email-id-URL-text-file/](https://www.geeksforgeeks.org/python-program-extract-email-id-url-text-file/)

**先决条件:** [与 Python Regex 的模式匹配](https://www.geeksforgeeks.org/pattern-matching-python-regex/)
给定网址文本文件，任务是从该文本文件中提取所有电子邮件 id 并打印`urllib.request`库，该库可用于处理所有与网址相关的工作。

示例:

```
Input : 
Hello
This is Geeksforgeeks
review-team@geeksforgeeks.org
contribute@geeksforgeeks.org
GfG is a portal for geeks
feedback@geeksforgeeks.org
careers@geeksforgeeks.org

Output :
[]
[]
['review-team@geeksforgeeks.org']
['contribute@geeksforgeeks.org']
[]
['feedback@geeksforgeeks.org']
['careers@geeksforgeeks.org']

```

网址文本文件可以使用`urllib.request`进行处理。对于使用正则表达式提取电子邮件，可以使用`re` 库。关于正则表达式的更多细节，请参考[本](https://www.geeksforgeeks.org/extracting-email-addresses-using-regular-expressions-python/)。

```
# library that handles the URL stuff
import urllib.request

# Importing module required for
# regular expressions
import re

# Assign urlopen to a file object variable
fhand = urllib.request.urlopen
    ('https://media.geeksforgeeks.org/wp-content/uploads/e-mail-1.txt')

for line in fhand:
    # Getting the text file
    # content line by line.
    s = line.decode().strip()

    # regex for extracting all email-ids
    # from the text file
    reg = re.findall(r"[A-Za-z0-9._%+-]+"
                     r"@[A-Za-z0-9.-]+"
                     r"\.[A-Za-z]{2,4}", s)

    # printing the list output
    print(reg)
```

**输出:**

```
[]
[]
['review-team@geeksforgeeks.org']
['contribute@geeksforgeeks.org']
[]
['feedback@geeksforgeeks.org']
['careers@geeksforgeeks.org']
```