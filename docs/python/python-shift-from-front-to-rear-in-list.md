# Python |列表中从前向后移动

> 原文:[https://www . geeksforgeeks . org/python-从列表中的前移到列表中的后/](https://www.geeksforgeeks.org/python-shift-from-front-to-rear-in-list/)

循环旋转在前面的文章中已经讨论过了。但有时，我们只需要一个特定的任务，一部分轮换，即把列表中的第一个元素移到最后一个元素。这在某些实用程序的日常编程中有应用。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表切片和`“+” operator`**
这些功能的组合可以用来执行列表中单班的任务。第一个元素被添加到列表的其余部分，以使用切片来实现这个任务。

```py
# Python3 code to demonstrate
# Shift from Front to Rear in List
# using list slicing and "+" operator

# initializing list 
test_list = [1, 4, 5, 6, 7, 8, 9, 12]

# printing the original list
print ("The original list is : " + str(test_list))

# using list slicing and "+" operator
# Shift from Front to Rear in List
test_list = test_list[1 :] + test_list[: 1] 

# printing result
print ("The list after shift is : " + str(test_list))
```

**Output :**

```py
The original list is : [1, 4, 5, 6, 7, 8, 9, 12]
The list after shift is : [4, 5, 6, 7, 8, 9, 12, 1]

```