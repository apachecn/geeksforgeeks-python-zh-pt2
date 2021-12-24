# Python–非嵌套单键嵌套字典列表

> 原文:[https://www . geesforgeks . org/python-unnest-单键-嵌套-字典-列表/](https://www.geeksforgeeks.org/python-unnest-single-key-nested-dictionary-list/)

有时，在使用 Python 数据时，我们会遇到一个问题，即我们需要对所有具有单个键嵌套的字典执行不必要的操作，即单个键和值，并且可以很容易地直接指向外部键。这种问题在需要数据优化的领域很常见。让我们讨论执行这项任务的某些方法。

> **输入**:test _ list =[{ ' gfg ':{ ' data ':1 } }，{'is' : {'data' : 5，'极客':7}}]
> **输出** : {'is': 5，' gfg': 1}
> 
> **输入**:test _ list =[{ ' gfg ':{ ' data ':' best ' } }]
> **输出** : {'gfg': 'best'}

**方法#1:使用 loop + `items()`**
以上方法的组合可以用来解决这个问题。在本文中，我们使用循环对列表中的值进行迭代，并使用 items()提取所有字典项，并使用蛮力方法执行新字典的创建。

```
# Python3 code to demonstrate working of 
# Unnest single Key Nested Dictionary List
# Using loop + items()

# initializing list
test_list = [{'gfg' : {'data' : 1}}, {'is' : {'data' : 5}}, {'best' : {'data' : 4}}]

# printing original list
print("The original list is : " + str(test_list))

# initializing key 
data_key = 'data'

# Unnest single Key Nested Dictionary List
# Using loop + items()
res = dict()
for sub in test_list:
    for key, val in sub.items():
        res[key] = sub[key][data_key]

# printing result 
print("The constructed Dictionary list : " + str(res)) 
```

**Output :**

> 原始列表为:[{'gfg': {'data': 1}}，{'is': {'data': 5}}，{'best': {'data': 4}}]
> 构造的字典列表为:{'gfg': 1，' best': 4，' is': 5}

**方法 2:使用列表理解**
这是另一种可以执行该任务的方式。在这种情况下，我们使用类似的方法来执行解决方案，但使用列表理解的速记方式。

```
# Python3 code to demonstrate working of 
# Unnest single Key Nested Dictionary List
# Using list comprehension

# initializing list
test_list = [{'gfg' : {'data' : 1}}, {'is' : {'data' : 5}}, {'best' : {'data' : 4}}]

# printing original list
print("The original list is : " + str(test_list))

# initializing key 
data_key = 'data'

# Unnest single Key Nested Dictionary List
# Using list comprehension
res = {x : y[data_key] for idx in test_list for x, y in idx.items()}

# printing result 
print("The constructed Dictionary list : " + str(res)) 
```

**Output :**

> 原始列表为:[{'gfg': {'data': 1}}，{'is': {'data': 5}}，{'best': {'data': 4}}]
> 构造的字典列表为:{'gfg': 1，' best': 4，' is': 5}