# Python–字符最独特的字符串

> 原文:[https://www . geesforgeks . org/python-最多唯一字符的字符串/](https://www.geeksforgeeks.org/python-string-with-most-unique-characters/)

有时，在使用 python 字符串时，我们可能会遇到这样的问题:我们希望提取具有最多唯一字符的特定列表。这类问题可以应用于竞争性编程和 web 开发领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用 max() +字典理解**
以上功能的组合可用于执行此任务。在这种情况下，我们首先使用字典收集每个字符的频率，然后使用 max()来计算具有最多唯一字符的字符串。

```
# Python3 code to demonstrate 
# String with most unique characters
# using max() + dictionary comprehension

# Initializing list
test_list = ['gfg', 'is', 'best', 'for', 'geeksc']

# printing original list
print("The original list is : " + str(test_list))

# String with most unique characters
# using max() + dictionary comprehension
temp =  {idx : len(set(idx)) for idx in test_list}
res = max(temp, key = temp.get)

# printing result 
print ("The string with most unique characters is : " + str(res))
```

**Output :**

```
The original list is : ['gfg', 'is', 'best', 'for', 'geeksc']
The string with most unique characters is : geeksc

```