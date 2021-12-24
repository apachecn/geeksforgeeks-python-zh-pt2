# Python 程序将元素插入排序列表

> 原文:[https://www . geesforgeks . org/python-program-to-insert-a-element-to-sorted-list/](https://www.geeksforgeeks.org/python-program-to-insert-an-element-into-sorted-list/)

给定一个排序列表和一个元素，编写一个 Python 程序，将元素插入给定列表的排序位置。

**示例:**

```py
Input : list = [1, 2, 4], n = 3
Output : list = [1, 2, 3, 4]

Input : list = ['a', 'b', 'c', 'd'], n = 'e'
Output : list = ['a', 'b', 'c', 'd', 'e']

```

**方法#1 :**
这种方法就是蛮力法。由于列表已经排序，我们从循环开始，检查列表元素是否大于给定元素。如果是，需要在这个位置插入给定的元素。

```py
# Python3 program to insert
# an element into sorted list

# Function to insert element

def insert(list, n):

    index = len(list)
    # Searching for the position
    for i in range(len(list)):
      if list[i] > n:
        index = i
        break

    # Inserting n in the list
    if index == len(list):
      list = list[:index] + [n]
    else:
      list = list[:index] + [n] + list[index:]
    return list

# Driver function
list = [1, 2, 4]
n = 3

print(insert(list, n))
```

**Output:**

```py
[1, 2, 3, 4]

```

**方法#2 :**
Python 附带了一个 *[等分模块](https://www.geeksforgeeks.org/bisect-algorithm-functions-in-python/)* ，其目的是在列表中找到需要插入元素的位置，以保持列表有序。因此，我们使用这个模块来解决给定的问题。

```py
# Python3 program to insert 
# an element into sorted list
import bisect 

def insert(list, n):
    bisect.insort(list, n) 
    return list

# Driver function
list = [1, 2, 4]
n = 3

print(insert(list, n))
```

**Output:**

```py
[1, 2, 3, 4]

```