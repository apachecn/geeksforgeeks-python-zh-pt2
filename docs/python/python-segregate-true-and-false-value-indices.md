# Python |分离真假值索引

> 原文:[https://www . geeksforgeeks . org/python-separate-true-and-false-value-indexs/](https://www.geeksforgeeks.org/python-segregate-true-and-false-value-indices/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们有布尔列表，并要求分别有真值和假值的索引。这可能在数据科学领域有所应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是执行该任务的一种方式。我们创建不同的列表，使用条件语句检查真值或假值，并相应地将其索引附加到专用列表中。

```
# Python3 code to demonstrate working of
# Segregate True and False value indices
# using loops

# initialize list
test_list = [False, True, False, False, True, True]

# printing original list
print("The original list is : " + str(test_list))

# Segregate True and False value indices
# using loops
res_true, res_false = [], []
for i in range(0, len(test_list)):
    if test_list[i]:
        res_true.append(i)
    else :
        res_false.append(i)

# printing result
print("True indices after grouping : " + str(res_true))
print("False indices after grouping : " + str(res_false))
```

**Output :**

```
The original list is : [False, True, False, False, True, True]
True indices after grouping : [1, 4, 5]
False indices after grouping : [0, 2, 3]

```