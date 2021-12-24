# Python–按第 k 列对矩阵行进行反向排序

> 原文:[https://www . geesforgeks . org/python-reverse-sort-matrix-逐行-kth-column/](https://www.geeksforgeeks.org/python-reverse-sort-matrix-row-by-kth-column/)

有时，在处理数据时，我们可能会遇到这样的问题，即需要根据一些决定性因素(如分数)对每行记录进行排序。这种问题在竞争性编程和 web 开发中很常见。让我们讨论执行这项任务的某些方法。

**方法一:使用`sorted()` + lambda + reverse**
以上方法的组合可以用来执行此任务。在这种情况下，我们使用 lambda 函数和列表理解，按照特定的列，使用逆序对列表进行降序排序。

```
# Python3 code to demonstrate 
# Reverse sort Matrix Row by Kth Column
# using sorted() + lambda + reverse()

# Initializing list
test_list = [['Manjeet', 65], ['Akshat', 42], ['Akash', 38], ['Nikhil', 192]]

# printing original lists
print("The original list is : " + str(test_list))

# Initializing K 
K = 1

# Reverse sort Matrix Row by Kth Column
# using sorted() + lambda + reverse()
res = sorted(test_list, key = lambda ele: ele[K], reverse = True)

# printing result 
print ("List after performing sorting of matrix records : " + str(res))
```

**Output :**

> 原列表为:[['Manjeet '，65]，['Akshat '，42]，['Akash '，38]，['Nikhil '，192]]
> 执行矩阵记录排序后的列表:['Nikhil '，192]，['Manjeet '，65]，['Akshat '，42]，['Akash '，38]]