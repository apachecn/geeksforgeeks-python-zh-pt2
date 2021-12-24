# Python–相似字符串比较

> 原文:[https://www . geesforgeks . org/python-相似-字符-字符串-比较/](https://www.geeksforgeeks.org/python-similar-characters-strings-comparison/)

给定两个由 delim 分隔的字符串，检查两者是否包含相同的字符。

> **输入** : test_str1 = 'e！e！k！s！' g '，test_str2 = 'g！e！e！k！s '，delim = '！'
> **输出**:真
> **说明**:人物相同，只是不同。位置。
> 
> **输入** : test_str1 = 'e！e！k！s '，test_str2 = 'g！e！e！k！s '，delim = '！'
> **输出**:假
> **解释**:第一弦 g 缺失。

**方法#1:使用排序()+拆分()**

在这种情况下，我们使用 split()执行拆分，然后执行排序任务以按顺序获取字符串，然后使用比较运算符比较字符串。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Similar characters Strings comparison
# Using split() + sorted()

# initializing strings
test_str1 = 'e:e:k:s:g'
test_str2 = 'g:e:e:k:s'

# printing original strings
print("The original string 1 is : " + str(test_str1))
print("The original string 2 is : " + str(test_str2))

# initializing delim 
delim = ':'

# == operator is used for comparison
res = sorted(test_str1.split(':')) == sorted(test_str2.split(':'))

# printing result 
print("Are strings similar : " + str(res)) 
```

**Output**

```py
The original string 1 is : e:e:k:s:g
The original string 2 is : g:e:e:k:s
Are strings similar : True

```

**方法 2:使用 set() + split()**

在这种情况下，我们将字符串转换为 set()，而不是 sort()，以获得排序。这仅适用于唯一的字符串。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Similar characters Strings comparison
# Using set() + split()

# initializing strings
test_str1 = 'e:k:s:g'
test_str2 = 'g:e:k:s'

# printing original strings
print("The original string 1 is : " + str(test_str1))
print("The original string 2 is : " + str(test_str2))

# initializing delim 
delim = ':'

# == operator is used for comparison
# removes duplicates and compares
res = set(test_str1.split(':')) == set(test_str2.split(':'))

# printing result 
print("Are strings similar : " + str(res)) 
```

**Output**

```py
The original string 1 is : e:k:s:g
The original string 2 is : g:e:k:s
Are strings similar : True

```