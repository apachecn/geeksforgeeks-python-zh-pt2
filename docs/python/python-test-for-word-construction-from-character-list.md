# Python–测试字符列表中的单词结构

> 原文:[https://www . geeksforgeeks . org/python-从字符列表中测试单词结构/](https://www.geeksforgeeks.org/python-test-for-word-construction-from-character-list/)

给定一个列表和一个字符串，测试该字符串是否可以由列表字符组成。

**示例:**

> **输入** : test_list = ['g '，' g '，' e '，' k '，' s '，' 4 '，' g '，' g '，' e '，' s '，' e '，' 4 '，' k']，test_str = 'geeks4geeks'
> **输出** : True
> **说明**:可以根据字符频率进行字符串。
> 
> **输入** : test_list = ['s '，' 4 '，' g '，' g '，' e '，' s '，' e '，' e '，' 4 '，' k']，test_str = 'geeks4geeks'
> **输出** : False
> **说明**:字符串不能根据字符频率制作。

**方法#1:使用**[**all()**](https://www.geeksforgeeks.org/any-all-in-python/)**+**[**count()**](https://www.geeksforgeeks.org/python-string-count/)

在这种情况下，我们测试字符串中的所有字符计数是否小于列表中每个字符的频率。使用 count()提取频率。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Test for Word construction from character list
# Using all() + count()

# initializing list
test_list = ['g', 'g', 'e', 'k', 's', '4', 'g',
             'g', 'e', 's', 'e', 'e', '4', 'k']

# printing original list
print("The original list is : " + str(test_list))

# initializing string 
test_str = 'geeks4geeks'

# checking for frequency of chars less than in list
res = all(test_str.count(chr) <= test_list.count(chr) for chr in test_str)

# printing result
print("Is word construction possible ? : " + str(res))
```

**输出:**

> 原列表为:['g '，' g '，' e '，' k '，' s '，' 4 '，' g '，' g '，' e '，' s '，' e '，' e '，' 4 '，' k']
> 构词法可能吗？:真

**方法 2:使用计数器()**

在本文中，我们使用 Counter()计算频率，然后从列表字符中减去单词。在空列表的情况下，意味着不可能形成一个单词。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Test for Word construction from character list
# Using Counter()
from collections import Counter

# initializing list
test_list = ['g', 'g', 'e', 'k', 's', '4', 'g',
             'g', 'e', 's', 'e', 'e', '4', 'k']

# printing original list
print("The original list is : " + str(test_list))

# initializing string 
test_str = 'geeks4geeks'

# checking for frequency of chars less than in list
res = not bool(dict(Counter(test_str) - Counter(test_list)))

# printing result
print("Is word construction possible ? : " + str(res))
```

**输出:**

> 原列表为:['g '，' g '，' e '，' k '，' s '，' 4 '，' g '，' g '，' e '，' s '，' e '，' e '，' 4 '，' k']
> 构词法可能吗？:真