# Python–列表中的后移 K

> 原文:[https://www.geeksforgeeks.org/python-rear-shift-k-in-list/](https://www.geeksforgeeks.org/python-rear-shift-k-in-list/)

涉及元素转移的传统问题在前面已经讨论过很多次了，但是有时我们有严格的约束来执行它们，任何可能的变化的知识都会有所帮助。本文讨论了这样一个在列表末尾移动 K 的问题，这里要注意的是，它只检查 K，不包括传统的“无”(假)值。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+ `isinstance()`**
在该方法中，我们分 2 步执行移位操作。在第一步中，我们得到了我们需要在前端得到的所有值，在末端我们只是把 K 推到末端。isinstance 方法用于过滤掉布尔假实体。

```
# Python3 code to demonstrate
# Rear shift K in List
# using list comprehension + isinstance()

# initializing list
test_list = [1, 4, None, "Manjeet", False, 4, False, 4, "Nikhil"]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = 4

# using list comprehension + isinstance()
# Rear shift K in List
temp = [ele for ele in test_list if ele != K and ele or ele is None or isinstance(ele, bool) ]
res = temp + [K] * (len(test_list) - len(temp))

# print result
print("The list after shifting K's to end : " + str(res))
```

**Output :**

```
The original list : [1, 4, None, 'Manjeet', False, 4, False, 4, 'Nikhil']
The list after shifting K's to end : [1, None, 'Manjeet', False, False, 'Nikhil', 4, 4, 4]

```