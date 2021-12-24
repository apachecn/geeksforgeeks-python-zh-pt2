# Python |在字典列表中分隔键的值

> 原文:[https://www . geesforgeks . org/python-分隔-关键字-字典列表中的值/](https://www.geeksforgeeks.org/python-segregating-keys-value-in-list-of-dictionaries/)

在使用字典时，我们可能会遇到这样的问题:我们需要将所有相似的键值隔离在一起。当使用数据库时，这种问题可能发生在 web 开发领域。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用生成器表达式**
可以使用生成器表达式来执行该特定任务。在这种情况下，我们一次取一个键，并在所有字典中检查匹配的键。缺点是我们需要知道钥匙在哪里。

```
# Python3 code to demonstrate working of
# Segregating key's value in list of dictionaries
# Using generator expression

# Initialize list
test_list = [{'gfg' : 1, 'best' : 2}, {'gfg' : 4, 'best': 5}]

# printing original list
print("The original list : " +  str(test_list))

# Using generator expression
# Segregating key's value in list of dictionaries
res = [tuple(sub["gfg"] for sub in test_list),
      tuple(sub["best"] for sub in test_list)]

# printing result 
print("Segregated values of keys are : " + str(res))
```

**Output :**

> 原始列表:[{'best': 2，' gfg': 1}，{'best': 5，' gfg': 4}]
> 键的分隔值为:[(1，4)，(2，5)]