# Python–在矩阵中列出字符串频率

> 原文:[https://www . geesforgeks . org/python-list-strings-frequency-in-matrix/](https://www.geeksforgeeks.org/python-list-strings-frequency-in-matrix/)

有时，在使用 Matrix 时，我们会遇到一个问题，即我们需要检查 Matrix 每行中来自 List 的参数字符串的频率。这是一个非常特殊的问题，在许多领域都有用处。让我们讨论解决这个任务的某些方法。

**方法#1:使用`count()` +循环**
上述功能的组合可用于执行该任务。在本例中，我们使用 count()计算频率，迭代任务在循环中执行。

```
# Python3 code to demonstrate 
# List Strings frequency in Matrix
# using count() + loop

# Initializing lists
test_list1 = [['Gfg', 'is', 'best'], ['Gfg', 'is', 'for', 'CS'], ['Gfg', 'is', 'for', 'Geeks']]
test_list2 = ['Gfg', 'is', 'best']

# printing original list1
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# List Strings frequency in Matrix
# using count() + loop
res = []
for val in test_list1:
    res.append([val.count(ele) for ele in test_list2])

# printing result 
print ("Frequency of strings in Matrix : " + str(res))
```

**Output :**

```
The original list 1 is : [['Gfg', 'is', 'best'], ['Gfg', 'is', 'for', 'CS'], ['Gfg', 'is', 'for', 'Geeks']]
The original list 2 is : ['Gfg', 'is', 'best']
Frequency of strings in Matrix : [[1, 1, 1], [1, 1, 0], [1, 1, 0]]

```