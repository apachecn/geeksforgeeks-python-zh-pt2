# Python |元组列表中的最小值和最大值

> 原文:[https://www . geesforgeks . org/python-元组列表中的最小值和最大值/](https://www.geeksforgeeks.org/python-min-and-max-value-in-list-of-tuples/)

最小值和最大值的计算在任何编程领域都是非常常见的实用程序，无论是开发领域还是包括任何编程结构的任何其他领域。有时，数据可能以元组的形式出现，并且必须在元组中执行最小和最大操作。让我们讨论处理这种情况的某些方法。

**方法#1:使用`min()`和`max()`**
在这个方法中，我们使用 python 内置的`min` 和`max` 函数来执行获取特定元素位置的最小值和最大值的任务。

```
# Python3 code to demonstrate 
# min and max in list of tuples
# using min() and max()

# initializing list  
test_list = [(2, 3), (4, 7), (8, 11), (3, 6)]

# printing original list
print ("The original list is : " + str(test_list))

# using min() and max()
# to get min and max in list of tuples
res1 = min(test_list)[0], max(test_list)[0]
res2 = min(test_list)[1], max(test_list)[1]

# printing result 
print ("The min and max of index 1 :  " +  str(res1))
print ("The min and max of index 2 :  " +  str(res2))
```

**Output:**

```
The original list is : [(2, 3), (4, 7), (8, 11), (3, 6)]
The min and max of index 1 :  (2, 8)
The min and max of index 2 :  (3, 11)

```

**方法 2:使用`map() + zip()`**
这是执行这一特定任务的更优雅的方式。在本任务中，我们使用`map`函数将元素链接到`zip` 函数，这些函数累积起来执行最小函数或最大函数的功能。

```
# Python3 code to demonstrate 
# min and max in list of tuples
# using map() + zip()

# initializing list  
test_list = [(2, 3), (4, 7), (8, 11), (3, 6)]

# printing original list
print ("The original list is : " + str(test_list))

# using map() + zip()
# to get min and max in list of tuples
res1 = list(map(max, zip(*test_list)))
res2 = list(map(min, zip(*test_list)))

# printing result 
print ("The indices wise maximum number : " +  str(res1))
print ("The indices wise minimum number : " +  str(res2))
```

**Output:**

```
The original list is : [(2, 3), (4, 7), (8, 11), (3, 6)]
The indices wise maximum number : [8, 11]
The indices wise minimum number : [2, 3]

```