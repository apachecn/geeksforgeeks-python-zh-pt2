# Python–正则表达式前瞻

> 原文:[https://www.geeksforgeeks.org/python-regex-lookahead/](https://www.geeksforgeeks.org/python-regex-lookahead/)

**前瞻**在 Python [正则表达式](https://www.geeksforgeeks.org/python-regex/)中用作断言，以确定模式是成功还是失败，即在解析器当前位置的右侧。它们什么都不匹配。因此，它们被称为零宽度断言。

**语法:**

```py
# Positive lookahead
(?=<lookahead_regex>)

```

**例 1:**

## 蟒蛇 3

```py
# importing regex
import re

# lookahead example
example = re.search(r'geeks(?=[a-z])', "geeksforgeeks")

# display output
print("Pattern:", example.group())
print("Pattern found from index:",
      example.start(), "to",
      example.end())
```

**输出:**

```py
Pattern: geeks
Pattern found from index: 0 to 5
```

前瞻断言*(？=[a-z])* 指定跟随*极客*的必须是小写字母字符。在这种情况下，是角色 *f* ，找到匹配。

**例 2:**

## 蟒 3

```py
# importing regex
import re

# Lookahead example
example = re.search(r'geeks(?=[a-z])', 
                    "geeks123")

# output
print(example)
```

**输出:**

```py
None
```

在上面的例子中，输出是 None，因为极客之后的下一个字符是 1。它不是小写字母字符。

前瞻部分不是搜索字符串的一部分。因此，它被称为**零宽度断言。**当您不希望输出返回搜索字符串中的前瞻部分，但希望使用它来匹配特定部分后面的模式时，它们很重要。下面的例子将说明这一点。

**例 3:**

## 蟒 3

```py
# import required module
import re

# using lookahead
example1 = re.search(r'geeks(?=[a-z])',
                     "geeksforgeeks")

print('Using lookahead:', example1.group())

# without using lookahead
example2 = re.search(r'geeks([a-z])',
                     "geeksforgeeks")

print('Without using lookahead:', example2.group())
```

**输出:**

```py
Using lookahead: geeks
Without using lookahead: geeksf
```

使用前瞻生成的输出是“极客”，而不使用前瞻生成的输出是*极客*。 *f* 被正则表达式使用，并成为搜索字符串的一部分。

**负前瞻**与前瞻相反。这是为了确保搜索字符串后面没有跟随<前瞻 _ 正则表达式>。

**语法:**

```py
# Negative Lookahead
(?!<lookahead_regex>) 

```

**例 4:**

## 蟒 3

```py
# import required module
import re

# positive lookahead
example1 = re.search('geeks(?=[a-z])',
                     'geeksforgeeks')
print('Positive Lookahead:', example1.group())

# negative lookahead
example2 = re.search('geeks(?![a-z])',
                     'geeks123')
print('Negative Lookahead:', example2.group())
```

**输出:**

```py
Positive Lookahead: geeks
Negative Lookahead: geeks
```

在上面的例子中，输出是极客，因为这里的搜索字符串*极客*后面没有小写字母。