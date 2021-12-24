# 字符串列表中最常用单词的 Python 程序

> 原文:[https://www . geeksforgeeks . org/python-最常用单词串列表程序/](https://www.geeksforgeeks.org/python-program-for-most-frequent-word-in-strings-list/)

给定字符串列表，编写一个 Python 程序来获取出现次数最多的单词。

**示例:**

> **输入**:test _ list =【“gfg 最适合极客”、“极客爱 gfg”、“gfg 最好”】
> **输出** : gfg
> **说明** : gfg 出现 3 次，最多总共出现在字符串中。
> 
> **输入** : test_list =【“极客爱 gfg”，“极客最好”】
> **输出**:极客
> **解释**:极客出现 2 次，最多总共出现在字符串中。

**方法#1:使用 loop+**[**max()**](https://www.geeksforgeeks.org/python-max-function/)**+**[**split()**](https://www.geeksforgeeks.org/python-string-split/)**+**[**default dict()**](https://www.geeksforgeeks.org/defaultdict-in-python/)

在本练习中，我们使用 [split()](https://www.geeksforgeeks.org/python-string-split/) 执行获取每个单词的任务，并使用 [defaultdict()](https://www.geeksforgeeks.org/defaultdict-in-python/) 记忆单词来增加其频率。最后将 [max()](https://www.geeksforgeeks.org/python-max-function/) 与参数一起使用，得到最大频率串的个数。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Most frequent word in Strings List
# Using loop + max() + split() + defaultdict()
from collections import defaultdict

# initializing Matrix
test_list = ["gfg is best for geeks", "geeks love gfg", "gfg is best"]

# printing original list
print("The original list is : " + str(test_list))

temp = defaultdict(int)

# memoizing count
for sub in test_list:
    for wrd in sub.split():
        temp[wrd] += 1

# getting max frequency
res = max(temp, key=temp.get)

# printing result
print("Word with maximum frequency : " + str(res))
```

**输出:**

```py
The original list is : ['gfg is best for geeks', 'geeks love gfg', 'gfg is best']
Word with maximum frequency : gfg
```

**方法 2:使用列表理解+** [**模式()**](https://www.geeksforgeeks.org/python-statistics-mode-function/)

在这种情况下，我们使用列表理解获得所有单词，并使用[模式()](https://www.geeksforgeeks.org/python-statistics-mode-function/)获得最大频率。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Most frequent word in Strings List
# Using list comprehension + mode()
from statistics import mode

# initializing Matrix
test_list = ["gfg is best for geeks", "geeks love gfg", "gfg is best"]

# printing original list
print("The original list is : " + str(test_list))

# getting all words
temp = [wrd for sub in test_list for wrd in sub.split()]

# getting frequency
res = mode(temp)

# printing result
print("Word with maximum frequency : " + str(res))
```

**输出:**

```py
The original list is : ['gfg is best for geeks', 'geeks love gfg', 'gfg is best']
Word with maximum frequency : gfg
```

#### 方法 3:使用列表()和计数器()

*   将所有单词追加到空列表中，使用[**【Counter()**](https://www.geeksforgeeks.org/python-counter-objects-elements/)功能计算所有单词的出现频率。
*   找到最大计数并打印该密钥。

下面是实现:

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Most frequent word in Strings List

from collections import Counter

# function which returns
# most frequent word
def mostFrequentWord(words):

    # Taking empty list
    lis = []
    for i in words:

        # Getting all words
        for j in i.split():
            lis.append(j)

    # Calculating frequency of all words
    freq = Counter(lis)

    # find max count and print that key
    max = 0
    for i in freq:
        if(freq[i] > max):
            max = freq[i]
            word = i
            return word

# Driver code
# initializing strings list
words = ["gfg is best for geeks", "geeks love gfg", "gfg is best"]

# printing original list
print("The original list is : " + str(words))

# passing this words to mostFrequencyWord function
# printing result
print("Word with maximum frequency : " + mostFrequentWord(words))
# This code is contributed by vikkycirus
```

**输出:**

```py
The original list is : ['gfg is best for geeks', 'geeks love gfg', 'gfg is best']
Word with maximum frequency : gfg
```