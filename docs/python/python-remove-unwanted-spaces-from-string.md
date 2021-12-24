# Python |删除字符串中不需要的空格

> 原文:[https://www . geesforgeks . org/python-从字符串中删除不需要的空格/](https://www.geeksforgeeks.org/python-remove-unwanted-spaces-from-string/)

有时，在处理字符串时，我们可能会遇到这样的情况:字符串中的中间单词之间可能有 1 个以上的空格，而这些空格大多是不需要的。这种情况可能发生在 web 开发中，通常需要纠正。让我们讨论执行这项任务的某些方法。

**方法#1:使用`re.sub()`**
这个问题可以使用正则表达式来执行，在正则表达式中，我们可以使用适当的正则表达式字符串将单词之间的间隔限制为单个空格。

```py
# Python3 code to demonstrate working of
# remove additional space from string
# Using re.sub()
import re

# initializing string 
test_str = "GfG  is   good           website"

# printing original string 
print("The original string is : " + test_str)

# using re.sub()
# remove additional space from string 
res = re.sub(' +', ' ', test_str)

# printing result 
print("The strings after extra space removal : " + str(res))
```

**Output :**

```py
The original string is : GfG  is   good           website
The strings after extra space removal : GfG is good website

```