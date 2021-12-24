# Python–K 的最长子串长度

> 原文:[https://www . geesforgeks . org/python-最长子串-长度为-k/](https://www.geeksforgeeks.org/python-longest-substring-length-of-k/)

给定一个字符串和一个字符 K，求 K 的最长子字符串长度

> **输入** : test_str = 'abcaaaacbbaa '，K = b
> **输出** : 2
> **解释** : b 出现两次，2 > 1。
> 
> **输入**:test _ str = ' abcccbbaa '，K = c
> **输出** : 3
> **解释**:c 出现的最大次数为 3。

**方法#1:使用循环**

这是解决这个问题的暴力方法，在这种情况下，当遇到 K 时，计数器被保持直到其他字符出现，并且计数被记录，这些计数的最大值被保持并且作为结果被返回。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Longest Substring of K
# Using loop

# initializing string
test_str = 'abcaaaacbbaa'

# printing original String
print("The original string is : " + str(test_str))

# initializing K 
K = 'a'

cnt = 0
res = 0
for idx in range(len(test_str)):

    # increment counter on checking
    if test_str[idx] == K:
        cnt += 1
    else:
        cnt = 0

    # retaining max
    res = max(res, cnt)

# printing result 
print("The Longest Substring Length : " + str(res)) 
```

**Output**

```
The original string is : abcaaaacbbaa
The Longest Substring Length : 4

```

**方法 2:使用 findall() + max()**

在这种情况下，我们使用 findall()获得 K 的所有可能的子串，并使用 max()获得以 len 为键的最大长度。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Longest Substring of K
# Using findall() + max()
import re

# initializing string
test_str = 'abcaaaacbbaa'

# printing original String
print("The original string is : " + str(test_str))

# initializing K 
K = 'a'

# getting all substrings
res = re.findall(r'' + K + '+', test_str)

# getting maximum of substrings Length
res = len(max(res, key = len))

# printing result 
print("The Longest Substring Length : " + str(res)) 
```

**Output**

```
The original string is : abcaaaacbbaa
The Longest Substring Length : 4

```