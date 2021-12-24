# Python–从列表中移除后部元素

> 原文:[https://www . geesforgeks . org/python-remove-rear-element-from-list/](https://www.geeksforgeeks.org/python-remove-rear-element-from-list/)

堆栈数据结构是非常众所周知的数据结构，Python 中的列表通常会将元素追加到列表的末尾。为了实现堆栈数据结构，必须能够从列表中移除结束元素。让我们讨论实现这一点的方法，以便可以使用列表轻松实现堆栈数据结构。

**方法#1:使用`pop(-1)`**
此方法弹出，即从列表中移除并打印第 I 个元素。此方法主要用于执行此任务的其他可用选项中。这将更改原始列表。

```py
# Python 3 code to demonstrate 
# Remove rear element
# using pop(-1)

# initializing list 
test_list = [1, 4, 3, 6, 7]

# Printing original list
print ("Original list is : " + str(test_list))

# using pop(-1) to
# Remove rear element
test_list.pop(-1)

# Printing modified list 
print ("Modified list is : " + str(test_list))
```

**Output :**

```py
Original list is : [1, 4, 3, 6, 7]
Modified list is : [1, 4, 3, 6]

```