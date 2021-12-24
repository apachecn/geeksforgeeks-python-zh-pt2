# Python 程序从其他列表中删除重复元素索引

> 原文:[https://www . geesforgeks . org/python-程序-删除重复元素-从其他列表中索引/](https://www.geeksforgeeks.org/python-program-to-remove-duplicate-elements-index-from-other-list/)

给定两个列表，任务是编写一个 Python 程序，从第二个列表中移除所有索引元素，它们是第一个列表中的重复元素索引。

**示例:**

> **输入** : test_list1 = [3，5，6，5，3，7，8，6]，test_list2 = [1，7，6，3，7，9，10，11]
> **输出** : [1，7，6，9，10]
> **解释** : 3，7，11 对应于 5，3，6 的第二次出现，因此被删除。
> 
> **输入** : test_list1 = [3，5，6，5，3，7，8]，test_list2 = [1，7，6，3，7，9，10]
> **输出** : [1，7，6，9，10]
> **解释** : 3 和 7 对应于 5 和 3 的第二次出现，因此被移除。

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/) **+** [**循环**](https://www.geeksforgeeks.org/loops-in-python/) **+** [**枚举()**](https://www.geeksforgeeks.org/enumerate-in-python/)

在本例中，我们使用 enumerate()执行获取所有索引的任务，并使用 set 循环存储已经发生的元素。然后，省略其他列表中的相同索引。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove duplicate elements index from other list
# Using list comprehension + loop + enumerate()

# initializing lists
test_list1 = [3, 5, 6, 5, 3, 7, 8, 6]
test_list2 = [1, 7, 6, 3, 7, 9, 10, 11]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

oc_set = set() 
temp = [] 

# getting duplicate elements list
for idx, val in enumerate(test_list1): 
    if val not in oc_set: 
        oc_set.add(val)          
    else: 
        temp.append(idx)

# excluding duplicate indices from other list
res = [ele for idx, ele in enumerate(test_list2) if idx not in temp]

# printing result
print("The list after removing duplicate indices : " + str(res))
```

**输出:**

```py
The original list 1 is : [3, 5, 6, 5, 3, 7, 8, 6]
The original list 2 is : [1, 7, 6, 3, 7, 9, 10, 11]
The list after removing duplicate indices : [1, 7, 6, 9, 10]
```

**方法二:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/) **+** [**枚举()**](https://www.geeksforgeeks.org/enumerate-in-python/)

在这种情况下，我们以一种简单的方式执行与上面类似的任务，使用 enumerate()和列表理解提取索引。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove duplicate elements index from other list
# Using list comprehension + enumerate()

# initializing lists
test_list1 = [3, 5, 6, 5, 3, 7, 8, 6]
test_list2 = [1, 7, 6, 3, 7, 9, 10, 11]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# getting duplicate elements list using list comprehension
temp = [idx for idx, val in enumerate(test_list1) if val in test_list1[:idx]]

# excluding duplicate indices from other list
res = [ele for idx, ele in enumerate(test_list2) if idx not in temp]

# printing result
print("The list after removing duplicate indices : " + str(res))
```

**输出:**

```py
The original list 1 is : [3, 5, 6, 5, 3, 7, 8, 6]
The original list 2 is : [1, 7, 6, 3, 7, 9, 10, 11]
The list after removing duplicate indices : [1, 7, 6, 9, 10]
```