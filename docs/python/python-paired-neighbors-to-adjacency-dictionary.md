# Python–相邻字典的成对邻居

> 原文:[https://www . geesforgeks . org/python-配对-邻居-邻接-字典/](https://www.geeksforgeeks.org/python-paired-neighbors-to-adjacency-dictionary/)

有时在使用 Python 对时，我们可能会遇到这样的问题，即哪些对代表邻居，我们需要计算每个元素的邻居。这种问题在竞争性编程和处理图形时非常常见。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以用来解决这个问题的方法之一。在这种情况下，我们预先设置所需的键，用空列表构造字典，并迭代添加值的对列表。

```
# Python3 code to demonstrate working of 
# Paired Neighbours to Adjacency Dictionary
# Using loop

# initializing list
test_list = [(1, 2), (4, 5), (1, 3), (3, 4), (5, 6), (6, 2)]

# printing original list
print("The original list is : " + str(test_list))

# Paired Neighbours to Adjacency Dictionary
# Using loop
res = {1: [], 2: [], 3: [], 4: [], 5: [], 6: []}
for sub in test_list:
    res[sub[0]].append(sub[1])
    res[sub[1]].append(sub[0])

# printing result 
print("The Neighbours Paired Dictionary : " + str(res)) 
```

**Output :**

> 原始列表为:[(1，2)，(4，5)，(1，3)，(3，4)，(5，6)，(6，2)]
> 邻居配对字典:{1: [2，3]，2: [1，6]，3: [1，4]，4: [5，3]，5: [4，6]，6: [5，2]}