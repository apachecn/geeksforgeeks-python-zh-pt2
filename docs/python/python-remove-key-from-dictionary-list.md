# Python–从字典列表中删除关键字

> 原文:[https://www . geesforgeks . org/python-从字典列表中移除密钥/](https://www.geeksforgeeks.org/python-remove-key-from-dictionary-list/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，需要从字典列表中移除特定的键。这种问题非常普遍，几乎在所有领域都有应用，包括日常编程和 web 开发领域。让我们讨论执行这项任务的某些方法。
**方法#1:使用 loop + del**
以上功能的组合可以用来解决这个问题。在这种情况下，我们迭代所有的键，并使用 del 从每个字典中删除所需的键。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove Key from Dictionary List
# Using loop + del

# initializing list
test_list = [{'Gfg' :  1, 'id' : 2, 'best' : 8 },
             {'Gfg' :  4, 'id' : 4, 'best':  10},
             {'Gfg' :  4, 'id' : 8, 'best':  11}]

# printing original list
print("The original list is : " + str(test_list))

# initializing key
del_key = 'id'

# Remove Key from Dictionary List
# Using loop + del
for items in test_list:
    if del_key in items:
        del items[del_key]

# printing result
print("The modified list : " + str(test_list))
```

**Output : **

```py
The original list is : [{'best': 8, 'id': 2, 'Gfg': 1}, {'best': 10, 'id': 4, 'Gfg': 4}, {'best': 11, 'id': 8, 'Gfg': 4}]
The modified list : [{'best': 8, 'Gfg': 1}, {'best': 10, 'Gfg': 4}, {'best': 11, 'Gfg': 4}]
```

**方法 2:使用列表理解+词典理解**
这是执行这个任务的又一种方式。在这种情况下，我们重构每个字典，去掉其中的特定键。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove Key from Dictionary List
# Using list comprehension + dictionary comprehension

# initializing list
test_list = [{'Gfg' :  1, 'id' : 2, 'best' : 8 },
             {'Gfg' :  4, 'id' : 4, 'best':  10},
             {'Gfg' :  4, 'id' : 8, 'best':  11}]

# printing original list
print("The original list is : " + str(test_list))

# initializing key
del_key = 'id'

# Remove Key from Dictionary List
# Using list comprehension + dictionary comprehension
res = [{key : val for key, val in sub.items() if key != del_key} for sub in test_list]

# printing result
print("The modified list : " + str(res))
```

**Output : **

```py
The original list is : [{'best': 8, 'id': 2, 'Gfg': 1}, {'best': 10, 'id': 4, 'Gfg': 4}, {'best': 11, 'id': 8, 'Gfg': 4}]
The modified list : [{'best': 8, 'Gfg': 1}, {'best': 10, 'Gfg': 4}, {'best': 11, 'Gfg': 4}]
```