# Python |分离键的值

> 原文:[https://www . geesforgeks . org/python-隔离-键-值/](https://www.geeksforgeeks.org/python-segregating-keys-values/)

很多时候，我们需要分离字典关键字的值，以防我们有一个字典列表，需要分离不同关键字的值。这是网络开发中非常有用的工具。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+ `tuple()`**
列表理解可以与元组函数耦合，并可用于执行该特定任务。列表理解执行分离任务，并使用元组函数将它们放入单独的元组中。

```
# Python3 code to demonstrate 
# segragation of keys and values
# using list comprehension + tuple()

# initializing list of dictionaries
test_list = [{'Nikhil' : 1, 'Akash' : 2},
             {'Nikhil' : 3, 'Akash' : 4}]

# printing original list 
print("The original list : " +  str(test_list))

# using list comprehension + tuple()
# to segregate keys and values
res = [tuple(i["Nikhil"] for i in test_list), tuple(i["Akash"]
                                          for i in test_list)]

# printing result 
print("The segregated keys and values : " + str(res))
```

**Output :**

```
The original list : [{'Akash': 2, 'Nikhil': 1}, {'Akash': 4, 'Nikhil': 3}]
The segregated keys and values : [(1, 3), (2, 4)]

```