# Python–双元素记录列表中的求和

> 原文:[https://www . geesforgeks . org/python-双元素求和-记录-列表/](https://www.geeksforgeeks.org/python-summation-in-dual-element-records-list/)

有时，在使用记录列表时，我们可能会遇到这样的问题，即我们执行二元组记录的求和并将其存储在列表中。这种应用可以发生在不同的领域。让我们讨论执行这项任务的某些方法。

**方法一:利用列表理解**
这是解决这个问题的方法之一。在这种情况下，我们对列表中的二元组进行求和，并在理解的列表中进行迭代。

```py
# Python3 code to demonstrate 
# Summation in Dual element Records List
# using list comprehension

# Initializing list
test_list = [(6, 7), (2, 4), (8, 9), (6, 2)]

# printing original lists
print("The original list is : " + str(test_list))

# Summation in Dual element Records List
# using list comprehension
res = [ele[0] + ele[1] for ele in test_list]

# printing result 
print ("Summation pairs in tuple list : " + str(res))
```

**Output :**

```py
The original list is : [(6, 7), (2, 4), (8, 9), (6, 2)]
Summation pairs in tuple list : [13, 6, 17, 8]

```