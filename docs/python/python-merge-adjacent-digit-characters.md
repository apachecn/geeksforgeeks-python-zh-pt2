# Python |合并相邻数字字符

> 原文:[https://www . geesforgeks . org/python-merge-相邻数字-字符/](https://www.geeksforgeeks.org/python-merge-adjacent-digit-characters/)

有时，python 列表中可能会出现多种类型的数据，有时这些数据会被不希望地标记化，因此我们需要将标记化的数字连接起来，并保持字母原样。让我们讨论一下完成这项任务的某些方法。

**方法#1:使用列表理解+ `"*" operator`**
这个任务可以使用列表理解来执行，首先连接数字，然后连接单词，然后只分离单词，同时连接形成结果字符串。

```py
# Python3 code to demonstrate
# Merge adjacent Digit characters
# list comprehension + "*" operator

# initializing list 
test_list = ['Geeks', 'for', 'Geeks', '2', '5']

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + "*" operator
# Merge adjacent Digit characters
res = [''.join([i for i in test_list if not i.isalpha()]), *[j for j in test_list if j.isalpha()]]

# print result
print("The joined adjacent word list(ignoring alphabets) : " + str(res))
```

**Output :**

```py
The original list : ['Geeks', 'for', 'Geeks', '2', '5']
The joined adjacent word list(ignoring alphabets) : ['25', 'Geeks', 'for', 'Geeks']

```