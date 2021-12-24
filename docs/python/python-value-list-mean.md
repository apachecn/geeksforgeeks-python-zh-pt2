# Python–值列表平均值

> 原文:[https://www.geeksforgeeks.org/python-value-list-mean/](https://www.geeksforgeeks.org/python-value-list-mean/)

有时，在使用 Python 字典值时，我们可能会遇到这样的问题，即我们需要找到所有字典值列表的所有值的平均值。这个问题可能在许多领域都有应用，包括 web 开发。让我们讨论一下解决这个问题的某些方法。

> **输入** : test_dict = {'best': [11，21]，' Gfg': [7，5]}
> **输出** : {'best': 16.0，' Gfg': 6.0}
> 
> **输入**:test _ dict = { ' Gfg ':[9]}
> **输出** : {'Gfg': 9.0}

**方法#1:使用 loop + `sum() + len()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 sum()计算所有值的总和，使用 len()计算所有值列表长度的总和。迭代使用循环完成。

```
# Python3 code to demonstrate working of 
# Value list mean
# Using loop + sum() + len()

# initializing dictionary
test_dict = {'Gfg' : [6, 7, 5, 4], 'is' : [10, 11, 2, 1], 'best' : [12, 1, 2]} 

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Value list mean
# Using loop + sum() + len()
res = dict()
for key in test_dict:
    res[key] = sum(test_dict[key]) / len(test_dict[key])

# printing result 
print("The dictionary average is : " + str(res)) 
```

**Output :**

> 原始字典为:{'is': [10，11，2，1]，' best': [12，1，2]，' Gfg': [6，7，5，4]}
> 字典平均值为:{'is': 6.0，' best': 5.0，' Gfg': 5.5}

**方法 2:使用字典理解**
这是执行这项任务的另一种方式。这是速记，在它的帮助下，这个任务可以以类似于上述方法的方式执行。

```
# Python3 code to demonstrate working of 
# Value list mean
# Using dictionary comprehension

# initializing dictionary
test_dict = {'Gfg' : [6, 7, 5, 4], 'is' : [10, 11, 2, 1], 'best' : [12, 1, 2]} 

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Value list mean
# Using dictionary comprehension
res = {key: sum(val) / len(val) for key, val, in test_dict.items()}

# printing result 
print("The dictionary average is : " + str(res)) 
```

**Output :**

> 原始字典为:{'is': [10，11，2，1]，' best': [12，1，2]，' Gfg': [6，7，5，4]}
> 字典平均值为:{'is': 6.0，' best': 5.0，' Gfg': 5.5}