# Python–替换非最大记录

> 原文:[https://www . geesforgeks . org/python-replace-non-maximum-records/](https://www.geeksforgeeks.org/python-replace-non-maximum-records/)

有时，在使用 Python 记录时，我们可能会遇到一个问题，即我们需要替换一个元素不是最大值的所有记录。这类问题可以应用于许多领域，包括日常编程和 web 开发领域。让我们讨论执行这项任务的某些方法。

> **输入** :
> 测试 _ 列表= [(1，4)，(9，11)]
> K =“非最大”
> **输出**:[‘非最大’，(9，11)]
> 
> **输入** :
> 测试 _ 列表= [(9，11)，(9，11)，(9，11)]
> K =“非最大”
> **输出** : [(9，11)，(9，11)，(9，11)]

**方法#1:使用 loop + `map() + filter()` + lambda**
上述功能的组合可用于执行该任务。在这种情况下，我们使用 map()和 filter 函数执行过滤任务，然后使用循环将值分配给非最大值元素。

```py
# Python3 code to demonstrate working of 
# Replace Non-Maximum Records
# Using loop + map() + filter() + lambda

# initializing list
test_list = [(1, 4), (9, 11), (4, 6), (6, 8), (9, 11)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = None 

# Replace Non-Maximum Records
# Using loop + map() + filter() + lambda
res = []
temp = list(filter(lambda ele: ele == max(test_list), test_list))
for ele in test_list:
    if ele not in temp:
        res.append(K)
    else :
        res.append(ele)

# printing result 
print("The list after replacing Non-Maximum : " + str(res)) 
```

**Output :**

```py
The original list is : [(1, 4), (9, 11), (4, 6), (6, 8), (9, 11)]
The list after replacing Non-Maximum : [None, (9, 11), None, None, (9, 11)]

```

**方法 2:使用列表理解+ `map() + filter() + lambda`**
以上功能的组合可以用来执行这个任务。在这种情况下，我们使用与上述类似的方法执行任务，不同的是使用列表理解来分配 k。

```py
# Python3 code to demonstrate working of 
# Replace Non-Maximum Records
# Using list comprehension + map() + filter() + lambda

# initializing list
test_list = [(1, 4), (9, 11), (4, 6), (6, 8), (9, 11)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = None 

# Replace Non-Maximum Records
# Using list comprehension + map() + filter() + lambda
temp = list(filter(lambda ele: ele == max(test_list), test_list))
res = [ele if ele in temp else K for ele in test_list]

# printing result 
print("The list after replacing Non-Maximum : " + str(res)) 
```

**Output :**

```py
The original list is : [(1, 4), (9, 11), (4, 6), (6, 8), (9, 11)]
The list after replacing Non-Maximum : [None, (9, 11), None, None, (9, 11)]

```