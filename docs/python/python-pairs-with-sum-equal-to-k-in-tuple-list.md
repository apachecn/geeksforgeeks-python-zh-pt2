# Python–元组列表中总和等于 K 的对

> 原文:[https://www . geeksforgeeks . org/python-对与和等于元组列表中的 k/](https://www.geeksforgeeks.org/python-pairs-with-sum-equal-to-k-in-tuple-list/)

有时，在处理数据时，我们会遇到一个问题，即我们需要找到元组列表对的总和。这类问题在网页开发和竞争性编程中可能很重要。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这个可以使用循环来解决。这是执行这项任务的粗暴方式。在这种情况下，我们迭代对求和的列表并保留其和为 k 的列表。

```py
# Python3 code to demonstrate 
# Pairs with Sum equal to K in tuple list
# using loop

# Initializing list
test_list = [(4, 5), (6, 7), (3, 6), (1, 2), (1, 8)]

# printing original list
print("The original list is : " + str(test_list))

# Initializing K 
K = 9

# Pairs with Sum equal to K in tuple list
# using loop
res = []
for ele in test_list:
    if ele[0] + ele[1] == K: 
        res.append(ele)

# printing result 
print ("List after extracting pairs equal to K : " + str(res))
```

**Output :**

```py
The original list is : [(4, 5), (6, 7), (3, 6), (1, 2), (1, 8)]
List after extracting pairs equal to K : [(4, 5), (3, 6), (1, 8)]

```