# Python |在空字符串上拆分列表

> 原文:[https://www . geesforgeks . org/python-拆分-空字符串列表/](https://www.geeksforgeeks.org/python-splitting-list-on-empty-string/)

有时，我们可能会遇到这样一个问题，即我们需要根据作为发货人发送的空白字符将一个列表拆分为多个列表。这种问题可以用于发送消息，也可以用于需要本地列表的列表的情况。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`index()`和列表切片**
列表切片可用于从本地列表中获取子列表，索引函数可用于检查可能充当分隔符的空字符串。这样做的缺点是，它只适用于单个拆分，即只能将一个列表分成两个子列表。

```py
# Python3 code to demonstrate
# divide list to siblist on deliminator
# using index() + list slicing 

# initializing list 
test_list = ['Geeks', 'for', '', 'Geeks', 1, 2]

# printing original list
print("The original list : " + str(test_list))

# using index() + list slicing
# divide list to siblist on deliminator
temp_idx = test_list.index('')
res = [test_list[: temp_idx], test_list[temp_idx + 1: ]]

# print result
print("The list of sublist after separation : " + str(res))
```

**Output :**

> 原列表:['Geeks '，' for '，"，' Geeks '，1，2]
> 分离后的子列表:['Geeks '，' for']，['Geeks '，1，2]]