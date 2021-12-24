# Python–字典中最小的 K 值

> 原文:[https://www . geesforgeks . org/python-minist-k-values-in-dictionary/](https://www.geeksforgeeks.org/python-smallest-k-values-in-dictionary/)

很多时候，在使用 Python 字典时，我们可能会遇到一个特殊的问题，即在众多键中寻找值的 K 最小值。在使用 web 开发领域时，这个问题很常见。让我们讨论执行这项任务的几种方法。

**方法#1 : `itemgetter() + items() + sorted()`**
上述方法的组合用于执行这一特定任务。在本文中，我们只是对使用 itemsgetter()表示并使用 item()访问的字典值进行排序。

```
# Python3 code to demonstrate working of
# Smallest K values in Dictionary
# Using sorted() + itemgetter() + items()
from operator import itemgetter

# Initialize dictionary
test_dict = {'gfg' : 1, 'is' : 4, 'best' : 6, 'for' : 7, 'geeks' : 3 }

# Initialize K 
K = 2

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Smallest K values in Dictionary
# Using sorted() + itemgetter() + items()
res = dict(sorted(test_dict.items(), key = itemgetter(1))[:K])

# printing result
print("The minimum K value pairs are " + str(res))
```

**Output :**

```
The original dictionary is : {'geeks': 3, 'is': 4, 'for': 7, 'best': 6, 'gfg': 1}
The minimum K value pairs are {'geeks': 3, 'gfg': 1}

```