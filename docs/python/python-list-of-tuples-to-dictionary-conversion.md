# Python |元组列表到字典的转换

> 原文:[https://www . geesforgeks . org/python-元组列表到字典的转换/](https://www.geeksforgeeks.org/python-list-of-tuples-to-dictionary-conversion/)

用 Python 编码时总是需要相互转换，这也是因为 Python 作为数据科学领域的主要语言的扩展。本文讨论了另一个问题，即转换为字典，将键作为元组的第一个元素，将 rest 作为它的值。

让我们讨论一下实现这一点的某些方法。

**方法一:利用词典理解**

这个问题可以通过使用字典理解的速记来解决，这种速记在字典中执行单行循环的经典朴素方法。

```
# Python3 code to demonstrate
# List of tuple to dictionary conversion
# using list comprehension

# initializing list
test_list = [('Nikhil', 21, 'JIIT'), ('Akash', 22, 'JIIT'), ('Akshat', 22, 'JIIT')]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension
# List of tuple to dictionary conversion
res = {sub[0]: sub[1:] for sub in test_list}

# print result
print("The dictionary after conversion : " + str(res))
```

**Output :**

> 原列表:[(“Nikhil”，21，“JIIT”)，(“Akash”，22，“JIIT”)，(“Akshat”，22，“JIIT”)]
> 转换后的字典:{“Nikhil”:(21，“JIIT”)，“Akshat”:(22，“JIIT”)，“Akash”:(22，“JIIT”)}

**方法二:使用`dict()` +词典理解**

执行类似于上述方法的任务，只是不同之处在于创建字典的方式。在上面的方法中，使用理解创建字典，这里`dict` 功能用于创建字典。

```
# Python3 code to demonstrate
# List of tuple to dictionary conversion
# using dict() + dictionary comprehension

# initializing list
test_list = [('Nikhil', 21, 'JIIT'), ('Akash', 22, 'JIIT'), ('Akshat', 22, 'JIIT')]

# printing original list
print("The original list : " + str(test_list))

# using dict() + dictionary comprehension
# List of tuple to dictionary conversion
res = dict((idx[0], idx[1:]) for idx in test_list) 

# print result
print("The dictionary after conversion : " + str(res))
```

**Output :**

> 原列表:[(“Nikhil”，21，“JIIT”)，(“Akash”，22，“JIIT”)，(“Akshat”，22，“JIIT”)]
> 转换后的字典:{“Nikhil”:(21，“JIIT”)，“Akshat”:(22，“JIIT”)，“Akash”:(22，“JIIT”)}