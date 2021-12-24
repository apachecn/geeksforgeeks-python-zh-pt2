# Python |旋转列表的方法

> 原文:[https://www.geeksforgeeks.org/python-ways-to-rotate-a-list/](https://www.geeksforgeeks.org/python-ways-to-rotate-a-list/)

列表的循环也在前面讨论过，但是这篇特别的文章集中在短手和各种短技巧上，以一行或一个词来实现。在程序员的生活中，这个操作对于完成各种任务是非常必要的。

让我们讨论轮换列表的不同方法。

**方法#1:使用切片**
这种特殊的方法是通用方法，主要用于完成这一任务，在许多文章中也有讨论。它的工作原理是，在给定旋转数的情况下，只需将后来切片的零件与最初切片的零件连接起来。

```py
# Python3 code to demonstrate 
# rotation of list 
# using slice 

# initializing list
test_list = [1, 4, 6, 7, 2]

# printing original list 
print ("Original list : " + str(test_list))

# using slicing to left rotate by 3
test_list = test_list[3:] + test_list[:3]

# Printing list after left rotate
print ("List after left rotate by 3 : " + str(test_list))

# using slicing to right rotate by 3
# back to Original
test_list = test_list[-3:] + test_list[:-3]

# Printing after right rotate
print ("List after right rotate by 3(back to original) : "
                                         + str(test_list))
```

**Output:**

```py
Original list : [1, 4, 6, 7, 2]
List after left rotate by 3 : [7, 2, 1, 4, 6]
List after right rotate by 3 ( back to original) : [1, 4, 6, 7, 2]

```

**方法#2:使用列表理解**
这个问题也可以用朴素的方法解决，但是它更短的实现需要借助列表理解。在这种方法中，我们只需在旋转后将每个值的索引重新分配到特定位置。

```py
# Python3 code to demonstrate 
# rotation of list 
# using list comprehension

# initializing list
test_list = [1, 4, 6, 7, 2]

# printing original list 
print ("Original list : " + str(test_list))

# using list comprehension to left rotate by 3
test_list = [test_list[(i + 3) % len(test_list)]
               for i, x in enumerate(test_list)]

# Printing list after left rotate
print ("List after left rotate by 3 : " + str(test_list))

# using list comprehension to right rotate by 3
# back to Original
test_list = [test_list[(i - 3) % len(test_list)]
               for i, x in enumerate(test_list)]

# Printing after right rotate
print ("List after right rotate by 3(back to original) : " 
                                        + str(test_list))
```

**Output:**

```py
Original list : [1, 4, 6, 7, 2]
List after left rotate by 3 : [7, 2, 1, 4, 6]
List after right rotate by 3(back to original) : [1, 4, 6, 7, 2]

```

**方法 3:使用`collections.deque.rotate()`**
集合模块有一个提供`rotate()`的 deque 类，它是允许旋转的内置函数。这是一个不太为人所知的功能，但有更大的效用。

```py
# Python3 code to demonstrate 
# rotation of list 
# using rotate()
from collections import deque

# initializing list
test_list = [1, 4, 6, 7, 2]

# printing original list 
print ("Original list : " + str(test_list))

# using rotate() to left rotate by 3
test_list = deque(test_list)
test_list.rotate(-3)
test_list = list(test_list)

# Printing list after left rotate
print ("List after left rotate by 3 : " + str(test_list))

# using rotate() to right rotate by 3
# back to Original
test_list = deque(test_list)
test_list.rotate(3)
test_list = list(test_list)

# Printing after right rotate
print ("List after right rotate by 3(back to original) : "
                                        + str(test_list))
```

**Output:**

```py
Original list : [1, 4, 6, 7, 2]
List after left rotate by 3 : [7, 2, 1, 4, 6]
List after right rotate by 3(back to original) : [1, 4, 6, 7, 2]

```