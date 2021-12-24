# Python–字典中键的唯一值

> 原文:[https://www . geesforgeks . org/python-字典中唯一键值/](https://www.geeksforgeeks.org/python-unique-values-of-key-in-dictionary/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即需要提取字典列表中特定键的唯一值。这种问题在日常编程和 web 开发领域非常常见。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [{ '极客':10，' for': 8，' best': 10}，{'best': 10}]
> **输出**:【10】
> 
> **输入**:test _ list =[{ ' best ':11 }]
> **输出**:【11】

**方法#1:使用 loop + `set()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们在循环中提取关键字的所有元素，然后将提取的列表转换为集合，以获得唯一的值。

```py
# Python3 code to demonstrate working of 
# Unique Values of Key in Dictionary
# Using loop + set()

# initializing list
test_list = [{'Gfg' : 5, 'is' : 6, 'best' : 7, 'for' : 8, 'geeks' : 10},
             {'Gfg' : 9, 'is' : 4, 'best' : 7, 'for' : 4, 'geeks' :7},
             {'Gfg' : 2, 'is' : 10, 'best' : 8, 'for' : 9, 'geeks' : 3}]

# printing original list
print("The original list is : " + str(test_list))

# initializing key
op_key = 'best'

# Unique Values of Key in Dictionary
# Using loop + set()
res = []
for sub in test_list:
    res.append(sub[op_key])
res = list(set(res))

# printing result 
print("The unique values of key : " + str(res)) 
```

**Output :**

> 原始列表为:[{'for': 8，' best': 7，' is': 6，' Gfg': 5，'极客':10}，{'for': 4，' best': 7，' is': 4，' Gfg': 9，'极客':7}，{'for': 9，' best': 8，' is': 10，' Gfg': 2，'极客':3 }]
> key 的唯一值:[8，7]

**方法 2:使用列表理解**
这是解决这个问题的又一种方法。在这种情况下，我们以与上述方法类似的方式执行，但采用速记方式。

```py
# Python3 code to demonstrate working of 
# Unique Values of Key in Dictionary
# Using list comprehension

# initializing list
test_list = [{'Gfg' : 5, 'is' : 6, 'best' : 7, 'for' : 8, 'geeks' : 10},
             {'Gfg' : 9, 'is' : 4, 'best' : 7, 'for' : 4, 'geeks' :7},
             {'Gfg' : 2, 'is' : 10, 'best' : 8, 'for' : 9, 'geeks' : 3}]

# printing original list
print("The original list is : " + str(test_list))

# initializing key
op_key = 'best'

# Unique Values of Key in Dictionary
# Using list comprehension
res = list(set(sub[op_key] for sub in test_list)) 

# printing result 
print("The unique values of key : " + str(res)) 
```

**Output :**

> 原始列表为:[{'for': 8，' best': 7，' is': 6，' Gfg': 5，'极客':10}，{'for': 4，' best': 7，' is': 4，' Gfg': 9，'极客':7}，{'for': 9，' best': 8，' is': 10，' Gfg': 2，'极客':3 }]
> key 的唯一值:[8，7]