# Python–列表中元素的步进频率

> 原文:[https://www . geesforgeks . org/python-步骤-列表中元素的频率/](https://www.geeksforgeeks.org/python-step-frequency-of-elements-in-list/)

有时候，在使用 Python 时，我们会遇到一个问题，需要计算列表中的频率。这是一个很常见的问题，在很多领域都有使用案例。但是我们有时会遇到这样的问题:我们需要对列表中的元素进行递增计数。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `defaultdict()`**
以上功能的组合可以用来执行这个任务。在这种情况下，我们只需用默认值初始化列表，并使用循环增加其频率。

```
# Python3 code to demonstrate 
# Step Frequency of elements in List
# using loop + defaultdict()
from collections import defaultdict

# Initializing loop 
test_list = ['gfg', 'is', 'best', 'gfg', 'is', 'life']

# printing original list 
print("The original list is : " + str(test_list))

# Step Frequency of elements in List
# using loop + defaultdict()
res_d = defaultdict(int)
res = []
for ele in test_list:
    res_d[ele] += 1
    res.append(res_d[ele])

# printing result 
print ("Step frequency of elements is : " + str(res))
```

**Output :**

```
The original list is : ['gfg', 'is', 'best', 'gfg', 'is', 'life']
Step frequency of elements is : [1, 1, 1, 2, 2, 1]

```