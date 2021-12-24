# Python |从列表中删除给定元素

> 原文:[https://www . geesforgeks . org/python-从列表中移除给定元素/](https://www.geeksforgeeks.org/python-remove-given-element-from-the-list/)

给定一个列表，编写一个 Python 程序从给定的列表中移除给定的元素(列表可能有重复)。在 Python 中，我们有多种方法可以完成这项任务。让我们来看看完成这项任务的一些 Pythonic 方法。

**方法#1:** 使用`pop()`方法【移除首先找到的给定元素。】

```py
# Python program to remove given element from the list
list1 = [1, 9, 8, 4, 9, 2, 9] 

# Printing initial list 
print ("original list : "+ str(list1)) 

remove = 9

# using pop() 
# to remove list element 9
if remove in list1: 
    list1.pop(list1.index(remove)) 

# Printing list after removal 
print ("List after element removal is : "  + str(list1)) 
```

**输出:**

```py
original list : [1, 9, 8, 4, 9, 2, 9]
List after element removal is : [1, 8, 4, 9, 2, 9]

```