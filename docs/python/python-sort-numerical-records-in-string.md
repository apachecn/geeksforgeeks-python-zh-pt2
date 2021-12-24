# Python |对字符串中的数字记录进行排序

> 原文:[https://www . geesforgeks . org/python-sort-numeric-records-in-string/](https://www.geeksforgeeks.org/python-sort-numerical-records-in-string/)

有时，在处理 Python 记录时，我们会遇到一个问题，即它们可能以字符串的名称和数字格式出现。这些可能需要分类。这个问题可能发生在许多涉及数据的领域。让我们讨论执行这项任务的某些方法。

**方法一:使用`join() + split() + sorted()` +列表理解**
以上功能的组合可以用来执行此任务。在本文中，我们使用 sorted()执行排序任务，使用 split()执行提取数字的任务。我们使用 join()执行重新连接已排序字符串的任务。

```py
# Python3 code to demonstrate working of 
# Sort Numerical Records in String
# Using join() + split() + sorted() + list comprehension

# initializing string
test_str = "Akshat 15 Nikhil 20 Akash 10"

# printing original string
print("The original string is : " + test_str)

# Sort Numerical Records in String
# Using join() + split() + sorted() + list comprehension
temp1 = test_str.split()
temp2 = [temp1[idx : idx + 2] for idx in range(0, len(temp1), 2)]
temp3 = sorted(temp2, key = lambda ele: (int(ele[1]), ele[0]))
res = ' '.join([' '.join(ele) for ele in temp3])

# printing result 
print("The string after sorting records : " + res) 
```

**Output :**

```py
The original string is : Akshat 15 Nikhil 20 Akash 10
The string after sorting records : Akash 10 Akshat 15 Nikhil 20

```