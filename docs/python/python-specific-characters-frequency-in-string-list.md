# Python–字符串列表中的特定字符频率

> 原文:[https://www . geesforgeks . org/python-特定字符-字符串中的频率列表/](https://www.geeksforgeeks.org/python-specific-characters-frequency-in-string-list/)

给定字符串列表，提取整个字符串列表中特定字符的频率。

> **输入** : test_list = [“极客 forgeeks 最适合极客”]，chr_list = ['e '，' b '，' g '，' f']
> **输出** : {'g': 3，' e': 7，' b': 1，' f' : 1}
> **解释**:提取某些字符的频率。
> 
> **输入** : test_list = ["geeksforgeeks "，chr_list = ['e '，' g']
> **输出** : {'g': 2，' e': 4}
> **解释**:提取某些字符的频率。

**方法#1:使用 join() + Counter()**

在这种情况下，我们连接所有的字符串，然后 Counter()执行获取所有频率的任务。最后一步是使用字典理解从字典列表中仅获取特定字符。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Specific Characters Frequency in String List
# Using join() + Counter()
from collections import Counter

# initializing lists
test_list = ["geeksforgeeks is best for geeks"]

# printing original list
print("The original list : " + str(test_list))

# char list 
chr_list = ['e', 'b', 'g']

# dict comprehension to retrieve on certain Frequencies
res = {key:val for key, val in dict(Counter("".join(test_list))).items() if key in chr_list}

# printing result 
print("Specific Characters Frequencies : " + str(res))
```

**Output**

```
The original list : ['geeksforgeeks is best for geeks']
Specific Characters Frequencies : {'g': 3, 'e': 7, 'b': 1}

```

**方法 2:使用 chain . from _ iterable()+Counter()+字典理解**

在本例中，连接任务是使用 chain.from_iterable()而不是 join()完成的。其余所有任务均按上述方法完成。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Specific Characters Frequency in String List
# Using chain.from_iterable() + Counter() + dictionary comprehension
from collections import Counter
from itertools import chain

# initializing lists
test_list = ["geeksforgeeks is best for geeks"]

# printing original list
print("The original list : " + str(test_list))

# char list 
chr_list = ['e', 'b', 'g']

# dict comprehension to retrieve on certain Frequencies
# from_iterable to flatten / join
res = {key:val for key, val in dict(Counter(chain.from_iterable(test_list))).items() if key in chr_list}

# printing result 
print("Specific Characters Frequencies : " + str(res))
```

**Output**

```
The original list : ['geeksforgeeks is best for geeks']
Specific Characters Frequencies : {'g': 3, 'e': 7, 'b': 1}

```