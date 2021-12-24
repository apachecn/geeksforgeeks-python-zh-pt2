# Python–最大和记录

> 原文:[https://www.geeksforgeeks.org/python-maximum-sum-record/](https://www.geeksforgeeks.org/python-maximum-sum-record/)

有时，在处理数据时，我们可能会遇到一个问题，即我们需要找到列表中可用对之间的最大和。这可以应用于数学领域的许多问题。让我们讨论执行这项任务的某些方法。

**方法#1:使用`max()` +列表理解**
该功能的组合可用于执行该任务。在这种情况下，我们计算所有对的和，然后使用 max()返回它的最大值。

```
# Python3 code to demonstrate working of
# Maximum Sum Record
# Using list comprehension + max()

# initialize list
test_list = [(3, 5), (1, 7), (10, 3), (1, 2)]

# printing original list 
print("The original list : " + str(test_list))

# Maximum Sum Record
# Using list comprehension + max()
temp = [b + a for a, b in test_list]
res = max(temp)

# printing result
print("Maximum sum among pairs : " + str(res))
```

**Output :**

```
The original list : [(3, 5), (1, 7), (10, 3), (1, 2)]
Maximum sum among pairs : 13

```