# Python–正则表达式向后看

> 原文:[https://www.geeksforgeeks.org/python-regex-lookbehind/](https://www.geeksforgeeks.org/python-regex-lookbehind/)

**Regex lookup behind**在 Python 中用作断言[正则表达式(re)](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/) 来判断模式是成功还是失败，即在解析器当前位置的右侧。它们什么都不匹配。因此，Regex 后视和[前视](https://www.geeksforgeeks.org/python-regex-lookahead/)被称为零宽度断言。

**语法:**

```py
# Positive lookbehind
(?<=<lookbehind_regex>)

# Positive lookahead
(?=<lookahead_regex>)
```

在这篇文章中，我们将讨论正则表达式的后视。

**例 1:**

## 蟒蛇 3

```py
# importing regex
import re

# Regex Lookbehind example
example = re.search(r'(?<=geeks)\w', 
                    'geeksforgeeks')

print(example.group())
print("Pattern found from index", 
      example.start(), example.end())
```

**输出:**

```py
f
Pattern found from index 5 6
```

正则表达式后视断言*(？<=极客)*指定任何单词字符(“\w”)之前的必须是“极客”字符串。在这种情况下，“极客”字符串出现在字符“f”之前。

**例 2:**

## 蟒蛇 3

```py
# importing regex
import re

# Regex Lookbehind example
example = re.search(r'(?<=geeks)\d', 
                    'geeksforgeeks')
print(example)
```

**输出:**

```py
None
```

在上面的例子中，输出是无，因为前面没有“极客”字符串的十进制数字。

lookback 部分不是搜索字符串的一部分。当您不想让输出返回搜索字符串中的后视部分，但想用它来匹配前面有特定部分的模式时，它们就很重要。下面的例子将说明这一点:

**例 3:**

## 蟒蛇 3

```py
import re

# Using lookbehind
example1 = re.search(r'(?<=[a-z])\d',
                     "geeks12")
print(example1.group())

# Without using lookbehind
example2 = re.search(r'([a-z])\d',
                     "geeks12")
print(example2.group())
```

**输出:**

```py
1
s1
```

使用 lookback 时，生成的输出为“1”，而不使用 lookback 时，生成的输出为“s1”。任何十进制数字之前的任何单词字符(\w)都会被正则表达式使用，因此它不会成为搜索字符串的一部分。

**消极观望**

消极落后是落后的反义词。这是为了确保搜索字符串的前面没有*<lookback _ regex>*。

**语法:**

```py
(?<!<lookbehind_regex>) 
Negative Lookbehind
```

**例 4:**

## 蟒蛇 3

```py
import re

# Lookbehind
example1 = re.search('(?<=[a-z])geeks', 
                     'geeksforgeeks')
print(example1.group())

# Negative Lookbehind
example2 = re.search('(?<![a-z])123', 
                     'geeks123')

# Output is None because 123 
# is preceded by a character i.e 's'
print(example2)
```

**输出:**

```py
geeks
None
```