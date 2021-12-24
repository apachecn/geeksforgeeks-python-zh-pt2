# 使用 Regex

对大写、小写、特殊字符和数值进行计数的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序到计数-大写-小写-特殊字符和数值-使用-regex/](https://www.geeksforgeeks.org/python-program-to-count-uppercase-lowercase-special-character-and-numeric-values-using-regex/)

**先决条件:**[Python 中的正则表达式](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)

给定一个字符串。任务是使用 Python 中的正则表达式计算字符串中出现的大写、小写、特殊字符和数值的数量。

**示例:**

```
Input : 
"ThisIsGeeksforGeeks!, 123" 

Output :
No. of uppercase characters = 4
No. of lowercase characters = 15
No. of numerical characters = 3
No. of special characters = 2

```

**方法:**re . find all(模式，字符串，标志=0)方法可用于查找字符串中模式的所有非重叠匹配。返回值是字符串列表。

下面是实现。

```
import re

string = "ThisIsGeeksforGeeks !, 123"

# Creating separate lists using 
# the re.findall() method.
uppercase_characters = re.findall(r"[A-Z]", string)
lowercase_characters = re.findall(r"[a-z]", string)
numerical_characters = re.findall(r"[0-9]", string)
special_characters = re.findall(r"[, .!?]", string)

print("The no. of uppercase characters is", len(uppercase_characters))
print("The no. of lowercase characters is", len(lowercase_characters))
print("The no. of numerical characters is", len(numerical_characters))
print("The no. of special characters is", len(special_characters))
```

**输出:**

```
The no. of uppercase characters is 4
The no. of lowercase characters is 15
The no. of numerical characters is 3
The no. of special characters is 4

```