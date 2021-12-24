# Python–最大评分词

> 原文:[https://www.geeksforgeeks.org/python-maximum-scoring-word/](https://www.geeksforgeeks.org/python-maximum-scoring-word/)

给定一个字符串，任务是编写一个 Python 程序来计算最大得分单词，即由具有最大位置总和的字符组成的单词。

**示例:**

> **输入:** test_str = '极客必须使用极客 forgeeks 获取 cs 知识'
> 
> **输出:**极客暴发户
> 
> **说明:**极客单词的字符位置值之和最大，因此为结果。
> 
> **输入:** test_str = '极客爱极客 forgeeks '
> 
> **输出:**极客暴发户
> 
> **说明:**极客单词的字符位置值之和最大，因此为结果。

**方法#1:使用**[**split()**](https://www.geeksforgeeks.org/python-string-split/)**+loop+**[**order()**](https://www.geeksforgeeks.org/ord-function-python/)**+**[**ascii _ 小写**](https://www.geeksforgeeks.org/python-string-ascii_lowercase/)

在本文中，我们首先使用 split()拆分每个单词，使用 order()获取位置大小，ascii _ 小写检查选择用于评估的字符池是否正确。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Maximum Scoring word
# Using split() + loop + ord() + ascii_lowercase
import string

# initializing string
test_str = 'geeks must use geeksforgeeks for cs knowledge'

# printing original string
print("The original string is : " + str(test_str))

score = 0
max_sc = 0
res = ''
for wrd in test_str.split():
    score = 0
    # computing score
    for lttr in wrd:
        if lttr in string.ascii_lowercase:
            score += ord(lttr) - 96

    # updating maximum
    if score > max_sc:
        max_sc = score
        res = wrd

# printing result
print("Maximum scoring word : " + str(res))
```

**输出:**

```
The original string is : geeks must use geeksforgeeks for cs knowledge
Maximum scoring word : geeksforgeeks
```

**方法 2:使用**[**sum()**](https://www.geeksforgeeks.org/sum-function-python/)**+loop+order()**

与上述方法类似，这里唯一的区别是 sum()用于求和任务，而不是内部循环。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Maximum Scoring word
# Using sum() + loop + ord()
import string

# initializing string
test_str = 'geeks must use geeksforgeeks for cs knowledge'

# printing original string
print("The original string is : " + str(test_str))

score = 0
max_sc = 0
res = ''
for wrd in test_str.split():

    # computing score
    # sum for cumulation
    score = sum(ord(lttr) - 96 for lttr in wrd if lttr in string.ascii_lowercase)

    # updating maximum
    if score > max_sc:
        max_sc = score
        res = wrd

# printing result
print("Maximum scoring word : " + str(res))
```

**输出:**

```
The original string is : geeks must use geeksforgeeks for cs knowledge
Maximum scoring word : geeksforgeeks
```