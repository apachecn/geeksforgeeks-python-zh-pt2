# Python–最具独特元素的列表

> 原文:[https://www . geesforgeks . org/python-最独特元素列表/](https://www.geeksforgeeks.org/python-list-with-most-unique-elements/)

有时，在处理数据时，我们会遇到一个问题，即我们需要计算具有最多唯一元素的列表。这在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `max() + set()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 max()计算最大出现元素，并使用 set()将逻辑简化为唯一性。

```py
# Python3 code to demonstrate 
# List with most unique elements
# using list comprehension + max() + set()

# Initializing lists
test_list1 = [1, 3, 4, 4, 4, 3, 3, 2, 2, 1]
test_list2 = [1, 3, 4, 6, 7]
test_list3 = [4, 5, 4, 3, 6, 7, 8]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))
print("The original list 3 is : " + str(test_list3))

# List with most unique elements
# using list comprehension + max() + set()
res = [ele for ele in [set(test_list1), set(test_list2), set(test_list3)]
      if len(ele) == max([len(sub) for sub in [set(test_list1), set(test_list2), set(test_list3)]])][0]

# printing result 
print ("List with Most unique values : " + str(list(res)))
```

**Output :**

```py
The original list 1 is : [1, 3, 4, 4, 4, 3, 3, 2, 2, 1]
The original list 2 is : [1, 3, 4, 6, 7]
The original list 3 is : [4, 5, 4, 3, 6, 7, 8]
List with Most unique values : [3, 4, 5, 6, 7, 8]

```