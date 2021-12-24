# Python–嵌套字典子集

> 原文:[https://www . geesforgeks . org/python-嵌套-字典-子集/](https://www.geeksforgeeks.org/python-nested-dictionary-subset/)

给定一个嵌套字典，测试另一个字典是否是子集。

**示例:**

> **输入**:test _ dict = {“gfg”:12、' best' : {1 : 3、4 : 3、' geeks' : {8 : 7}}，sub_dict = {8 : 7}
> **输出** : True
> **解释**:字典中存在的必需嵌套字典。
> 
> **输入**:test _ dict = {“gfg”:12、' best' : {1 : 3、4 : 3、' geeks' : {8 : 7}}，sub_dict = {9 : 7}
> **输出** : False
> **解释**:字典中不存在嵌套字典。

**方法:使用**[**all()**](https://www.geeksforgeeks.org/any-all-in-python/)**+**[**any()**](https://www.geeksforgeeks.org/any-all-in-python/)**+**[T15】is instance()](https://www.geeksforgeeks.org/python-isinstance-method/)**+**[T21】递归](https://www.geeksforgeeks.org/recursion/)

在这种情况下，我们使用函数在每个嵌套处检查子集，并使用 all()检查所有匹配的键，any()用于实用程序测试与测试字典上的测试子集匹配的任何嵌套的可能子集。使用递归测试每个嵌套。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Nested Dictionary Subset Python
# Using all() + any() + isinstance() + recursion

def check_eq(mast_dict, subdict):
    if not isinstance(mast_dict, (dict, list)):
        return mast_dict == subdict
    if isinstance(mast_dict, list):

        # check for nesting dictionaries in list
        return all(check_eq(x, y) for x, y in zip(mast_dict, subdict))

    # check for all keys
    return all(mast_dict.get(idx) == subdict[idx] or check_eq(mast_dict.get(idx), subdict[idx]) for idx in subdict)

def is_subset(mast_dict, subdict):
    if isinstance(mast_dict, list):

        # any matching dictionary in list
        return any(is_subset(idx, subdict) for idx in mast_dict)

    # any matching nested dictionary
    return check_eq(mast_dict, subdict) or (isinstance(mast_dict, dict) and any(is_subset(y, subdict) for y in mast_dict.values()))

# initializing dictionary
test_dict = {"gfg": 12, 'best': {1: 3, 4: 3, 'geeks': {8: 7}}, 'cs': 7}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing subset dict
sub_dict = {8: 7}

# calling func
res = is_subset(test_dict, sub_dict)

# printing result
print("Is dictionary subset : " + str(res))
```

**输出:**

> 原始字典为:{'gfg': 12，' best': {1: 3，4: 3，' geeks': {8: 7}}，' cs': 7}
> 是字典子集:True