# Python 程序使用正则表达式

查找具有特定扩展名的文件

> 原文:[https://www . geesforgeks . org/python-program-to-find-files-with-special-extension-use-regex/](https://www.geeksforgeeks.org/python-program-to-find-files-having-a-particular-extension-using-regex/)

**先决条件:**[Python 中的正则表达式](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)

很多时候，我们需要从不同类型的文件列表中搜索特定类型的文件。我们可以使用 python 只用几行代码来实现这一点。而最酷的部分是我们不需要安装任何的外部包，python 有一个内置的包叫做 **re** ，用它我们可以很容易的编写出执行这个任务的程序。

**进场:**

*   该程序搜索具有**的文件。不同文件列表中的 XML“**扩展名。
*   制作一个正则表达式/模式:“\”。xml { content } # x201D
*   这里 **re.search()** 函数用于检查字符串(文件名)中任何地方的匹配。它基本上在找到模式时返回 match 对象，如果没有找到模式，则返回 null。
*   这里使用的不同元字符的功能:
    1.  \用于在其后指定字符的特殊含义。它也用于转义特殊字符。
    2.  $字符串以它前面的模式结束。
*   这里”。搜索并处理 xml”模式。

下面是实现:

## 蟒蛇 3

```py
# import library
import re

# list of different types of file
filenames = ["gfg.html", "geeks.xml", 
            "computer.txt", "geeksforgeeks.jpg"]

for file in filenames:
    # search given pattern in the line 
    match = re.search("\.xml{content}quot;, file)

    # if match is found
    if match:
        print("The file ending with .xml is:",
             file)
```

**Output:**

```py
The file ending with .xml is: geeks.xml
```