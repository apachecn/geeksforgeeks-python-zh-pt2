# Python–字符串缩写中的词频

> 原文:[https://www . geesforgeks . org/python-words-in-string-frequency-short hands/](https://www.geeksforgeeks.org/python-words-frequency-in-string-shorthands/)

有时在使用 Python 字符串时，我们会遇到需要提取字符串中所有单词的频率的问题。这个问题早就解决了。本文讨论了解决这个问题的捷径，因为它在许多领域都有应用，从 web 开发到竞争性编程。让我们讨论一下解决这个问题的某些方法。

> **输入** : test_str = 'Gfg 最好'
> **输出** : {'Gfg': 1，' is': 1，'最好':1}
> 
> **输入**:test _ str = ' Gfg Gfg '
> **输出** : {'Gfg': 3}

**方法#1:使用字典理解+ `count() + split()`**
以上功能的组合可以用来解决这个问题。在本例中，我们首先拆分所有单词，然后使用 count()对它们进行计数。

```py
# Python3 code to demonstrate working of 
# Words Frequency in String Shorthands
# Using dictionary comprehension + count() + split()

# initializing string
test_str = 'Gfg is best . Geeks are good and Geeks like Gfg'

# printing original string
print("The original string is : " + str(test_str))

# Words Frequency in String Shorthands
# Using dictionary comprehension + count() + split()
res = {key: test_str.count(key) for key in test_str.split()}

# printing result 
print("The words frequency : " + str(res)) 
```

**Output :**

> 原来的字符串是:Gfg 最好。极客是好的，极客喜欢 Gfg
> 词频:{'Gfg': 2，' is': 1，' best': 1，':1、“极客”:2、“是”:1、“好”:1、“和”:1、“喜欢”:1}

**方法 2:使用`Counter() + split()`**
以上方法的组合也可以用来解决这个问题。在本文中，我们使用 Counter()执行计数任务，使用 split()执行单词分离。

```py
# Python3 code to demonstrate working of 
# Words Frequency in String Shorthands
# Using Counter() + split()
from collections import Counter

# initializing string
test_str = 'Gfg is best . Geeks are good and Geeks like Gfg'

# printing original string
print("The original string is : " + str(test_str))

# Words Frequency in String Shorthands
# Using Counter() + split()
res = Counter(test_str.split())

# printing result 
print("The words frequency : " + str(dict(res))) 
```

**Output :**

> 原来的字符串是:Gfg 最好。极客是好的，极客喜欢 Gfg
> 词频:{'Gfg': 2，' is': 1，' best': 1，':1、“极客”:2、“是”:1、“好”:1、“和”:1、“喜欢”:1}