# Python |基于 Kth 元素元组列表删除重复项

> 原文:[https://www . geesforgeks . org/python-remove-duplicates-based-on-kth-element-tuple-list/](https://www.geeksforgeeks.org/python-remove-duplicates-based-on-kth-element-tuple-list/)

有时，在处理记录时，我们可能会遇到一个问题，即需要根据列表中元组的 Kth 元素删除重复项。这个问题适用于使用记录作为输入的领域。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用循环**
这是一个蛮力方法来执行这个特定的任务。在这种情况下，我们检查元组的 Kth 索引，并添加到一个集合中以保持记录。如果该值已经在内存集中，我们将从结果中丢弃它，因为它是重复的。

```
# Python3 code to demonstrate working of
# Remove duplicates based on Kth element tuple list
# Using loop

# initialize list 
test_list = [(3, 1, 5), (1, 3, 6), (2, 1, 7),
                        (5, 2, 8), (6, 3, 0)]

# printing original list
print("The original list is : " + str(test_list))

# initialize K 
K = 1 

# Remove duplicates based on Kth element tuple list
# Using loop
temp = set()   
res = []
for ele in test_list:
    if ele[K] not in temp:
        res.append(ele)
        temp.add(ele[K])

# printing result
print("The list after removal of K based duplicates : " + str(res))
```

**Output :**

> 原列表为:[(3，1，5)，(1，3，6)，(2，1，7)，(5，2，8)，(6，3，0)]
> 去除 K 基副本后的列表:[(3，1，5)，(1，3，6)，(5，2，8)]