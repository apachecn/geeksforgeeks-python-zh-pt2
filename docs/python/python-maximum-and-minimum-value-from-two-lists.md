# Python |两个列表中的最大值和最小值

> 原文:[https://www . geesforgeks . org/python-两个列表中的最大值和最小值/](https://www.geeksforgeeks.org/python-maximum-and-minimum-value-from-two-lists/)

在列表中找到最大值和最小值是很常见的问题。但是有时这个问题可以扩展为两个列表，因此变成了一个修正的问题。本文讨论了容易执行这项任务的人手不足问题。让我们讨论一下解决这个问题的某些方法。

**方法一:使用 max()+min()+“`+`”运算符**
最大值和最小值可以通过 python 常规的 max 和 min 函数来确定，一个到两个列表的扩展可以使用“`+`”运算符来处理。

```
# Python3 code to demonstrate
# maximum and minimum values in two lists 
# using max() + min() + "+" operator

# initializing lists
test_list1 = [1, 3, 4, 5, 2, 6]
test_list2 = [3, 4, 8, 3, 10, 1]

# printing the original lists
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " + str(test_list2))

# using max() + min() + "+" operator
# maximum and minimum values in two lists 
max_all = max(test_list1 + test_list2)
min_all = min(test_list1 + test_list2)

# printing result
print ("The maximum of both lists is : " + str(max_all))
print ("The minimum of both lists is : " + str(min_all))
```

**Output:**

```
The original list 1 is : [1, 3, 4, 5, 2, 6]
The original list 2 is : [3, 4, 8, 3, 10, 1]
The maximum of both lists is : 10
The minimum of both lists is : 1

```

**方法#2:使用`max() + min() + chain()`**
另一种执行特定任务的方法是使用链函数，该函数执行类似于“+”运算符的任务，但使用迭代器，因此速度更快。

```
# Python3 code to demonstrate
# maximum and minimum values in two lists 
# using max() + min() + "+" operator
from itertools import chain

# initializing lists
test_list1 = [1, 3, 4, 5, 2, 6]
test_list2 = [3, 4, 8, 3, 10, 1]

# printing the original lists
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " + str(test_list2))

# using max() + min() + "+" operator
# maximum and minimum values in two lists 
max_all = max(chain(test_list1, test_list2))
min_all = min(chain(test_list1, test_list2))

# printing result
print ("The maximum of both lists is : " + str(max_all))
print ("The minimum of both lists is : " + str(min_all))
```

**Output:**

```
The original list 1 is : [1, 3, 4, 5, 2, 6]
The original list 2 is : [3, 4, 8, 3, 10, 1]
The maximum of both lists is : 10
The minimum of both lists is : 1

```