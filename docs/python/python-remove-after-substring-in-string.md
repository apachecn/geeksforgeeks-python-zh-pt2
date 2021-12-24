# Python–删除字符串中的子字符串后

> 原文:[https://www . geesforgeks . org/python-字符串中的子字符串后移除/](https://www.geeksforgeeks.org/python-remove-after-substring-in-string/)

给定一个字符串，删除特定子字符串后的所有字符。

> **输入** : test_str = 'geeksforgeeks 最适合极客'，sub_str = '适合"
> **输出** : geeksforgeeks 最适合
> **解释**:for 之后移除的所有内容。
> 
> **输入** : test_str = 'geeksforgeeks 最适合极客'，sub _ str = ' is "
> **输出** : geeksforgeeks is
> **解释**:is 后移除的一切。

**方法#1:使用 index() + len() +切片**

在这种情况下，我们首先获取要执行移除的子字符串的索引，然后使用 len()将它的长度添加到该索引中，然后使用 slicing 将该字符串之后的元素切片。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Remove after substring in String
# Using index() + len() + slicing

# initializing strings
test_str = 'geeksforgeeks is best for geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing sub string 
sub_str = "best"

# slicing off after length computation
res = test_str[:test_str.index(sub_str) + len(sub_str)]

# printing result 
print("The string after removal : " + str(res)) 
```

**Output**

```
The original string is : geeksforgeeks is best for geeks
The string after removal : geeksforgeeks is best

```

**方法 2:使用正则表达式() (用于数值出现后的剥离)**

这是一个稍微不同的问题的解决方案，在这个问题中，数字出现后需要移除字符串。我们使用匹配操作，它在找到匹配之前保留所有内容。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Remove after substring in String
# Using regex() ( for stripping off after numeric occurrence)
import re

# initializing strings
test_str = 'geeksforgeeks is best 4 geeks'

# printing original string
print("The original string is : " + str(test_str))

# slicing after the numeric occurrence
res = re.match(r"(.*\d+)", test_str).group()

# printing result 
print("The string after removal : " + str(res)) 
```

**Output**

```
The original string is : geeksforgeeks is best 4 geeks
The string after removal : geeksforgeeks is best 4

```