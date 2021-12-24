# Python–相似索引元素频率

> 原文:[https://www . geesforgeks . org/python-相似-索引-元素-频率/](https://www.geeksforgeeks.org/python-similar-index-elements-frequency/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们需要检查一个元素在其他列表中是否有相似的索引出现。这可能在许多领域有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`sum() + zip()`**
上述功能的组合可用于执行该任务。在这种情况下，我们对交叉列表中匹配的元素求和。

```
# Python3 code to demonstrate 
# Similar index elements frequency
# using sum() + zip()

# Initializing lists 
test_list1 = [1, 3, 5, 6, 8]
test_list2 = [4, 3, 6, 6, 10]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Similar index elements frequency
# using sum() + zip()
res = sum(x == y for x, y in zip(test_list1, test_list2))

# printing result 
print ("Number of elements having similar index : " + str(res))
```

**Output :**

```
The original list 1 is : [1, 3, 5, 6, 8]
The original list 2 is : [4, 3, 6, 6, 10]
Number of elements having similar index : 2

```