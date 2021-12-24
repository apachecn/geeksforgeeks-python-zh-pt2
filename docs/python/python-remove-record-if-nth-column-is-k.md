# Python–如果第 n 列为 K

，则删除记录

> 原文:[https://www . geesforgeks . org/python-remove-record-if-n-column-is-k/](https://www.geeksforgeeks.org/python-remove-record-if-nth-column-is-k/)

有时，在处理记录列表时，我们可能会遇到一个问题，即我们需要根据记录的第 n 个位置是否存在某些元素来执行记录删除。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方法。在这种情况下，我们对列表中的每个元素进行迭代，如果它的第 N 列等于 k，则排除它。

```
# Python3 code to demonstrate 
# Remove Record if Nth Column is K
# using loop

# Initializing list
test_list = [(5, 7), (6, 7, 8), (7, 8, 10), (7, 1)]

# printing original list
print("The original list is : " + str(test_list))

# Initializing K 
K = 7

# Initializing N 
N = 1

# Remove Record if Nth Column is K
# using loop
res = []
for sub in test_list:
    if (sub[N] != K):
        res.append(sub)

# printing result 
print ("List after removal : " + str(res))
```

**Output :**

```
The original list is : [(5, 7), (6, 7, 8), (7, 8, 10), (7, 1)]
List after removal : [(7, 8, 10), (7, 1)]

```