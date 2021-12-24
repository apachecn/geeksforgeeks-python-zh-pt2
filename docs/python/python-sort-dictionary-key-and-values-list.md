# Python–排序字典键和值列表

> 原文:[https://www . geesforgeks . org/python-sort-dictionary-key-and-values-list/](https://www.geeksforgeeks.org/python-sort-dictionary-key-and-values-list/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，需要对它进行排序，wrt 键，但也可能会有一个变化，需要对它的值列表进行排序。让我们讨论一下执行这项任务的具体方法。

> **输入** : test_dict = {'c': [3]，' b': [12，10]，' a': [19，4]}
> **输出** : {'a': [4，19]，' b': [10，12]，' c': [3]}
> 
> **输入** : test_dict = {'c': [10，34，3]}
> **输出** : {'c': [3，10，34]}

**方法一:使用`sorted()` +循环**
以上功能的组合可以解决这个问题。在这种情况下，我们首先对键的所有值进行排序，然后以暴力的方式执行键排序。

```py
# Python3 code to demonstrate working of 
# Sort Dictionary key and values List
# Using loop + dictionary comprehension

# initializing dictionary
test_dict = {'gfg': [7, 6, 3], 
             'is': [2, 10, 3], 
             'best': [19, 4]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Sort Dictionary key and values List
# Using loop + dictionary comprehension
res = dict()
for key in sorted(test_dict):
    res[key] = sorted(test_dict[key])

# printing result 
print("The sorted dictionary : " + str(res)) 
```

**Output :**

> 原字典为:{'gfg': [7，6，3]，' is': [2，10，3]，' best': [19，4]}
> 排序后的字典:{'best': [4，19]，' gfg': [3，6，7]，' is': [2，3，10]}

**方法 2:使用字典理解+ `sorted()`**
以上功能的组合可以用来解决这个问题。在本文中，我们在词典理解结构中执行双重排序任务。

```py
# Python3 code to demonstrate working of 
# Sort Dictionary key and values List
# Using dictionary comprehension + sorted()

# initializing dictionary
test_dict = {'gfg': [7, 6, 3], 
             'is': [2, 10, 3], 
             'best': [19, 4]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Sort Dictionary key and values List
# Using dictionary comprehension + sorted()
res = {key : sorted(test_dict[key]) for key in sorted(test_dict)}

# printing result 
print("The sorted dictionary : " + str(res)) 
```

**Output :**

> 原字典为:{'gfg': [7，6，3]，' is': [2，10，3]，' best': [19，4]}
> 排序后的字典:{'best': [4，19]，' gfg': [3，6，7]，' is': [2，3，10]}