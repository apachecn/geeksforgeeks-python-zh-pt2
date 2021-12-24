# Python |将列表中最后一个元素移到第一个位置

> 原文:[https://www . geesforgeks . org/python-shift-最后一个元素到列表中第一个位置/](https://www.geeksforgeeks.org/python-shift-last-element-to-first-position-in-list/)

循环旋转在前面的文章中已经讨论过了。但有时，我们只需要一个特定的任务，一部分轮换，即把列表中的最后一个元素移到第一个元素。这在某些实用程序的日常编程中有应用。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表切片和“`+`”运算符**
这些功能的组合可以用来执行列表中单个班次的任务。最后一个元素被添加到列表的其余部分，以使用切片来实现这个任务。

```
# Python3 code to demonstrate
# shift last element to first 
# using list slicing and "+" operator

# initializing list 
test_list = [1, 4, 5, 6, 7, 8, 9, 12]

# printing the original list
print ("The original list is : " + str(test_list))

# using list slicing and "+" operator
# shift last element to first
test_list = test_list[-1:] + test_list[:-1] 

# printing result
print ("The list after shift is : " + str(test_list))
```

**Output:**

```
The original list is : [1, 4, 5, 6, 7, 8, 9, 12]
The list after shift is : [12, 1, 4, 5, 6, 7, 8, 9]

```