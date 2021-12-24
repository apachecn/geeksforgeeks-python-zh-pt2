# Python |列表 K 扩展

> 原文:[https://www.geeksforgeeks.org/python-list-expansion-by-k/](https://www.geeksforgeeks.org/python-list-expansion-by-k/)

有时，我们需要减少 python 列表的长度，但其他时候，我们可能也需要通过重复 N 次每个元素来增加它的大小。这种类型的实用程序可以在日常编程中使用。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解**
这个任务可以使用列表理解方法来执行，该方法只是通用循环方法的缩短版本，在该方法中，我们使用迭代将每个元素重复 K 次。

```
# Python3 code to demonstrate
# List extension by K 
# using list comprehension

# initializing list
test_list = [4, 5, 2, 8]

# printing original list 
print("The original list : " + str(test_list))

# initializing K
K = 3

# using list comprehension 
# to extend list 
res = [i for i in test_list for j in range(K)]

# printing result
print("The resultant list after extension is : " + str(res))
```

**Output :**

> 原列表:[4，5，2，8]
> 扩展后的结果列表为:[4，4，4，5，5，5，2，2，8，8，8]