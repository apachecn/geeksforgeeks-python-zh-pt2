# Python–K 字符上列表的拆分字符串

> 原文:[https://www . geesforgeks . org/python-拆分-k 字符列表字符串/](https://www.geeksforgeeks.org/python-split-string-of-list-on-k-character/)

有时在处理数据时，我们可能会遇到这样的问题:我们需要对字符串执行拆分操作，有时，我们可能还需要将它们整体执行到嵌套的字符串中。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环+ `split()`**
上述功能的组合可用于执行该任务。在本文中，我们遍历每个列表字符串并执行手动拆分，然后使用 extend()和 loop 将新元素添加到该列表中。

```py
# Python3 code to demonstrate 
# Split String of list on K character
# using loop + split()

# Initializing list 
test_list = ['Gfg is best', 'for Geeks', 'Preparing']

# printing original list
print("The original list is : " + str(test_list))

K = ' '

# Split String of list on K character
# using loop + split()
res = []
for ele in test_list:
    sub = ele.split(K)
    res.extend(sub)

# printing result 
print ("The extended list after split strings : " + str(res))
```

**Output :**

```py
The original list is : ['Gfg is best', 'for Geeks', 'Preparing']
The extended list after split strings : ['Gfg', 'is', 'best', 'for', 'Geeks', 'Preparing']

```