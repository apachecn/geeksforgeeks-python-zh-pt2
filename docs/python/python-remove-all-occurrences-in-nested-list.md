# Python |移除嵌套列表中的所有事件

> 原文:[https://www . geesforgeks . org/python-移除嵌套列表中的所有事件/](https://www.geeksforgeeks.org/python-remove-all-occurrences-in-nested-list/)

移除元素的任务通常不会带来任何挑战，但有时，我们可能会遇到比仅移除单个元素或仅在普通列表中执行移除更复杂的问题。问题可能是删除所有嵌套列表。让我们讨论一下解决这个问题的某些方法。

**方法一:使用列表理解**

列表理解可以作为推荐的较长方法的较短方法，以正常的循环方式来执行这个任务，在这个任务中，我们只检查匹配并重建没有目标列表元素的列表。

```py
# Python3 code to demonstrate
# Remove all occurrences in nested list
# using list comprehension

# initializing list
test_list = [[4, 5], [1, 2, 3], [4, 5], [8, 9], [10, 11]]

# initializing list to delete
del_list = [4, 5]

# printing original list
print("The original list : " + str(test_list))

# printing delete list 
print("The list to be deleted is : " + str(del_list))

# using list comprehension
# Remove all occurrences in nested list
res = [i for i in test_list if i != del_list]

# print result
print("The list after removal of list element : " + str(res))
```

**Output :**

```py
The original list : [[4, 5], [1, 2, 3], [4, 5], [8, 9], [10, 11]]
The list to be deleted is : [4, 5]
The list after removal of list element : [[1, 2, 3], [8, 9], [10, 11]]

```

**方法 2:使用`filter() + partial() + operator.ne`**

也可以使用上述功能来执行任务。过滤函数执行过滤，并通过部分函数返回部分列表，并使用`operator.ne`方法施加不相等的条件。

```py
# Python3 code to demonstrate
# Remove all occurrences in nested list
# using filter() + partial() + operator.ne
from functools import partial
from operator import ne

# initializing list
test_list = [[4, 5], [1, 2, 3], [4, 5], [8, 9], [10, 11]]

# initializing list to delete
del_list = [4, 5]

# printing original list
print("The original list : " + str(test_list))

# printing delete list 
print("The list to be deleted is : " + str(del_list))

# using filter() + partial() + operator.ne
# Remove all occurrences in nested list
res = list(filter(partial(ne, del_list), test_list))

# print result
print("The list after removal of list element : " + str(res))
```

**Output :**

```py
The original list : [[4, 5], [1, 2, 3], [4, 5], [8, 9], [10, 11]]
The list to be deleted is : [4, 5]
The list after removal of list element : [[1, 2, 3], [8, 9], [10, 11]]

```