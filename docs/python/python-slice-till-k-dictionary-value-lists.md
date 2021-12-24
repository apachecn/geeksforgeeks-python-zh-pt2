# Python–切片直到 K 字典值列表

> 原文:[https://www . geesforgeks . org/python-slice-till-k-dictionary-value-list/](https://www.geeksforgeeks.org/python-slice-till-k-dictionary-value-lists/)

给定以值为列表的字典，将每个列表切割到 k

> **输入**:test _ dict = {“Gfg”:[1，6，3，5，7]，“Best”:[5，4，2，8，9]，“is”:[4，6，8，4，2]}，K = 3
> **输出**:{“Gfg”:[1，6，3]，“Best”:[5，4，2]，“is”:[4，6，8]}
> **解释**:提取的 3 长度字典值
> 
> **输入**:test _ dict = {“Gfg”:[1，6，3，5，7]，“Best”:[5，4，2，8，9]，“is”:[4，6，8，4，2]}，K = 2
> **输出**:{“Gfg”:[1，6]，“Best”:[5，4]，“is”:[4，6]}
> **解释**:提取的 2 长度字典值列表。

**方法#1:使用循环+列表切片**

上述功能的组合可以用来解决这个问题。在这种情况下，我们使用切片操作执行列表切片任务，并循环遍历所有键。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Slice till K dictionary value lists
# Using loop + list slicing 

# initializing dictionary
test_dict = {"Gfg" : [1, 6, 3, 5, 7], 
             "Best" : [5, 4, 2, 8, 9],
             "is" : [4, 6, 8, 4, 2]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = 4

res = dict()
for sub in test_dict:

    # slicing till K and reassigning
    res[sub] = test_dict[sub][:K]

# printing result 
print("The dictionary after conversion " + str(res)) 
```

**Output**

> 原字典为:{'Gfg': [1，6，3，5，7]，' Best': [5，4，2，8，9]，' is': [4，6，8，4，2]}
> 转换后的字典为{'Gfg': [1，6，3，5]，' Best': [5，4，2，8]，' is': [4，6，8，4]}

**方法二:使用词典理解+列表切片**

这是执行这项任务的另一种方式。在本文中，我们使用字典理解来执行重新分配任务，并提供了一种线性方法来解决这个问题。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Slice till K dictionary value lists
# Using dictionary comprehension + list slicing

# initializing dictionary
test_dict = {"Gfg" : [1, 6, 3, 5, 7],
             "Best" : [5, 4, 2, 8, 9], 
             "is" : [4, 6, 8, 4, 2]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = 4

# one-liner to slice elements of list 
# items() used to get all key-value pair of dictionary
res = {key: val[:K] for key, val in test_dict.items()}

# printing result 
print("The dictionary after conversion " + str(res)) 
```

**Output**

> 原字典为:{'Gfg': [1，6，3，5，7]，' Best': [5，4，2，8，9]，' is': [4，6，8，4，2]}
> 转换后的字典为{'Gfg': [1，6，3，5]，' Best': [5，4，2，8]，' is': [4，6，8，4]}