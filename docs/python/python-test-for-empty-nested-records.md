# Python–测试空嵌套记录

> 原文:[https://www . geesforgeks . org/python-空嵌套记录测试/](https://www.geeksforgeeks.org/python-test-for-empty-nested-records/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要测试特定字典是否有嵌套记录，并且它们都是空的，即在列表的情况下没有键或没有值。这种问题在数据科学等数据领域非常普遍。
我们来讨论一下执行这个任务的特定方式。

> **输入** : test_dict = {'Gfg': []，'极客':{ }
> **输出**:真
> 
> **输入** : test_dict = {'Gfg': 4}
> 输出 : False

**方法#1:使用递归+ `all() + isinstance()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 all()检查所有嵌套，并使用 isinstance()测试字典或列表。

```
# Python3 code to demonstrate working of 
# Test for empty Nested Records
# Using recursion + all() + isinstance

# Helper function
def hlper_fnc(test_dict):
    if isinstance(test_dict, dict):
        return all(hlper_fnc(sub) for _, sub in test_dict.items())
    if isinstance(test_dict, list):
        return all(hlper_fnc(sub) for sub in test_dict)
    return False

# initializing dictionary
test_dict = {'Gfg': [], 'is': { 'best': [], 'for': {} }, 'geeks': {}}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Test for empty Nested Records
# Using recursion + all() + isinstance
res = hlper_fnc(test_dict)

# printing result 
print("Is dictionary without data ? : " + str(res)) 
```

**Output :**

> 原词典:{'is': {'best': []，' for': {}，' geeks': {}，' Gfg': []}
> 是没有数据的词典吗？:真