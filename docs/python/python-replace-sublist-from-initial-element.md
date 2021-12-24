# Python–从初始元素

替换子列表

> 原文:[https://www . geesforgeks . org/python-replace-sublist-from-initial-element/](https://www.geeksforgeeks.org/python-replace-sublist-from-initial-element/)

给定列表和替换子列表，基于替换子列表的初始元素执行列表子列表的替换。

> **输入** : test_list = [3，7，5，3]，repl_list = [7，8]
> **输出** : [3，7，8，3]
> **说明**:7 开始更换，因此 7 和 8 被更换。
> 
> **输入** : test_list = [3，7，5，3，9，10]，repl_list = [5，6，7，4]
> **输出** : [3，7，5，6，7，4]
> **:替换从 5 开始，一直到列表结束。**

****方法:使用列表理解+列表切片**
以上功能的组合可以用来解决这个问题。在这种情况下，我们提取开始元素的索引，然后根据需求对列表进行适当的切片。**

```py
# Python3 code to demonstrate working of 
# Replace substring from Initial element
# Using list slicing + list comprehension

# initializing list
test_list = [5, 2, 6, 4, 7, 1, 3]

# printing original list 
print("The original list : " + str(test_list))

# initializing repl_list 
repl_list = [6, 10, 18]

# Replace substring from Initial element
# Extracting index
idx = test_list.index(repl_list[0])

# Slicing till index, and then adding rest of list
res = test_list[ :idx] + repl_list + test_list[idx + len(repl_list):]

# printing result 
print("Substituted List : " + str(res))
```

****Output :**

```py
The original list : [5, 2, 6, 4, 7, 1, 3]
Substituted List : [5, 2, 6, 10, 18, 1, 3]

```**