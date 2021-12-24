# Python–从元组记录列表中提取后置元素

> 原文:[https://www . geesforgeks . org/python-后元素-从元组列表中提取-记录/](https://www.geeksforgeeks.org/python-rear-element-extraction-from-list-of-tuples-records/)

在使用元组时，我们将不同的数据存储为不同的元组元素。有时，需要打印元组中的特定信息，如后方索引。例如，一段代码想要打印所有学生数据的名字。让我们讨论一下如何解决这个问题。

**方法一:使用列表理解**
列表理解是解决这个问题最简单的方法。我们可以只迭代所有索引中的后索引值，并将其存储在列表中，然后打印出来。

```py
# Python3 code to demonstrate 
# Rear element extraction from Records
# using list comprehension 

# initializing list of tuples
test_list = [(1, 'Rash', 21), (2, 'Varsha', 20), (3, 'Kil', 19)]

# printing original list 
print ("The original list is : " + str(test_list))

# using list comprehension to get names
# Rear element extraction from Records
res = [lis[-1] for lis in test_list]

# printing result
print ("List with only rear tuple element : " + str(res))
```

**Output :**

```py
The original list is : [(1, 'Rash', 21), (2, 'Varsha', 20), (3, 'Kil', 19)]
List with only rear tuple element : [21, 20, 19]

```