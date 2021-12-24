# Python |列表中元素对的连接方式

> 原文:[https://www . geesforgeks . org/python-列表中元素对的连接方式/](https://www.geeksforgeeks.org/python-ways-to-join-pair-of-elements-in-list/)

给定一个列表，任务是连接列表中的一对元素。下面给出了一些解决给定任务的方法。

**方法#1:使用`zip()`方法**

```
# Python code to demonstrate 
# how to join pair of elements of list

# Initialising list
ini_list = ['a', 'b', 'c', 'd', 'e', 'f']

# Printing initial list 
print ("Initial list", str(ini_list))

# Pairing the elements of lists
res = [i + j for i, j in zip(ini_list[::2], ini_list[1::2])]

# Printing final result
print ("Result", str(res))
```

**输出:**

```
Initial list ['a', 'b', 'c', 'd', 'e', 'f']
Result ['ab', 'cd', 'ef']

```