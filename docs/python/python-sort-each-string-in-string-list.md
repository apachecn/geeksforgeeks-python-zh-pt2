# Python |对字符串列表中的每个字符串进行排序

> 原文:[https://www . geesforgeks . org/python-sort-每个字符串中的字符串列表/](https://www.geeksforgeeks.org/python-sort-each-string-in-string-list/)

有时，在使用 Python 时，我们会遇到一个问题，即我们需要对列表中存在的所有字符串执行排序操作。这个问题可能发生在一般编程和 web 开发中。让我们讨论一下解决这个问题的某些方法。

**方法一:使用列表理解+ `sorted() + join()`**
这是解决这个问题的一种方法。在本文中，我们使用 sorted()功能来执行排序操作，并使用 join()来重建字符串列表。

```
# Python3 code to demonstrate working of
# Sort Strings in String list
# using list comprehension + sorted() + join()

# initialize list 
test_list = ['gfg', 'is', 'good']

# printing original list 
print("The original list : " + str(test_list))

# Sort Strings in String list
# using list comprehension + sorted() + join()
res = [''.join(sorted(ele)) for ele in test_list]

# printing result
print("List after string sorting : " + str(res))
```

**Output :**

```
The original list : ['gfg', 'is', 'good']
List after string sorting : ['fgg', 'is', 'dgoo']

```