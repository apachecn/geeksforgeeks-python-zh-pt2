# Python–列表中特定范围的添加

> 原文:[https://www . geesforgeks . org/python-specific-range-addition-in-list/](https://www.geeksforgeeks.org/python-specific-range-addition-in-list/)

有时，在使用 Python 时，我们需要在 Python 列表中执行编辑。有时我们需要对其中的特定索引范围执行此操作。这种应用可以在许多领域得到应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是一种可以执行该任务的暴力方式。在这种情况下，我们只需遍历必须执行编辑的指定范围。

```py
# Python3 code to demonstrate 
# Specific Range Addition in List
# using loop

# Initializing list
test_list = [4, 5, 6, 8, 10, 11]

# printing original list 
print("The original list is : " + str(test_list))

# Initializing range 
i, j = 2, 5

# Specific Range Addition in List
# using loop
for idx in range(i, j):
    test_list[idx] += 3

# printing result 
print ("List after range addition : " + str(test_list))
```

**Output :**

```py
The original list is : [4, 5, 6, 8, 10, 11]
List after range addition : [4, 5, 9, 11, 13, 11]

```