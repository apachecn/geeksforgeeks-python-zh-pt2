# Python–从字典中移除不相交的元组键

> 原文:[https://www . geeksforgeeks . org/python-remove-disjoint-tuple-key-from-dictionary/](https://www.geeksforgeeks.org/python-remove-disjoint-tuple-keys-from-dictionary/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要根据与其他列表中的任何一个元素存在键相匹配的键存在，从记录中移除元组键。这种问题在数据领域也有应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_dict = {(9，3) : 4，(' is '，6) : 2，(' for '，9) : 'geeks'}
> **输出** : {}
> 
> **输入** : test_dict = {('is '，9): 2，(' for '，8): 7}
> **输出** : {('for '，8): 7}

**方法 1:使用循环**
这是执行该任务的方式之一。在这种情况下，我们执行字典键的迭代，检查是否存在任何需要的键，并相应地执行删除。

```
# Python3 code to demonstrate working of 
# Remove Disjoint Tuple keys from Dictionary
# Using loop

# initializing dictionary
test_dict = {('Gfg', 3) : 4, ('is', 6) : 2, ('best', 10) : 3, ('for', 9) : 'geeks'}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing List 
rem_list = [9, 'is']

# Remove Disjoint Tuple keys from Dictionary
# Using loop
res = dict()
for idx in test_dict:
    if idx[0] not in rem_list and idx[1] not in rem_list:
        res[idx] = test_dict[idx]

# printing result 
print("Dictionary after removal : " + str(res)) 
```

**Output :**

> 原词典:{('Gfg '，3): 4，(' best '，10): 3，(' for '，9): 'geeks '，(' is '，6): 2}
> 词典删除后:{('Gfg '，3): 4，(' best '，10): 3}

**方法 2:使用`set() + dictionary comprehension + isdisjoint()`**
以上功能的组合也可以用来解决这个问题。在本文中，我们使用 isdisjoint()执行比较任务。

```
# Python3 code to demonstrate working of 
# Remove Disjoint Tuple keys from Dictionary
# Using set() + dictionary comprehension + isdisjoint()

# initializing dictionary
test_dict = {('Gfg', 3) : 4, ('is', 6) : 2, ('best', 10) : 3, ('for', 9) : 'geeks'}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing List 
rem_list = [9, 'is']

# Remove Disjoint Tuple keys from Dictionary
# Using set() + dictionary comprehension + isdisjoint()
res = {keys: val for keys, val in test_dict.items() if set(keys).isdisjoint(rem_list)}

# printing result 
print("Dictionary after removal : " + str(res)) 
```

**Output :**

> 原词典:{('Gfg '，3): 4，(' best '，10): 3，(' for '，9): 'geeks '，(' is '，6): 2}
> 词典删除后:{('Gfg '，3): 4，(' best '，10): 3}