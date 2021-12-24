# Python |表格 k 清单

> 原文:[https://www.geeksforgeeks.org/python-modulo-k-list/](https://www.geeksforgeeks.org/python-modulo-k-list/)

在使用 python 列表时，我们会遇到这样一种情况，我们需要对列表中的每个元素取整数 k 的模。我们可能需要对每个元素进行迭代和取模 k，但这会增加代码的行数。让我们讨论一下执行这项任务的某些人手不足的情况。

**方法#1:使用列表理解**
列表理解只是执行我们使用天真方法执行的任务的简单方法。这主要有助于节省时间，在代码可读性方面也是最好的。

```py
# Python3 code to demonstrate 
# Modulo K List
# using list comprehension

# initializing list 
test_list = [4, 5, 6, 3, 9]

# printing original list
print ("The original list is : " + str(test_list))

# initializing K
K = 4

# using list comprehension
# Modulo K List
res = [x % K for x in test_list]

# printing result 
print ("The list after Modulo K to each element : " + str(res))
```

**Output :**

```py
The original list is : [4, 5, 6, 3, 9]
The list after Modulo K to each element : [0, 1, 2, 3, 1]

```