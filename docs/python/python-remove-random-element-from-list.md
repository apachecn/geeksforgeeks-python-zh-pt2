# Python |从列表中移除随机元素

> 原文:[https://www . geesforgeks . org/python-remove-random-element-from-list/](https://www.geeksforgeeks.org/python-remove-random-element-from-list/)

有时，在使用 Python 列表时，我们可能会遇到问题或部分问题，其中我们希望在删除一些随机元素后转换列表。这可以在游戏领域或个人项目中得到应用。让我们讨论一下完成这项任务的具体方法。

**方法:使用`randrange() + pop()`**
在这种情况下，我们只需将上述功能组合成一个，就可以完成这个任务。随机元素由`randrange()`选择，然后使用`pop()`访问并从列表中删除

```py
# Python3 code to demonstrate working of
# Remove random element from list
# Using randrange() + pop()
import random

# initializing list 
test_list = [6, 4, 8, 9, 10]

# printing list 
print("The original list : " + str(test_list))

# Remove random element from list
# Using randrange() + pop()
test_list.pop(random.randrange(len(test_list)))

# Printing result
print("List after removal of random number : " + str(test_list))
```

**Output :**

```py

The original list : [6, 4, 8, 9, 10]
List after removal of random number : [6, 4, 8, 10]

```