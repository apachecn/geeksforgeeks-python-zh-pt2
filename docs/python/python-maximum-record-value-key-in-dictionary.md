# Python–字典中的最大记录值关键字

> 原文:[https://www . geesforgeks . org/python-最大记录值-字典中的键/](https://www.geeksforgeeks.org/python-maximum-record-value-key-in-dictionary/)

有时，在处理字典记录时，我们可能会遇到这样的问题:我们需要找到列表中嵌套记录的特定键的最大值的键。这可以应用于诸如网络开发和机器学习等领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方式。在这种情况下，我们遍历键的每个键，并分配给 max，即嵌套记录中所需键的最大值。

```py
# Python3 code to demonstrate working of 
# Maximum record value key in dictionary
# Using loop

# initializing dictionary
test_dict = {'gfg' : {'Manjeet' : 5, 'Himani' : 10},
             'is' : {'Manjeet' : 8, 'Himani' : 9},
             'best' : {'Manjeet' : 10, 'Himani' : 15}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing search key
key = 'Himani'

# Maximum record value key in dictionary
# Using loop
res = None
res_max = 0
for sub in test_dict:
    if test_dict[sub][key] > res_max:
        res_max = test_dict[sub][key]
        res = sub

# printing result 
print("The required key is : " + str(res)) 
```

**Output :**

> 原词典为:{'best': {'Himani': 15，' Manjeet': 10}，' gfg': {'Himani': 10，' Manjeet': 5}，' is': {'Himani': 9，' Manjeet': 8}}
> 所需关键字为:best