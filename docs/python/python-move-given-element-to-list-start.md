# Python |将给定元素移动到列表开始处

> 原文:[https://www . geesforgeks . org/python-move-given-element-to-list-start/](https://www.geeksforgeeks.org/python-move-given-element-to-list-start/)

涉及元素转移的传统问题在前面已经讨论过很多次了，但是有时我们有严格的约束来执行它们，任何可能的变化的知识都会有所帮助。本文讨论了一个这样的问题，在列表的开头移动 K，这里要注意的是，它只检查 K，不包括传统的“无”(假)值。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+ `isinstance()`**
在该方法中，我们分 2 步执行移位操作。在第一步中，我们得到了我们需要在前端得到的所有值，最后我们只是把 K 推到前端。isinstance 方法用于过滤掉布尔假实体。

```py
# Python3 code to demonstrate 
# Move all K element to List Start
# using list comprehension + isinstance() 

# initializing list 
test_list = [1, 4, None, "Manjeet", False, 4, False, 4, "Nikhil"] 

# printing original list 
print("The original list : " + str(test_list)) 

# initializing K 
K = 4

# using list comprehension + isinstance() 
# Move all K element to List Start
temp = [ele for ele in test_list if ele != K and ele or ele is None or isinstance(ele, bool) ] 
res = [K] * (len(test_list) - len(temp)) + temp

# print result 
print("The list after shifting K's to start : " + str(res)) 
```

**Output :**

```py
The original list : [1, 4, None, 'Manjeet', False, 4, False, 4, 'Nikhil']
The list after shifting K's to start : [4, 4, 4, 1, None, 'Manjeet', False, False, 'Nikhil']

```