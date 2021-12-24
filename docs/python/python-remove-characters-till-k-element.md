# Python–删除字符直到 K 元素

> 原文:[https://www . geesforgeks . org/python-remove-characters-till-k-element/](https://www.geeksforgeeks.org/python-remove-characters-till-k-element/)

有时，在使用 Python 时，我们可能会遇到这样的问题:我们需要让列表中的所有元素出现在列表中的特定字符之后。这种问题可以在数据领域和 web 开发中得到应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方法。在这种情况下，我们迭代循环，直到找到 K，然后开始添加字符，看起来就像删除 K 之前的元素。

```py
# Python3 code to demonstrate 
# Remove characters till K element
# using loop

# Initializing list
test_list = ['gfg', 'is', 'best', 'for', 'geeks']

# printing original list
print("The original list is : " + str(test_list))

# Initializing K 
K = 'best'

# Remove characters till K element
# using loop
res = []
flag = 0
for ele in test_list:
    if ele == K:
        flag = 1 
        continue
    if flag:
        res.append(ele)

# printing result 
print ("List elements after removing all before K : " + str(res))
```

**Output :**

```py
The original list is : ['gfg', 'is', 'best', 'for', 'geeks']
List elements after removing all before K : ['for', 'geeks']

```