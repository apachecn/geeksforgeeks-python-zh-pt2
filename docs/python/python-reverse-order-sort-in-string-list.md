# Python |字符串列表中的逆序排序

> 原文:[https://www . geesforgeks . org/python-逆序-字符串列表排序/](https://www.geeksforgeeks.org/python-reverse-order-sort-in-string-list/)

有时，在使用 Python 时，我们会遇到一个问题，即我们需要对列表中存在的所有字符串执行反向排序操作。这个问题可能发生在一般编程和 web 开发中。让我们讨论一下解决这个问题的某些方法。

**方法一:使用列表理解+ `sorted() + join() + reverse`**
这是解决这个问题的一种方法。在本文中，我们使用 sorted()功能来执行排序操作，并使用 join()来重建字符串列表。通过将“reverse”作为 True 参数传递给 sorted()来实现反向逻辑。

```
# Python3 code to demonstrate working of 
# Reverse Order Sort in String List
# using list comprehension + sorted() + join() + reverse

# initialize list 
test_list = ['gfg', 'is', 'good'] 

# printing original list 
print("The original list : " + str(test_list)) 

# Reverse Order Sort in String List
# using list comprehension + sorted() + join() + reverse
res = [''.join(sorted(ele, reverse = True)) for ele in test_list] 

# printing result 
print("List after string reverse sorting : " + str(res)) 
```

**Output :**

```
The original list : ['gfg', 'is', 'good']
List after string reverse sorting : ['ggf', 'si', 'oogd']

```