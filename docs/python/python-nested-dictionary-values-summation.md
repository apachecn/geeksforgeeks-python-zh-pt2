# Python–嵌套字典值求和

> 原文:[https://www . geesforgeks . org/python-嵌套-字典-值-求和/](https://www.geeksforgeeks.org/python-nested-dictionary-values-summation/)

有时，在使用 Python 字典时，我们可能会遇到嵌套记录的问题，我们需要对其键值进行累积求和。这可能会在 web 开发和竞争性编程等领域得到应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `items() + values()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们迭代使用 values()提取的所有值，并执行求和任务。

```
# Python3 code to demonstrate working of 
# Nested Dictionary values summation
# Using loop + items() + values()

# initializing dictionary
test_dict = {'gfg' : {'a' : 4, 'b' : 5, 'c' : 8},
             'is' : {'a' : 8, 'c' : 10},
             'best' : {'c' : 19, 'b' : 10}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Nested Dictionary values summation
# Using loop + items() + values()
res = dict()
for sub in test_dict.values():
    for key, ele in sub.items():
        res[key] = ele + res.get(key, 0)

# printing result 
print("The summation dictionary is : " + str(res)) 
```

**Output :**

> 原始字典为:{'gfg': {'a': 4，' b': 5，' c': 8}，' best': {'b': 10，' c': 19}，' is': {'a': 8，' c': 10}}
> 求和字典为:{'a': 12，' b': 15，' c': 37}