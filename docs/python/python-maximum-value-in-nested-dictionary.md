# Python–嵌套字典中的最大值

> 原文:[https://www . geesforgeks . org/python-嵌套字典中的最大值/](https://www.geeksforgeeks.org/python-maximum-value-in-nested-dictionary/)

有时，在使用 python 字典时，我们会遇到这样的问题，即每个键本身都是一个记录，有几个键，我们希望将该值替换为字典键的最大值。这种问题可以应用于许多涉及数据的领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是一种可以执行该任务的暴力方式。在这种情况下，我们对每个键的键进行迭代，以获得最大值并将其设置在结果字典中。

```
# Python3 code to demonstrate working of 
# Maximum Value in Nested Dictionary
# Using loop

# initializing dictionary
test_dict = {'gfg' : {'a' : 15, 'b' : 14},
             'is' : {'d' : 2, 'e' : 10, 'f' :  3},
             'best' : {'g' : 19}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Maximum Value in Nested Dictionary
# Using loop
res = {}
for key, val in test_dict.items():
    max_val = 0
    for ele in val.values():
        if ele > max_val:
            max_val = ele
    res[key] = max_val

# printing result 
print("The modified dictionary : " + str(res)) 
```

**Output :**

> 原词典为:{'is': {'f': 3，' e': 10，' d': 2}，' gfg': {'a': 15，' b': 14}，' best': {'g': 19}}
> 修改后的词典:{'best': 19，' is': 10，' gfg': 15}