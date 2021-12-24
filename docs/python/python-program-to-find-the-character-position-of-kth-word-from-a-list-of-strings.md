# Python 程序从字符串列表中找到第 k 个单词的字符位置

> 原文:[https://www . geesforgeks . org/python-program-to-find-the-character-position-of-kth-word-from-list-strings/](https://www.geeksforgeeks.org/python-program-to-find-the-character-position-of-kth-word-from-a-list-of-strings/)

给定一个字符串列表。任务是找到单词的字符位置索引，它位于字符串列表中的第 Kth 个索引处。

**示例:**

> **输入**:test _ list =[“geek forgeeks”“is”“best”“for”“geek”]，K = 21
> **输出** : 0
> **解释**:第 21 个索引出现在“geek”中，指向“g”，即单词的第 0 个元素。
> 
> **输入**:test _ list =[“geek forgeks”“is”“best”“for”“geek”]，K = 15
> **输出** : 1
> **说明**:第 15 个索引出现在“best”中，指向“e”，即单词的第 1 个元素。

**方法一:使用 enumerate() +列表理解**

在这种情况下，我们使用嵌套的[枚举()](https://www.geeksforgeeks.org/enumerate-in-python/)来检查列表中单词和字符串的索引，列表理解用于将逻辑封装在 1 行中。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Word Index for K position in Strings List
# Using enumerate() + list comprehension

# initializing list
test_list = ["geekforgeeks", "is", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 20

# enumerate to get indices of all inner and outer list
res = [ele[0] for sub in enumerate(test_list) for ele in enumerate(sub[1])]

# getting index of word
res = res[K]

# printing result
print("Index of character at Kth position word : " + str(res))
```

**Output**

> 原列表为:['极客 forgeks '，' is '，' best '，' for '，'极客']
> 第 k 个位置的人物索引字:2

**方法 2:使用 next() + zip() + count()**

在这种情况下，我们使用 [zip()](https://www.geeksforgeeks.org/zip-in-python/) 将单词的数量与其计数配对，并累积直到我们没有达到 Kth Index。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Word Index for K position in Strings List
# Using next() + zip() + count()
from itertools import count

# initializing list
test_list = ["geekforgeeks", "is", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 20

# count() for getting count
# pairing using zip()
cnt = count()
res = next(j for sub in test_list for j, idx in zip(
    range(len(sub)), cnt) if idx == K)

# printing result
print("Index of character at Kth position word : " + str(res))
```

**Output**

> 原列表为:['极客 forgeks '，' is '，' best '，' for '，'极客']
> 第 k 个位置的人物索引字:2