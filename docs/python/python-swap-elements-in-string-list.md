# Python–交换字符串列表中的元素

> 原文:[https://www . geeksforgeeks . org/python-swap-elements in-string-list/](https://www.geeksforgeeks.org/python-swap-elements-in-string-list/)

有时，在处理数据记录时，我们可能会遇到这样的问题:我们需要执行某些交换操作，其中我们需要在整个字符串列表中用其他元素替换一个元素。这在日常和数据科学领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`replace()` +列表理解**
上述功能的组合可用于执行该任务。在本文中，我们使用列表理解来遍历列表，并使用 replace()来执行交换任务。

```py
# Python3 code to demonstrate 
# Swap elements in String list
# using replace() + list comprehension

# Initializing list
test_list = ['Gfg', 'is', 'best', 'for', 'Geeks']

# printing original lists
print("The original list is : " + str(test_list))

# Swap elements in String list
# using replace() + list comprehension
res = [sub.replace('G', '-').replace('e', 'G').replace('-', 'e') for sub in test_list]

# printing result 
print ("List after performing character swaps : " + str(res))
```

**Output :**

```py
The original list is : ['Gfg', 'is', 'best', 'for', 'Geeks']
List after performing character swaps : ['efg', 'is', 'bGst', 'for', 'eGGks']

```