# Python–删除标点元组

> 原文:[https://www . geesforgeks . org/python-remove-标点-元组/](https://www.geeksforgeeks.org/python-remove-punctuation-tuples/)

有时，在使用 Python 元组时，我们可能会遇到一个问题，即我们需要删除元组中包含标点符号的所有元组。这种问题可能发生在数据过滤应用程序中。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [(' . ', ', '), ('!'，8)】
> T3】输出:【】
> 
> **输入** : test_list = [(1，3)，(3，8)]
> **输出** : [(1，3)，(3，8)]

**方法#1:使用`any() + list comprehension + string.punctuation`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 string .标点符号执行识别标点符号的任务，any()用于测试元素是否属于任何标点符号。

```
# Python3 code to demonstrate working of 
# Remove Punctuation Tuples
# Using any() + list comprehension + string.punctuation
import string

# initializing list
test_list = [('.', ', '), ('!', 8), (5, 6), (';', 10)]

# printing original list
print("The original list is : " + str(test_list))

# Remove Punctuation Tuples
# Using any() + list comprehension + string.punctuation
res = [idx for idx in test_list if not any(punc in idx 
                      for punc in string.punctuation)]

# printing result 
print("Tuples after punctuation removal : " + str(res)) 
```

**Output :**

```
The original list is : [('.', ', '), ('!', 8), (5, 6), (';', 10)]
Tuples after punctuation removal : [(5, 6)]

```

**方法 2:使用`regex() + filter() + lambda + string.punctuation`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用正则表达式执行标点符号识别任务，并使用 filter() + lambda 进行过滤。仅限于处理字符串和检查特定索引。

```
# Python3 code to demonstrate working of 
# Remove Punctuation Tuples
# Using regex() + filter() + lambda + string.punctuation
import string
import re

# initializing list
test_list = [('.', ', '), ('!', '8'), ('5', '6'), (';', '10')]

# printing original list
print("The original list is : " + str(test_list))

# Remove Punctuation Tuples
# Using regex() + filter() + lambda + string.punctuation
temp = re.compile('[{}]'.format(re.escape(string.punctuation)))
res = list(filter(lambda tup: not temp.search(tup[0]), test_list))

# printing result 
print("Tuples after punctuation removal : " + str(res)) 
```

**Output :**

```
The original list is : [('.', ', '), ('!', '8'), ('5', '6'), (';', '10')]
Tuples after punctuation removal : [('5', '6')]

```