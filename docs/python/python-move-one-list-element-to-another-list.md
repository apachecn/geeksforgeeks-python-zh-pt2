# Python |将一个列表元素移动到另一个列表

> 原文:[https://www . geesforgeks . org/python-move-one-list-element-to-other-list/](https://www.geeksforgeeks.org/python-move-one-list-element-to-another-list/)

有时，在使用 Python 列表时，可能会出现一个问题，即我们需要执行元素的列表间转换。解决这个问题总是非常有用的。让我们讨论一下执行这项任务的具体方法。

**方法:使用`pop() + insert() + index()`**
可以使用上述功能的组合来执行该特定任务。在这里我们只是使用`pop` 函数的属性来返回和移除元素，并使用`index`函数将其插入到其他列表的特定位置。

```
# Python3 code to demonstrate working of
# Move one list element to another list
# Using pop() + index() + insert()

# initializing lists
test_list1 = [4, 5, 6, 7, 3, 8]
test_list2 = [7, 6, 3, 8, 10, 12]

# printing original lists
print("The original list 1 is : " +  str(test_list1))
print("The original list 2 is : " +  str(test_list2))

# Using pop() + index() + insert()
# Move one list element to another list
res = test_list1.insert(4, test_list2.pop(test_list2.index(10)))

# Printing result
print("The list 1 after insert is : " +  str(test_list1))
print("The list 2 after remove is : " +  str(test_list2))
```

**Output :**

```
The original list 1 is : [4, 5, 6, 7, 3, 8]
The original list 2 is : [7, 6, 3, 8, 10, 12]
The list 1 after insert is : [4, 5, 6, 7, 10, 3, 8]
The list 2 after remove is : [7, 6, 3, 8, 12]

```