# Python |以相同顺序洗牌两个列表

> 原文:[https://www . geeksforgeeks . org/python-shuffle-同顺序两个列表/](https://www.geeksforgeeks.org/python-shuffle-two-lists-with-same-order/)

有时，在使用 Python 列表时，我们会遇到一个问题，即需要在列表中执行洗牌操作。这项任务很简单，Python 中有一些简单的功能可以完成这项任务。但是有时，我们需要对两个列表进行洗牌，以便它们的洗牌顺序一致。让我们讨论一下执行这项任务的方法。

**方法:使用`zip() + shuffle()` + `*`运算符**
在该方法中，该任务分三步执行。首先，使用`zip()`将列表压缩在一起。下一步是使用内置的`shuffle()`执行无序播放，最后一步是使用*运算符将列表解压缩为单独的列表。

```py
# Python3 code to demonstrate working of
# Shuffle two lists with same order
# Using zip() + * operator + shuffle()
import random

# initializing lists
test_list1 = [6, 4, 8, 9, 10]
test_list2 = [1, 2, 3, 4, 5]

# printing lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# Shuffle two lists with same order
# Using zip() + * operator + shuffle()
temp = list(zip(test_list1, test_list2))
random.shuffle(temp)
res1, res2 = zip(*temp)

# Printing result
print("List 1 after shuffle : " + str(list(res1)))
print("List 2 after shuffle : " + str(list(res2)))
```

**Output :**

```py

The original list 1 : [6, 4, 8, 9, 10]
The original list 2 : [1, 2, 3, 4, 5]
List 1 after shuffle : [6, 10, 4, 8, 9]
List 2 after shuffle : [1, 5, 2, 3, 4]

```