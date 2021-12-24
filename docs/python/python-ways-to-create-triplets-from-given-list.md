# Python |从给定列表中创建三元组的方法

> 原文:[https://www . geesforgeks . org/python-从给定列表创建三元组的方法/](https://www.geeksforgeeks.org/python-ways-to-create-triplets-from-given-list/)

给定一个单词列表，编写一个 Python 程序从给定的列表中创建三元组。

**示例:**

> **输入:**【‘Geeks’，‘for’，‘Geeks’，‘is’，‘best’，‘resource’，‘study’】
> **输出:**
> 【【‘Geeks’，‘for’，‘Geeks’，‘is’，
> 【‘Geeks’，‘is’，‘best’，‘resource’，
> 【‘best’，‘resource’，‘for’，【‘resource’，‘for’，‘study’】】
> 
> **输入:** ['I '，' am '，' Paras '，' Jain '，' I '，' Study '，' From '，' GFG']
> **输出:**
> [' I '，' am '，' Paras '，' Jain '，
> [' Paras '，' Jain '，' I '，' Study '，
> [' I '，' Study '，' From '，['Study '，' From '，' GFG']

让我们看看完成这项任务的一些方法。

**方法#1:** 使用列表理解

```py
# Python code to create triplets from list of words.

# List of word initialization
list_of_words = ['I', 'am', 'Paras', 'Jain',
                 'I', 'Study', 'DS', 'Algo']

# Using list comprehension
List = [list_of_words[i:i + 3] 
        for i in range(len(list_of_words) - 2)]

# printing list
print(List)
```

**Output:**

```py
[['I', 'am', 'Paras'], ['am', 'Paras', 'Jain'], 
 ['Paras', 'Jain', 'I'], ['Jain', 'I', 'Study'],
 ['I', 'Study', 'DS'], ['Study', 'DS', 'Algo']]

```

**方法#2:** 使用迭代

```py
# Python code to create triplets from list of words.

# List of word initialization
list_of_words = ['Geeks', 'for', 'Geeks', 'is',
                 'best', 'resource', 'for', 'study']

# Output list initialization
out = []

# Finding length of list
length = len(list_of_words)

# Using iteration
for z in range(0, length-2):
    # Creating a temp list to add 3 words
    temp = []
    temp.append(list_of_words[z])
    temp.append(list_of_words[z + 1])
    temp.append(list_of_words[z + 2])
    out.append(temp)

# printing output
print(out)
```

**Output:**

```py
[['Geeks', 'for', 'Geeks'], ['for', 'Geeks', 'is'],
 ['Geeks', 'is', 'best'], ['is', 'best', 'resource'],
 ['best', 'resource', 'for'], ['resource', 'for', 'study']]

```