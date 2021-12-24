# Python–元素移除后的求和

> 原文:[https://www . geeksforgeeks . org/python-元素后求和-移除/](https://www.geeksforgeeks.org/python-summation-after-elements-removal/)

有时我们需要执行从存在于其他列表中的列表中移除所有项目的操作，也就是说，我们在一个列表中被赋予了一些无效的数字，这些数字需要从原始列表中移除并执行其求和。让我们讨论可以执行此操作的各种方法。

**方法#1:使用列表理解+ sum()**
列表理解可用于执行仅一行中的简单方法，因此给出了执行该特定任务的简单方法。执行求和的任务是使用 sum()完成的。

```
# Python 3 code to demonstrate 
# Summation after elements removal
# using list comprehension + sum()

# initializing list 
test_list = [1, 3, 4, 6, 7, 6]

# initializing remove list 
remove_list = [3, 6]

# printing original list 
print ("The original list is : " + str(test_list))

# printing remove list 
print ("The remove list is : " + str(remove_list))

# using list comprehension + sum() to perform task
res = sum([i for i in test_list if i not in remove_list])

# printing result
print ("The list after performing removal summation is : " + str(res))
```

**Output :**

```
The original list is : [1, 3, 4, 6, 7, 6]
The remove list is : [3, 6]
The list after performing removal summation is : 12

```