# Python |用列表修改元组内容

> 原文:[https://www . geesforgeks . org/python-modification-tuple-contents-with-list/](https://www.geeksforgeeks.org/python-modifying-tuple-contents-with-list/)

在 Python 中，元组是不可变的，因此一旦元组形成，就不需要对其进行任何更改。这种限制使得它们的处理更加困难，因此对元组的某些操作非常有用。本文讨论用给定的列表修改第二个元组元素。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`zip()` +列表理解**
在该方法中，我们只需取元组列表的第一个元素和对应索引处的元素，并使用 zip 函数将它们压缩在一起。

```
# Python3 code to demonstrate
# modifying tuple elements
# using zip() + list comprehension

# initializing lists
test_list1 = [('Geeks', 1), ('for', 2), ('Geeks', 3)]
test_list2 = [4, 5, 6]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# using zip() + list comprehension
# modifying tuple elements
res = [(i[0], j) for i, j in zip(test_list1, test_list2)]

# print result
print("The modified resultant list of tuple : " + str(res))
```

**Output :**

```
The original list 1 : [('Geeks', 1), ('for', 2), ('Geeks', 3)]
The original list 2 : [4, 5, 6]
The modified resultant list of tuple : [('Geeks', 4), ('for', 5), ('Geeks', 6)]

```