# Python–连续字符频率

> 原文:[https://www . geesforgeks . org/python-sequence-characters-frequency/](https://www.geeksforgeeks.org/python-successive-characters-frequency/)

有时，在使用 Python 字符串时，我们可能会遇到一个问题，即我们需要找到字符串中特定单词的下一个字符的频率。这是一个非常独特的问题，在日常编程和 web 开发中具有应用潜力。让我们讨论执行这项任务的某些方法。

> **输入** : test_str = 'geeks 代表 geeksforgeeks '，que _ word = ' geek "
> **输出** : {'s': 3}
> 
> **输入** : test_str = 'geek '，que _ word = ' geek "
> **输出** : {}

**方法#1:使用 loop + `count() + re.findall()`**
以上方法的组合构成了执行此任务的蛮力法。在本例中，我们使用 count()执行计数任务，并使用 findall()搜索字符。

```py
# Python3 code to demonstrate working of 
# Successive Characters Frequency
# Using count() + loop + re.findall()
import re

# initializing string
test_str = 'geeksforgeeks is best for geeks. A geek should take interest.'

# printing original string
print("The original string is : " + str(test_str))

# initializing word 
que_word = "geek"

# Successive Characters Frequency
# Using count() + loop + re.findall()
temp = []
for sub in re.findall(que_word + '.', test_str):
    temp.append(sub[-1])

res = {que_word : temp.count(que_word) for que_word in temp}

# printing result 
print("The Characters Frequency is : " + str(res))
```

**Output :**

```py
The original string is : geeksforgeeks is best for geeks. A geek should take interest.
The Characters Frequency is : {'s': 3, ' ': 1}

```

**方法 2:使用`Counter() + list comprehension + re.findall()`**
上述功能的组合用于执行以下任务。在本文中，我们使用 Counter()代替 count()来解决这个问题。适用于较新版本的 Python。

```py
# Python3 code to demonstrate working of 
# Successive Characters Frequency
# Using Counter() + list comprehension + re.findall()
from collections import Counter
import re

# initializing string
test_str = 'geeksforgeeks is best for geeks. A geek should take interest.'

# printing original string
print("The original string is : " + str(test_str))

# initializing word 
que_word = "geek"

# Successive Characters Frequency
# Using Counter() + list comprehension + re.findall()
res = dict(Counter(re.findall(f'{que_word}(.)', test_str, 
                                    flags=re.IGNORECASE)))

# printing result 
print("The Characters Frequency is : " + str(res))
```

**Output :**

```py
The original string is : geeksforgeeks is best for geeks. A geek should take interest.
The Characters Frequency is : {'s': 3, ' ': 1}

```