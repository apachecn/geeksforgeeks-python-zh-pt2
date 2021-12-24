# Python |选择性指数求和

> 原文:[https://www . geesforgeks . org/python-selective-indexs-summary/](https://www.geeksforgeeks.org/python-selective-indices-summation/)

在 python 中，从元素的索引中访问元素是一项更简单的任务，只需在列表中使用[]运算符就可以了。但是在某些情况下，当我们有不止一个索引时，我们会遇到任务，我们需要获取与这些索引相对应的所有元素，然后执行求和。让我们讨论完成这项任务的某些方法。

**方法#1:使用列表理解+ `sum()`**
这个任务很容易通过循环来执行，因此简写为第一个从这个任务开始的方法。迭代索引列表以从列表中获取相应的元素到新列表中是执行这个任务的强力方法。求和的任务是使用 sum()执行的。

```py
# Python3 code to demonstrate 
# Selective indices Summation
# using list comprehension + sum()

# initializing lists 
test_list = [9, 4, 5, 8, 10, 14] 
index_list = [1, 3, 4] 

# printing original lists 
print ("Original list : " + str(test_list)) 
print ("Original index list : " + str(index_list)) 

# using list comprehension + sum() to 
# Selective indices Summation
res_list = sum([test_list[i] for i in index_list]) 

# printing result 
print ("Resultant list : " + str(res_list)) 
```

**Output :**

```py
Original list : [9, 4, 5, 8, 10, 14]
Original index list : [1, 3, 4]
Resultant list : 22

```