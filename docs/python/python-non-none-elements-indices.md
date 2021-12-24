# Python–非无元素索引

> 原文:[https://www . geesforgeeks . org/python-non-non-elements-indexes/](https://www.geeksforgeeks.org/python-non-none-elements-indices/)

很多时候，在数据科学领域工作时，我们需要得到所有非无索引的列表，这样它们就很容易被前置。这是一个很受欢迎的问题，解决它的方法很方便。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+ `range()`**
在该方法中，我们只需使用范围函数检查每个索引，如果发现该索引不是无，则存储该索引。

```py
# Python3 code to demonstrate
# Non-None elements indices
# using list comprehension + enumerate

# initializing list 
test_list = [1, None, 4, None, None, 5]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + enumerate
# Non-None elements indices 
res = [i for i in range(len(test_list)) if test_list[i] != None]

# print result
print("The Non None indices list is : " + str(res))
```

**Output :**

```py
The original list : [1, None, 4, None, None, 5]
The Non None indices list is : [0, 2, 5]

```