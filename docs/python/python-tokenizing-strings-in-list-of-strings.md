# Python |字符串列表中的标记化字符串

> 原文:[https://www . geesforgeks . org/python-字符串列表中的字符串标记化/](https://www.geeksforgeeks.org/python-tokenizing-strings-in-list-of-strings/)

有时，在处理数据时，我们需要对字符串进行字符串标记化，这可能会作为字符串列表的输入。这在机器学习的许多应用中有一个用例。让我们讨论一下实现这一点的某些方法。

**方法一:使用列表理解+ `split()`**

我们可以通过使用列表理解来遍历字符串列表中的每个字符串来实现这个特殊的任务，而 split 函数执行标记化的任务。

```py
# Python3 code to demonstrate
# Tokenizing strings in list of strings
# using list comprehension + split()

# initializing list
test_list = ['Geeks for Geeks', 'is', 'best computer science portal']

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + split()
# Tokenizing strings in list of strings
res = [sub.split() for sub in test_list]

# print result
print("The list after split of strings is : " + str(res))
```

**Output :**

> 原列表:['Geeks for Geeks '，' is '，' best computer science portal']
> 字符串拆分后的列表为:[['Geeks '，' for '，' Geeks']，['is']，['best '，' computer '，' science '，' portal']]

**方法 2:使用`map() + split()`**
这是另一种可以解决这个特殊任务的方法。在这个方法中，我们只是执行与上面类似的任务，只是我们使用 map 函数将拆分逻辑绑定到整个列表。

```py
# Python3 code to demonstrate
# Tokenizing strings in list of strings
# using map() + split()

# initializing list
test_list = ['Geeks for Geeks', 'is', 'best computer science portal']

# printing original list
print("The original list : " + str(test_list))

# using map() + split()
# Tokenizing strings in list of strings
res = list(map(str.split, test_list))

# print result
print("The list after split of strings is : " + str(res))
```

**Output :**

> 原列表:['Geeks for Geeks '，' is '，' best computer science portal']
> 字符串拆分后的列表为:['Geeks '，' for '，' Geeks']，['is']，['best '，' computer '，' science '，' portal']]