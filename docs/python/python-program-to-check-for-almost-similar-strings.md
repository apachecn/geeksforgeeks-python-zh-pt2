# Python 程序检查几乎相似的字符串

> 原文:[https://www . geesforgeks . org/python-程序检查几乎相似的字符串/](https://www.geeksforgeeks.org/python-program-to-check-for-almost-similar-strings/)

给定两个字符串，这里的任务是编写一个 python 程序，可以测试它们是否几乎相似。字符串的相似性是根据每个字符的频率差的标准来检查的，该频率差应该大于这里用 k 表示的阈值

> **输入:**test _ str 1 =‘aabcdaa’，test _ str 2 = " abbaccd "，K = 2
> 
> **输出:**真
> 
> **解释:**“a”在 str1 中出现 4 次，在 str2 中出现 2 次，4–2 = 2，在 range 中，同样，所有字符都在 range 中，因此为 true。
> 
> **输入:**test _ str 1 =‘aabcdaaa’，test _ str 2 = " abbaccda "，K = 3
> 
> **输出:**真
> 
> **解释:**“a”在 str1 中出现 5 次，在 str2 中出现 3 次，5–3 = 2，在 range 中，同样，所有字符都在 range 中，因此为 true。

**方法一:** *使用*[*ascii _ Lowe case*](https://www.geeksforgeeks.org/python-string-ascii_lowercase/)*[*字典理解*](https://www.geeksforgeeks.org/python-dictionary-comprehension/)*[*循环*](https://www.geeksforgeeks.org/loops-in-python/) *和* [*abs()*](https://www.geeksforgeeks.org/abs-in-python/)**

**在这种情况下，我们使用字典理解和循环计算两个字符串中所有字符的所有频率。接下来，从字母小写 ascii 字符迭代每个字符，并使用 abs()测试两个字符串中的频率差异，如果任何差异计算为大于 K，则结果被标记为关闭。**

****例****

## **蟒蛇 3**

```
**from string import ascii_lowercase

# function to compute frequencies

def get_freq(test_str):

    # starting at 0 count
    freqs = {char: 0 for char in ascii_lowercase}

    # counting frequencies
    for char in test_str:
        freqs[char] += 1
    return freqs

# initializing strings
test_str1 = 'aabcdaa'
test_str2 = "abbaccd"

# printing original strings
print("The original string 1 is : " + str(test_str1))
print("The original string 2 is : " + str(test_str2))

# initializing K
K = 2

# getting frequencies
freqs_1 = get_freq(test_str1)
freqs_2 = get_freq(test_str2)

# checking for frequencies
res = True
for char in ascii_lowercase:
    if abs(freqs_1[char] - freqs_2[char]) > K:
        res = False
        break

# printing result
print("Are strings similar ? : " + str(res))**
```

****输出:****

> **原始字符串 1 是:aabcdaa**
> 
> **最初的字符串 2 是:abbaccd**
> 
> **字符串是否相似？:真**

****方法二:** *使用* [*计数器()*](https://www.geeksforgeeks.org/python-counter-objects-elements/) *和* [*max()*](https://www.geeksforgeeks.org/max-min-python/)**

**在本例中，我们使用 Counter()执行获取单个字符频率的任务，并使用 max()获取最大差值，如果大于 K，则结果被标记为 off。**

****示例:****

## **蟒蛇 3**

```
**from collections import Counter

# initializing strings
test_str1 = 'aabcdaa'
test_str2 = "abbaccd"

# printing original strings
print("The original string 1 is : " + str(test_str1))
print("The original string 2 is : " + str(test_str2))

# initializing K
K = 2

# extracting frequencies
cnt1 = Counter(test_str1.lower())
cnt2 = Counter(test_str2.lower())

# getting maximum difference
res = True
if max((cnt1 - cnt2).values()) > K or max((cnt2 - cnt1).values()) > K:
    res = False

# printing result
print("Are strings similar ? : " + str(res))**
```

****输出:****

> **原始字符串 1 是:aabcdaa**
> 
> **最初的字符串 2 是:abbaccd**
> 
> **字符串是否相似？:真**