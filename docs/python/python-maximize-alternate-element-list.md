# Python |最大化替代元素列表

> 原文:[https://www . geesforgeks . org/python-maximum-alternate-element-list/](https://www.geeksforgeeks.org/python-maximize-alternate-element-list/)

获取列表最大值的问题是非常普遍的，我们可能有一天会面临获取替代元素最大值的问题，并获取包含替代元素最大值的 2 个元素的列表。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+列表切片+ `max()`**
使用列表理解的列表切片可以用来执行这个特定的任务。我们可以通过列表理解来获得运行逻辑，列表切片可以通过最大化函数来分割出可选字符。

```
# Python3 code to demonstrate
# Maximize alternate element List
# using list comprehension + list slicing + max()

# initializing list 
test_list = [2, 1, 5, 6, 8, 10]

# printing original list 
print("The original list : " + str(test_list))

# using list comprehension + list slicing + max()
# Maximize alternate element List
res = [max(test_list[i : : 2]) for i in range(len(test_list) // (len(test_list)//2))]

# print result
print("The alternate elements maximum list : " + str(res))
```

**Output :**

```
The original list : [2, 1, 5, 6, 8, 10]
The alternate elements maximum list : [8, 10]

```