# 在 Python 中减去字符串列表

> 原文:[https://www . geesforgeks . org/减法-字符串列表-in-python/](https://www.geeksforgeeks.org/subtract-string-lists-in-python/)

有时，在处理列表时，我们可能会遇到一个问题，即我们需要从其他列表元素中移除一个列表元素，即执行减法。这在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + remove()**
上述功能的组合可用于执行此任务。在本文中，我们使用 remove()执行元素移除，并使用 loop 检查相似的元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Subtract String Lists
# using loop + remove()

# initialize lists
test_list1 = ["gfg", "is", "best", "for", "CS"]
test_list2 = ["preferred", "is", "gfg"]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# Subtract String Lists
# using loop + remove()
res = [ ele for ele in test_list1 ]
for a in test_list2:
  if a in test_list1:
    res.remove(a)

# printing result
print("The Subtracted list is : " + str(res))
```

**Output**

```py
The original list 1 : ['gfg', 'is', 'best', 'for', 'CS']
The original list 2 : ['preferred', 'is', 'gfg']
The Subtracted list is : ['best', 'for', 'CS']
```

**方法#2:使用 Counter() + elements()**
以上功能的组合提供了解决这个问题的简写。在这种情况下，我们提取两个列表中的元素计数，然后通过使用 element()提取它们来执行分离。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Subtract String Lists
# using Counter() + elements()
from collections import Counter

# initialize lists
test_list1 = ["gfg", "is", "best", "for", "CS"]
test_list2 = ["preferred", "is", "gfg"]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# Subtract String Lists
# using Counter() + elements()
res = list((Counter(test_list1)-Counter(test_list2)).elements())

# printing result
print("The Subtracted list is : " + str(res))
```

**Output**

```py
The original list 1 : ['gfg', 'is', 'best', 'for', 'CS']
The original list 2 : ['preferred', 'is', 'gfg']
The Subtracted list is : ['best', 'for', 'CS']
```