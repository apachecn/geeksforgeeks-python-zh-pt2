# Python 字符串| capwords()方法

> 原文:[https://www . geesforgeks . org/python-string-capwords-method/](https://www.geeksforgeeks.org/python-string-capwords-method/)

在 Python 中，字符串 **capwords()** 方法用于使用 split()方法大写字符串中的所有单词。

> **语法:** string.capwords(string，sep=None)
> **返回值:**执行上述操作后返回格式化字符串。

使用 Split 将参数拆分成单词，使用大写字母将每个单词大写，使用 join 将大写单词连接起来。如果可选的第二个参数 **sep** 不存在或**无**，空格字符的运行将被替换为一个空格，前导和尾随空格将被删除，否则 **sep** 将用于拆分和连接单词。
**代码#1:** 如果 **sep** 参数为左**无**。

## 蟒蛇 3

```py
# imports string module
import string

sentence = 'Python is one of the best programming languages.'

# sep parameter is left None
formatted = string.capwords(sentence, sep = None)

print(formatted)
```

**Output:** 

```py
Python Is One Of The Best Programming Languages.
```

**代码#2:** 当**九月**不是**无。**

## 蟒蛇 3

```py
# imports string module
import string

sentence = 'Python is one of the best programming languages.'

# sep parameter is 'g'
formatted = string.capwords(sentence, sep = 'g')
print('When sep = "g"', formatted)

# sep parameter is 'o'
formatted = string.capwords(sentence, sep = 'o')
print('When sep = "o"', formatted)
```

**Output:** 

```py
When sep = "g" Python is one of the best progRamming langUagEs.
When sep = "o" PythoN is oNe oF the best proGramming languages.
```