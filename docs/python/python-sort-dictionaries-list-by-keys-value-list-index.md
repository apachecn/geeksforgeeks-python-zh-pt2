# Python–根据键的值列表索引对字典列表进行排序

> 原文:[https://www . geesforgeks . org/python-sort-dictionary-list-by-key-value-list-index/](https://www.geeksforgeeks.org/python-sort-dictionaries-list-by-keys-value-list-index/)

给定字典列表，根据关键字的索引值对字典进行排序。

> **输入**:[{“Gfg”:[6，7，8]，“是”:9，“最佳”:10}，
> {“Gfg”:[2，0，3]，“是”:11，“最佳”:19}，
> {“Gfg”:[4，6，9]，“是”:16，“最佳”:1}]，K =“Gfg”，idx = 0
> **输出**:[{“Gfg”:[2，0，3]，“是”:
> 
> **输入**:[{“Gfg”:[6，7，8]，“是”:9，“最佳”:10}，
> {“Gfg”:[2，0，3]，“是”:11，“最佳”:19}，
> {“Gfg”:[4，6，9]，“是”:16，“最佳”:1}]，K =“Gfg”，idx = 1
> **输出**:[{“Gfg”:[2，0，3]，“是”:

**方法#1:使用排序的()+λ**

上述功能的组合可以用来解决这个问题。在这种情况下，我们使用排序来执行排序，lambda 函数中提供了基于列表索引的逻辑。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sort dictionaries list by Key's Value list index
# Using sorted() + lambda

# initializing lists
test_list = [{"Gfg" : [6, 7, 8], "is" : 9, "best" : 10}, 
             {"Gfg" : [2, 0, 3], "is" : 11, "best" : 19},
             {"Gfg" : [4, 6, 9], "is" : 16, "best" : 1}]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = "Gfg"

# initializing idx 
idx = 2

# using sorted() to perform sort in basis of 1 parameter key and 
# index
res = sorted(test_list, key = lambda ele: ele[K][idx])

# printing result 
print("The required sort order : " + str(res))
```

**Output**

> 原始列表:[{'Gfg': [6，7，8]，' is': 9，' best': 10}，{'Gfg': [2，0，3]，' is': 11，' best': 19}，{'Gfg': [4，6，9]，' is': 16，' best': 1}]
> 所需的排序顺序:[{'Gfg': [2，0，3]，' is': 11，' best': 19}，{'Gfg': [6，7，8]，'

**方法 2:使用排序的()+ lambda(平局情况下的附加参数)**

这是对值排序的修改，如果列表中的值相同，则添加另一个参数。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sort dictionaries list by Key's Value list index
# Using sorted() + lambda (Additional parameter in case of tie)

# initializing lists
test_list = [{"Gfg" : [6, 7, 9], "is" : 9, "best" : 10}, 
             {"Gfg" : [2, 0, 3], "is" : 11, "best" : 19},
             {"Gfg" : [4, 6, 9], "is" : 16, "best" : 1}]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = "Gfg"

# initializing idx 
idx = 2

# initializing K2 
K2 = "best"

# using sorted() to perform sort in basis of 2 parameter key
# inner is evaluated after the outer key in lambda order
res = sorted(sorted(test_list, key = lambda ele: ele[K2]), key = lambda ele: ele[K][idx])

# printing result 
print("The required sort order : " + str(res))
```

**Output**

> 原始列表:[{'Gfg': [6，7，9]，' is': 9，' best': 10}，{'Gfg': [2，0，3]，' is': 11，' best': 19}，{'Gfg': [4，6，9]，' is': 16，' best': 1}]
> 所需的排序顺序:[{'Gfg': [2，0，3]，' is': 11，' best': 19}，{'Gfg': [4，6，9]，'