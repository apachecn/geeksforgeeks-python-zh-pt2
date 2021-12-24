# Python–字符串列表中的特定案例更改

> 原文:[https://www . geesforgeks . org/python-特定大小写-字符串列表变化/](https://www.geeksforgeeks.org/python-specific-case-change-in-string-list/)

在使用字符串列表时，案例的问题是常见的，但有时，我们会有选择地关注字符串中的变更案例。即基于其他列表。这可以在日常编程中应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `upper() + enumerate()`**
这是可以执行此任务的方式之一。在本例中，我们对每个元素和比较字符串运行一个循环，如果发现相等，那么这些列表的情况不会改变，其余字符串的情况会改变。

```
# Python3 code to demonstrate 
# Specific case change in String List
# using loop + upper() + enumerate() 

# Initializing lists
test_list1 = ['GFG', 'IS', 'BEST', 'FOR', 'GEEKS']
test_list2 = ['Gfg', 'Best']

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Specific case change in String List
# using loop + upper() + enumerate() 
for idx, ele in enumerate(test_list1):
    for ele2 in test_list2:
        if ele == ele2.upper():
            test_list1[idx] = ele2

# printing result 
print ("The string list after case change is : " + str(test_list1))
```

**Output :**

```
The original list 1 is : ['GFG', 'IS', 'BEST', 'FOR', 'GEEKS']
The original list 2 is : ['Gfg', 'Best']
The string list after case change is : ['Gfg', 'IS', 'Best', 'FOR', 'GEEKS']

```