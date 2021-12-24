# Python–N 个重复 K 字符的非重叠出现

> 原文:[https://www . geesforgeks . org/python-非重叠-出现-n-重复-k-字符/](https://www.geeksforgeeks.org/python-non-overlapping-occurrences-of-n-repeated-k-character/)

给定一个字符串，计算 N 个重复的 K 字符的非重叠出现。

> **输入**:test _ str = ' aabaaabbaa '，K = ' a '，N = 3
> **输出** : 2
> **解释**:“AAA”出现两次为非重叠运行。
> 
> **输入**:test _ str = ' aaabaaabbbaa '，K = ' b '，N = 3
> **输出** : 1
> **解释**:“BBB”作为非重叠运行出现一次。

**方法#1:使用 sum() + split() [仅适用于双字符串]**

在这种情况下，在除了 K 之外的字符上执行分割，然后计算每个片段的出现次数，并使用 sum()对频率求和。这适用于仅包含 2 个唯一字符的字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Non-Overlapping occurrences of N Repeated K character
# Using split() + sum

# initializing string
test_str = 'aaabaaaabbaa'

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = "a"

# initializing N 
N = 2

# getting split char
spl_char = [ele for ele in test_str if ele != K][0]

# getting split list 
temp = test_str.split(spl_char)

# getting Non-Overlapping occurrences
res = sum( len(sub) // N for sub in temp)

# printing result 
print("The Non-Overlapping occurrences : " + str(res)) 
```

**Output**

```
The original string is : aaabaaaabbaa
The Non-Overlapping occurrences : 4

```

**方法 2:使用 re.findall()**

这是执行该任务的另一种方式。这可以处理所有类型的字符串，并使用正则表达式()来解决这个问题。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Non-Overlapping occurrences of N Repeated K character
# Using re.findall()
import re

# initializing string
test_str = 'aaabaaaabbaa'

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = "a"

# initializing N 
N = 2

# getting length using len()
# getting all occ. of substring
res = len(re.findall(K * N, test_str))

# printing result 
print("The Non-Overlapping occurrences : " + str(res)) 
```

**Output**

```
The original string is : aaabaaaabbaa
The Non-Overlapping occurrences : 4

```