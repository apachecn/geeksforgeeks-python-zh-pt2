# Python |从元组列表中移除特定元素

> 原文:[https://www . geesforgeks . org/python-从元组列表中移除特定元素/](https://www.geeksforgeeks.org/python-remove-particular-element-from-tuple-list/)

自从 Python 在数据分析中流行以来，我们在许多问题中都有元组列表作为容器。有时，在数据预处理时，我们可能会遇到一个问题，即我们需要从元组列表中完全移除一个特定的元素。让我们讨论一下执行这项任务的方法。

**方法:使用列表理解**
这个任务可以使用使用循环的蛮力方式来使用，但是更好的替代速记是可以在一行中执行这个任务的方法。列表理解可以帮助我们实现它，因此建议使用这种方法来完成这项任务。这只是检查元素，并删除如果它是选定的元素。

```
# Python3 code to demonstrate working of
# Remove particular element from tuple list
# using list comprehension

# initialize list
test_list = [(5, 6, 7), (7, 2, 4, 6), (6, 6, 7), (6, 10, 8)]

# printing original list
print("The original list is : " + str(test_list))

# declaring remove element
N = 6

# Remove particular element from tuple list
# using list comprehension
res = [tuple(ele for ele in sub if ele != N) for sub in test_list]

# printing result
print("The Tuple List after removal of element : " + str(res))
```

**Output :**

```
The original list is : [(5, 6, 7), (7, 2, 4, 6), (6, 6, 7), (6, 10, 8)]
The Tuple List after removal of element : [(5, 7), (7, 2, 4), (7, ), (10, 8)]

```