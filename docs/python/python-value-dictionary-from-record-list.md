# Python–记录列表中的值字典

> 原文:[https://www . geesforgeks . org/python-value-dictionary-from-record-list/](https://www.geeksforgeeks.org/python-value-dictionary-from-record-list/)

有时，在使用 Python Records 列表时，我们可能会遇到这样的问题，即我们需要仅采用二进制字典的值来改革字典。这可以在许多处理数据的领域中得到应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `values() + update()`**
以上功能的组合可以用来执行这个任务。在这种情况下，使用 values()提取值，并使用 update()更新新字典。

```py
# Python3 code to demonstrate working of 
# Value Dictionary from Record List
# Using loop + values() + update()

# initializing list
test_list = [{1 : 'gfg', 2 : 'best'}, {3 : 'for', 4 : 'geeks'}]

# printing original list
print("The original list is : " + str(test_list))

# Value Dictionary from Record List
# Using loop + values() + update()
res = dict()
for sub in test_list:
    res.update((sub.values(), ))

# printing result 
print("The values dictionary is : " + str(dict(res))) 
```

**Output :**

> 原始列表为:[{1: 'gfg '，2: 'best'}，{3: 'for '，4: 'geeks'}]
> 值字典为:{'gfg': 'best '，' for': 'geeks'}