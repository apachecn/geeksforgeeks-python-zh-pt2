# Python–后缀列表总和

> 原文:[https://www.geeksforgeeks.org/python-suffix-list-sum/](https://www.geeksforgeeks.org/python-suffix-list-sum/)

如今，特别是在竞争编程领域，计算后缀和的效用在许多问题中非常普遍和有特色。因此，有一个单一的解决方案会有很大的帮助。让我们讨论一下解决这个问题的某些方法。

**方法:使用列表理解+ `sum()` +列表切片**
这个问题可以通过上面两个函数的组合来解决，其中我们使用列表理解来将逻辑扩展到每个元素，求和函数来获得和，切片用于获得和，直到特定的索引。

```py
# Python3 code to demonstrate
# Suffix List Sum 
# using list comprehension + sum() + list slicing 

# initializing list
test_list = [3, 4, 1, 7, 9, 1]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + sum() + list slicing
# Suffix List Sum 
test_list.reverse()
res = [sum(test_list[ : i + 1 ]) for i in range(len(test_list))]

# print result
print("The suffix sum list is : " + str(res))
```

**Output :**

```py
The original list : [3, 4, 1, 7, 9, 1]
The suffix sum list is : [1, 10, 17, 18, 22, 25]

```