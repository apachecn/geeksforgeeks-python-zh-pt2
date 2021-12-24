# Python |三重列表求和

> 原文:[https://www.geeksforgeeks.org/python-triple-list-summation/](https://www.geeksforgeeks.org/python-triple-list-summation/)

应用程序可能要求将 2-3 个列表的元素添加到一个列表中并执行求和。这种应用有可能进入机器学习领域，有时也可能进入网络开发领域。让我们讨论一下执行这项特殊任务的某些方法。

**方法#1:使用+运算符+ `sum()`**
这可以很容易地使用+运算符来完成，因为它在列表的后面进行元素添加。类似的逻辑在多个列表的情况下被扩展。求和使用 sum()执行。

```
# Python3 code to demonstrate 
# Triple List Summation
# using + operator + sum()

# initializing lists
test_list1 = [1, 3, 5, 5, 4]
test_list2 = [4, 6, 2, 8, 10]
test_list3 = [7, 5, 2, 9, 11]

# printing original lists
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " + str(test_list2))
print ("The original list 3 is : " + str(test_list3))

# using + operator + sum()
# Triple List Summation
test_list1 = sum(test_list1 + test_list2 + test_list3)

# printing result 
print ("The summed and modified list is : " + str(test_list1))
```

**Output :**

```
The original list 1 is : [1, 3, 5, 5, 4]
The original list 2 is : [4, 6, 2, 8, 10]
The original list 3 is : [7, 5, 2, 9, 11]
The summed and modified list is : 82

```