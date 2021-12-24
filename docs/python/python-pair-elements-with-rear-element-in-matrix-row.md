# Python–将元素与矩阵行中的后元素配对

> 原文:[https://www . geeksforgeeks . org/python-对-元素-带-后元素-在矩阵中-行/](https://www.geeksforgeeks.org/python-pair-elements-with-rear-element-in-matrix-row/)

有时候，在处理数据时，我们可能会遇到一个问题，即我们需要将容器中的每个元素与特定的索引元素配对，比如后置元素。这种问题在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解**
这是执行该任务的一种方式。在这种情况下，我们遍历列表中的每个行元素，并使用列表的负索引将其与后元素配对。

```
# Python3 code to demonstrate 
# Pair elements with Rear element in Matrix Row
# using list comprehension

# Initializing list
test_list = [[4, 5, 6], [2, 4, 5], [6, 7, 5]]

# printing original list
print("The original list is : " + str(test_list))

# Pair elements with Rear element in Matrix Row
# using list comprehension
res = []
for sub in test_list:
    res.append([[ele, sub[-1]] for ele in sub[:-1]])

# printing result 
print ("The list after pairing is : " + str(res))
```

**Output :**

```
The original list is : [[4, 5, 6], [2, 4, 5], [6, 7, 5]]
The list after pairing is : [[[4, 6], [5, 6]], [[2, 5], [4, 5]], [[6, 5], [7, 5]]]

```