# Python–未列出的单值字典列表

> 原文:[https://www . geesforgeks . org/python-unlist-单值-dictionary-list/](https://www.geeksforgeeks.org/python-unlist-single-valued-dictionary-list/)

给定字典列表，执行记录的取消列表，其中我们只有一个字典作为记录元素。

> **输入**:test _ list =[{ ' best ':[{ ' a ':6 }]，' Gfg': 15}]
> **输出** : [{'best': {'a': 6}，' Gfg': 15}]
> **说明:**与' best '键关联的值列表改为字典。
> 
> **输入**:test _ list =[{ ' Gfg ':[{ ' best ':17 }]}]
> **输出**:[{ ' Gfg ':{ ' best ':17 } }]
> **解释:** : 'Gfg '键的值改为单字典。

**方法#1:使用 loop + isinstance()**
这是可以执行此任务的蛮力方式。在本例中，我们使用 isinstance()测试列表类型，循环用于迭代。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Unlist Single Valued Dictionary List
# Using loop + isinstance()

# initializing list
test_list = [{'Gfg': 1,
            'is': [{'a': 2, 'b': 3}]},
            {'best': [{'c': 4, 'd': 5}],
             'CS': 6}]

# printing original list
print("The original list is : " + str(test_list))

# Using loop + isinstance()
for dicts in test_list:
    for key, val in dicts.items():

        # isinstance() is used to check for list to convert
        if isinstance(val, list):
            dicts[key] = val[0]

# printing result
print("The converted Dictionary list : " + str(test_list))
```

**Output : **

```
The original list is : [{'Gfg': 1, 'is': [{'b': 3, 'a': 2}]}, {'CS': 6, 'best': [{'d': 5, 'c': 4}]}]
The converted Dictionary list : [{'Gfg': 1, 'is': {'b': 3, 'a': 2}}, {'CS': 6, 'best': {'d': 5, 'c': 4}}]
```

**方法 2:使用列表理解+ isinstance()**
以上功能的组合可以用来解决问题。在这种情况下，我们用类似于上述方法的短手方法执行类似的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Unlist Single Valued Dictionary List
# Using list comprehension + isinstance()

# initializing list
test_list = [{'Gfg': 1,
            'is': [{'a': 2, 'b': 3}]},
            {'best': [{'c': 4, 'd': 5}],
             'CS': 6}]

# printing original list
print("The original list is : " + str(test_list))

# Using list comprehension + isinstance()
# Similar way as above, extracting first element of list
res = [{key: val[0] if isinstance(val, list) else val
        for key, val in sub.items()}
        for sub in test_list]

# printing result
print("The converted Dictionary list : " + str(res))
```

**Output : **

```
The original list is : [{'Gfg': 1, 'is': [{'b': 3, 'a': 2}]}, {'CS': 6, 'best': [{'d': 5, 'c': 4}]}]
The converted Dictionary list : [{'Gfg': 1, 'is': {'b': 3, 'a': 2}}, {'CS': 6, 'best': {'d': 5, 'c': 4}}]
```