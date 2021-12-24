# Python–删除不需要的键关联

> 原文:[https://www . geeksforgeeks . org/python-remove-不需要的-key-associations/](https://www.geeksforgeeks.org/python-remove-unwanted-keys-associations/)

有时，在使用 Python 字典时，我们可能会遇到这样的问题，即需要删除一些不需要的键及其相关嵌套。这可以应用于许多领域，包括网络开发和竞争性编程。让我们讨论执行这项任务的某些方法。

> **输入**:test _ dict = { ' best ':{ ' for ':{ ' geeks ':{ ' CS ':{ ' Gfg ':12 } } } } }
> **输出** : {'best': {'for': {}}}
> 
> **输入** : test_dict = {'best' : 14、' gfg' : 13}
> **输出** : {'best' : 14、' gfg' : 13}

**方法一:使用`isinstance()` +循环+递归**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用 isinstance()检查元素值是否是字典或键，并重复构造所有不作为不需要的键出现的键。

```py
# Python3 code to demonstrate working of 
# Remove unwanted Keys associations
# Using isinstance() + loop + recursion

def helper_fnc(test_dict, unw_keys):
    temp = {}
    for key, val in test_dict.items():
        if key in unw_keys:
            continue
        if isinstance(val, dict):
            temp[key] = helper_fnc(val, unw_keys)
        else:
            temp[key] = val
    return temp

# initializing dictionary
test_dict = {"Gfg" : {'is' : 45, 'good' : 15}, 
             'best' : {'for' : {'geeks' :  {'CS' : 12}}}}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing unwanted keys
unw_keys = ['is', 'geeks']

# Remove unwanted Keys associations
# Using isinstance() + loop + recursion
res = helper_fnc(test_dict, unw_keys)

# printing result 
print("The filtered dictionary : " + str(res)) 
```

**Output :**

> 原始词典:{'Gfg': {'is': 45，' good': 15}，' best ':{ ' for ':{ ' geeks ':{ ' CS ':12 } } }
> 筛选后的词典:{'Gfg': {'good': 15}，' best': {'for': {}}