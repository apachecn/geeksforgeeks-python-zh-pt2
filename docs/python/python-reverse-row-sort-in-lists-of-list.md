# Python–列表中的反向行排序

> 原文:[https://www . geesforgeks . org/python-反向行-列表中排序/](https://www.geeksforgeeks.org/python-reverse-row-sort-in-lists-of-list/)

有时，在处理数据时，我们会遇到一个问题，即我们需要按降序对矩阵的行进行排序。这类问题在网络开发和数据科学领域有其应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环+排序()+反转**
这个问题可以通过使用循环来循环每一行来解决。排序和反向可用于对行执行反向排序。

```
# Python3 code to demonstrate 
# Reverse Row sort in Lists of List
# using loop

# initializing list 
test_list = [[4, 1, 6], [7, 8], [4, 10, 8]]

# printing original list
print ("The original list is : " + str(test_list))

# Reverse Row sort in Lists of List
# using loop
for ele in test_list: 
    ele.sort(reverse = True) 

# printing result 
print ("The reverse sorted Matrix is : " + str(test_list))
```

**Output :**

```
The original list is : [[4, 1, 6], [7, 8], [4, 10, 8]]
The reverse sorted Matrix is : [[6, 4, 1], [8, 7], [10, 8, 4]]

```