# Python–删除包含列表字符的单词

> 原文:[https://www . geesforgeks . org/python-remove-words-containing-list-characters/](https://www.geeksforgeeks.org/python-remove-words-containing-list-characters/)

有时，在数据过滤的过程中，我们会遇到一个问题，即我们需要删除由某些字母组成的单词。这种应用在数据科学领域很常见。让我们讨论执行这项任务的某些方法。

**方法一:使用`all()` +列表理解**
以上方法的组合可以用来执行此任务。在这种情况下，我们只需在每个列表中使用 all()检查所有列表字符，并过滤掉包含任何一个字符的字符串。

```py
# Python3 code to demonstrate 
# Remove words containing list characters
# using list comprehension + all()
from itertools import groupby

# initializing list 
test_list = ['gfg', 'is', 'best', 'for', 'geeks']

# initializing char list 
char_list = ['g', 'o']

# printing original list
print ("The original list is : " + str(test_list))

# printing character list
print ("The character list is : " + str(char_list))

# Remove words containing list characters
# using list comprehension + all()
res = [ele for ele in test_list if all(ch not in ele for ch in char_list)]

# printing result 
print ("The filtered strings are : " + str(res))
```

**Output :**

```py
The original list is : ['gfg', 'is', 'best', 'for', 'geeks']
The character list is : ['g', 'o']
The filtered strings are : ['is', 'best']

```