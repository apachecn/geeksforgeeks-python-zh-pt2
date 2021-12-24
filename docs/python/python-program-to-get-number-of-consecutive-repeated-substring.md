# Python 程序获取连续重复子串的个数

> 原文:[https://www . geesforgeks . org/python-program-to-get-number-of-continued-repeated-substring/](https://www.geeksforgeeks.org/python-program-to-get-number-of-consecutive-repeated-substring/)

给定一个子串 K，任务是编写一个 Python 程序，在 K 的每次连续出现中找到 K 串的重复。

**例**

> **输入:** test_str = '极客是所有极客的极客，K = '极客'
> 
> **输出:**【2，3，1】
> 
> **解释:**第一个“极客”的连续是 2。
> 
> **输入:**test _ str = ' geeks geeks geeks geeks 适用于所有极客'，K = ' geeks "
> 
> **输出:**【2，4，1】
> 
> **说明:**第一个“极客”的连续是 2，接下来是 4 个极客的连续。

**方法一:使用** [**拆分()**](https://www.geeksforgeeks.org/python-string-split/) **+** [**计数()**](https://www.geeksforgeeks.org/python-string-count/) **+** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

仅适用于连续被空格分隔的特定情况。在这种情况下，使用 split()对每个单词进行拆分，并使用 count()对每个片段进行重复计数。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Number of repeated substrings in consecution
# Using split() + count() + list comprehension

# initializing string
test_str = 'geeksgeeks are geeksgeeksgeeks for all geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = "geeks"

# count() counts repetition
res = [sub.count(K) for sub in test_str.split(' ') if sub.count(K) != 0]

# printing result
print("String repetitions : " + str(res))
```

**输出:**

> 最初的字符串是:极客是所有极客的极客
> 
> 字符串重复:[2，3，1]

**方法二:使用**[**findall()**](https://www.geeksforgeeks.org/python-regex-re-search-vs-re-findall/)**+regex+**[**len()**](https://www.geeksforgeeks.org/python-string-length-len/)

在这种情况下，计算子串重复的所有游程，然后用子串长度除以长度得到重复数的度量。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Number of repeated substrings in consecution
# Using findall() + regex + len()
import re

# initializing string
test_str = 'geeksgeeksaregeeksgeeksgeeksforallgeeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = 'geeks'
n = len(K)

# getting regex
regx = re.compile(f'((?:{K})+)')

# getting repeats counts
# findall finding all substring joined repetitions
res = [len(occ) // n for occ in regx.findall(test_str)]

# printing result
print("String repetitions : " + str(res))
```

**输出:**

> 最初的字符串是:极客是所有极客的极客
> 
> 字符串重复:[2，3，1]