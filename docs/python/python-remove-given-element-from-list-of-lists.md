# Python |从列表列表中移除给定元素

> 原文:[https://www . geesforgeks . org/python-从列表列表中移除给定元素/](https://www.geeksforgeeks.org/python-remove-given-element-from-list-of-lists/)

从列表中删除基本元素已经被处理过很多次了，但是有时我们有一个列表，而不是只有一个列表，我们需要在列表中执行这个特定的任务。让人手不足的人来完成这项特殊任务会有所帮助。让我们讨论执行这个特殊任务的某些方法。

**方法一:使用列表理解**

这种方法背后的逻辑是减少代码的大小，并使用循环作为列表理解本身的一种方式来执行任务。

```
# Python3 code to demonstrate
# Removing element from list of lists
# using list comprehension

# initializing list
test_list = [[4, 5, 6], [5, 6, 4, 1], [4], [4, 8, 9, 10]]

# printing original list
print("The original list : " + str(test_list))

# initializing Number to delete
N = 4

# using list comprehension
# Removing element from list of lists
res = [[ele for ele in sub if ele != N] for sub in test_list]

# print result
print("The list after deletion of element : " + str(res))
```

**Output :**

```
The original list : [[4, 5, 6], [5, 6, 4, 1], [4], [4, 8, 9, 10]]
The list after deletion of element : [[5, 6], [5, 6, 1], [], [8, 9, 10]]

```

**方法二:使用列表理解+列表切片**
在这个方法中，我们一般做的任务类似于上面的方法，变化只是我们为了更好的代码可读性使用了列表切片。

```
# Python3 code to demonstrate
# Removing element from list of lists
# using list comprehension + list slicing

# initializing list
test_list = [[4, 5, 6], [5, 6, 4, 1], [4], [4, 8, 9, 10]]

# printing original list
print("The original list : " + str(test_list))

# initializing Number to delete
N = 4

# using list comprehension + list slicing
# Removing element from list of lists
for sub in test_list:
    sub[:] = [ele for ele in sub if ele != N]

# print result
print("The list after deletion of element : " + str(test_list))
```

**Output :**

```
The original list : [[4, 5, 6], [5, 6, 4, 1], [4], [4, 8, 9, 10]]
The list after deletion of element : [[5, 6], [5, 6, 1], [], [8, 9, 10]]

```