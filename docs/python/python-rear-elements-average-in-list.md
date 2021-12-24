# Python–列表中的后元素平均值

> 原文:[https://www . geeksforgeeks . org/python-后置元素-列表中的平均值/](https://www.geeksforgeeks.org/python-rear-elements-average-in-list/)

有时，在处理数据时，我们会遇到一个问题，即我们需要计算 k 之后所有后面元素的平均值。这可能是数学和数据科学领域的一个应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`sum()` +列表理解**
上述功能的组合可用于执行该任务。在这种情况下，我们首先让初始的 K 元素保持原样，并执行元素剩余部分的求和和除以剩余元素的数量。

```
# Python3 code to demonstrate 
# Rear elements Average in List
# using list comprehension + sum()

# Initializing list
test_list = [5, 6, 4, 7, 8, 1, 10]

# printing original list
print("The original list is : " + str(test_list))

# Initializing K 
K = 3

# Rear elements Average in List
# using list comprehension + sum()
res = test_list[ : K] + [sum(test_list[K:]) / len(test_list[K: ])]

# printing result 
print ("Average List after K elements : " + str(res))
```

**Output :**

```
The original list is : [5, 6, 4, 7, 8, 1, 10]
Average List after K elements : [5, 6, 4, 6.5]

```