# Python–删除重复子集元组

> 原文:[https://www . geesforgeks . org/python-remove-replica-subset-元组/](https://www.geeksforgeeks.org/python-remove-duplicate-subset-tuples/)

有时，在使用 Python 元组时，我们可能会遇到一个问题，即我们需要执行元组的移除，而元组已经作为子集存在于其他元组中。这类问题可用于数据预处理。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [(6，9，17，18)，(15，34，56)，(6，7，10)，(6，7)，(6，9)，(15，34)]，K = 2
> **输出** : [(6，9，17，18)，(15，34，56)，(6，7，10)]
> 
> **输入** : test_list = [(6，9，17，18)，(15，34，56)，(6，7，10)]，K = 2
> **输出** : [(6，9，17，18)，(15，34，56)，(6，7，10)]

**方法一:使用`setdefault()` +列表理解**
这是解决这个任务的方法之一。在这种情况下，我们执行初始化列表和保存要比较的元素的任务。最后，利用列表理解进行子集元组的移除。这种方法为移除元组的大小提供了灵活性。

```py
# Python3 code to demonstrate working of 
# Remove Duplicate subset Tuples
# Using setdefault() + list comprehension

# initializing lists
test_list = [(6, 9, 17, 18), (15, 34, 56), (6, 7), (6, 9), (15, 34)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 2

# Remove Duplicate subset Tuples
# Using setdefault() + list comprehension
temp = {}
for sub in test_list:
    temp2 = sub[:K]
    temp.setdefault(temp2, []).append(sub)
res = [sub for sub in test_list if len(sub) > K or len(temp[sub]) == 1]

# printing result 
print("Tuple list after removal : " + str(res)) 
```

**Output :**

```py
The original list is : [(6, 9, 17, 18), (15, 34, 56), (6, 7), (6, 9), (15, 34)]
Tuple list after removal : [(6, 9, 17, 18), (15, 34, 56), (6, 7)]

```

**方法 2:使用`all() + any()` +循环**
上述功能的组合提供了解决这个问题的另一种方法。在这种情况下，我们测试所有子集，无论大小。any()函数用于检查在使用 all()提取的特定元组的所有元素中，是否有任何元组是新的。

```py
# Python3 code to demonstrate working of 
# Remove Duplicate subset Tuples
# Using all() + any()+ loop

# initializing lists
test_list = [(6, 9, 17, 18), (15, 34, 56), (6, 7), (6, 9), (15, 34)]

# printing original list
print("The original list is : " + str(test_list))

# Remove Duplicate subset Tuples
# Using all() + any() + loop
res = []
test_list = sorted(test_list, key = lambda x: len(x))
for idx, sub in enumerate(test_list):
    if any(all(ele in sub2 for ele in sub) for sub2 in test_list[idx + 1:]):
        pass 
    else:
        res.append(sub)

# printing result 
print("Tuple list after removal : " + str(res)) 
```

**Output :**

```py
The original list is : [(6, 9, 17, 18), (15, 34, 56), (6, 7), (6, 9), (15, 34)]
Tuple list after removal : [(6, 9, 17, 18), (15, 34, 56), (6, 7)]

```