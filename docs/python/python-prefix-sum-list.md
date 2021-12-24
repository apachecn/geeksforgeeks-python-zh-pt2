# Python |前缀和列表

> 原文:[https://www.geeksforgeeks.org/python-prefix-sum-list/](https://www.geeksforgeeks.org/python-prefix-sum-list/)

如今，特别是在竞争编程领域，计算前缀和的效用在许多问题中非常普遍和有特点。因此，有一个单一的解决方案会有很大的帮助。让我们讨论一下解决这个问题的某些方法。

**方法一:使用列表理解+求和()+列表切片**

这个问题可以通过上述两个函数的组合来解决，其中我们使用列表理解来将逻辑扩展到每个元素，使用求和函数来获得和，使用切片来获得和，直到特定的索引。

```py
# Python3 code to demonstrate
# prefix sum list
# using list comprehension + sum() + list slicing 

# initializing list
test_list = [3, 4, 1, 7, 9, 1]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + sum() + list slicing
# prefix sum list
res = [sum(test_list[ : i + 1]) for i in range(len(test_list))]

# print result
print("The prefix sum list is : " + str(res))
```

**Output :**

```py
The original list : [3, 4, 1, 7, 9, 1]
The prefix sum list is : [3, 7, 8, 15, 24, 25]

```

**方法#2:** 使用`accumulate(iterable)`方法。

```py
# function to find cumulative sum of list
from itertools import accumulate 

def cumulativeSum(lst): 
    print (list(accumulate(lst))) 

# Driver program 
if __name__ == "__main__": 
    lst = [3, 4, 1, 7, 9, 1]
    cumulativeSum(lst) 
```

**输出:**

```py
[3, 7, 8, 15, 24, 25]
```