# Python–按总位数排序元组

> 原文:[https://www . geesforgeks . org/python-按总位数排序元组/](https://www.geeksforgeeks.org/python-sort-tuples-by-total-digits/)

给定元组列表，根据元组中的总位数执行排序。

**示例:**

> **输入** : test_list = [(3，4，6，723)，(1，2)，(134，234，34)]
> **输出** : [(1，2)，(3，4，6，723)，(134，234，34)]
> **解释** : 2 < 6 < 8，按总位数递增排序。
> 
> **输入** : test_list = [(1，2)，(134，234，34)]
> **输出** : [(1，2)，(134，234，34)]
> **解释** : 2 < 8，按总位数递增排序。

**方法#1:使用 sort()+**[**len()**](https://www.geeksforgeeks.org/python-string-length-len/)**+**[**sum()**](https://www.geeksforgeeks.org/sum-function-python/)

在这种情况下，我们通过字符串转换和 len()得到元组中每个元素的所有长度的总和。然后 sort()与 key 一起使用来解决这个问题。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sort Tuples by Total digits
# Using sort() + len() + sum()

def count_digs(tup):

    # gets total digits in tuples
    return sum([len(str(ele)) for ele in tup ])

# initializing list
test_list = [(3, 4, 6, 723), (1, 2), (12345,), (134, 234, 34)]

# printing original list
print("The original list is : " + str(test_list))

# performing sort 
test_list.sort(key = count_digs)

# printing result 
print("Sorted tuples : " + str(test_list))
```

**Output**

```py
The original list is : [(3, 4, 6, 723), (1, 2), (12345,), (134, 234, 34)]
Sorted tuples : [(1, 2), (12345,), (3, 4, 6, 723), (134, 234, 34)]

```

**方法 2:使用排序的()+λ+sum()+len()**

在本文中，我们使用 sorted()执行排序任务，lambda 函数执行元组中总位数的计算任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sort Tuples by Total digits
# Using sorted() + lambda + sum() + len()

# initializing list
test_list = [(3, 4, 6, 723), (1, 2), (12345,), (134, 234, 34)]

# printing original list
print("The original list is : " + str(test_list))

# performing sort, lambda function provides logic
res = sorted(test_list, key = lambda tup : sum([len(str(ele)) for ele in tup ]))

# printing result 
print("Sorted tuples : " + str(res))
```

**Output**

```py
The original list is : [(3, 4, 6, 723), (1, 2), (12345,), (134, 234, 34)]
Sorted tuples : [(1, 2), (12345,), (3, 4, 6, 723), (134, 234, 34)]

```