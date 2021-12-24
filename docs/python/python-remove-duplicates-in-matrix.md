# Python |移除矩阵中的重复项

> 原文:[https://www . geesforgeks . org/python-remove-replicates-in-matrix/](https://www.geeksforgeeks.org/python-remove-duplicates-in-matrix/)

在使用 Python Matrix 时，我们可能会面临一个问题，即我们需要从 Matrix 中删除重复项。由于矩阵的广泛使用，这个问题在机器学习领域可能会出现。让我们讨论一下执行这项任务的具体方法。

**方法:使用循环**
这个任务可以使用循环以蛮力方式执行。在这种情况下，我们只是使用循环迭代列表，检查元素是否已经存在，如果是新元素，则追加，并构造一个非重复矩阵。

```py
# Python3 code to demonstrate working of
# Removing duplicates in Matrix
# using loop

# initialize list 
test_list = [[5, 6, 8], [8, 5, 3], [9, 10, 3]]

# printing original list
print("The original list is : " + str(test_list))

# Removing duplicates in Matrix
# using loop
res = []
track = []
count = 0

for sub in test_list:
    res.append([]);
    for ele in sub:
        if ele not in track:
             res[count].append(ele)
             track.append(ele)
    count += 1

# printing result
print("The Matrix after duplicates removal is : " + str(res))
```

**Output :**

```py
The original list is : [[5, 6, 8], [8, 5, 3], [9, 10, 3]]
The Matrix after duplicates removal is : [[5, 6, 8], [3], [9, 10]]

```