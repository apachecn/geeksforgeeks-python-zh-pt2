# Python 程序到相等的字符频率

> 原文:[https://www . geesforgeks . org/python-程序到等字符频率/](https://www.geeksforgeeks.org/python-program-to-equal-character-frequencies/)

给定一个字符串，确保它有相等的字符频率，如果没有，通过添加所需的字符来相等。

> **输入**:test _ str = ' geesforgeks '
> **输出**:geesforgeeksggkkssfffoorr
> **解释**:最多字符为 4 个‘e’。其他字符以频率 4 –(字符数)追加。
> 
> **输入**:test _ str = ' geksforgeks '
> **输出**:geeksforgsggksfforr
> **解释**:最多字符为 3 个‘e’。其他字符以频率 3 –(字符数)追加。

**方法#1:使用 count() + max() +循环**

在这种情况下，我们得到最大出现字符的频率，然后附加每个字符以匹配最大字符频率。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Equal character frequencies
# Using max() + count() + loop

# initializing string
test_str = 'geeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# getting maximum frequency character 
max_freq = max([test_str.count(ele) for ele in test_str])

# equating frequencies 
res = test_str
for chr in test_str:

    # if frequencies don't match max_freq
    if res.count(chr) != max_freq:
        res += chr * (max_freq - test_str.count(chr))

# printing result 
print("Equal character frequency String : " + str(res)) 
```

**输出:**

```
The original string is : geeksforgeeks
Equal character frequency String : geeksforgeeksggkkssfffooorrr
```

**方法 2:使用 Counter() +循环**

与上面类似，不同之处在于 Counter()用于获取最大元素计数。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Equal character frequencies
# Using Counter() + loop 
from collections import Counter

# initializing string
test_str = 'geeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# getting maximum frequency character 
# using Counter()
freq_dict = Counter(test_str) 
max_freq = test_str.count(max(freq_dict, key = freq_dict.get)) 

# equating frequencies 
res = test_str
for chr in test_str:

    # if frequencies don't match max_freq
    if res.count(chr) != max_freq:
        res += chr * (max_freq - test_str.count(chr))

# printing result 
print("Equal character frequency String : " + str(res)) 
```

**输出:**

```
The original string is : geeksforgeeks
Equal character frequency String : geeksforgeeksggkkssfffooorrr
```