# Python |字典中 N 个最大值

> 原文:[https://www . geesforgeks . org/python-n-最大值-in-dictionary/](https://www.geeksforgeeks.org/python-n-largest-values-in-dictionary/)

很多时候，在使用 Python 字典时，我们可能会遇到一个特殊的问题，即在众多键中找到 N 个最大值。在使用 web 开发领域时，这个问题很常见。让我们讨论执行这项任务的几种方法。

**方法#1 : `itemgetter() + items() + sorted()`**

上述方法的组合用于执行这一特定任务。在这里，我们只是对使用`itemgetter()`表示并使用`items().`访问的字典值进行反向排序

```py
# Python3 code to demonstrate working of
# N largest values in dictionary
# Using sorted() + itemgetter() + items()
from operator import itemgetter

# Initialize dictionary
test_dict = {'gfg' : 1, 'is' : 4, 'best' : 6, 'for' : 7, 'geeks' : 3 }

# Initialize N 
N = 3

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# N largest values in dictionary
# Using sorted() + itemgetter() + items()
res = dict(sorted(test_dict.items(), key = itemgetter(1), reverse = True)[:N])

# printing result
print("The top N value pairs are  " + str(res))
```

**Output :**

```py
The original dictionary is : {'best': 6, 'gfg': 1, 'geeks': 3, 'for': 7, 'is': 4}
The top N value pairs are  {'for': 7, 'is': 4, 'best': 6}

```

**方法 2:使用`nlargest()`**
可以使用`nlargest`功能执行该任务。这是`heapq`库中内置的功能，内部执行该任务，外部也可以使用。缺点是只打印键而不打印值。

```py
# Python3 code to demonstrate working of
# N largest values in dictionary
# Using nlargest
from heapq import nlargest

# Initialize dictionary
test_dict = {'gfg' : 1, 'is' : 4, 'best' : 6, 'for' : 7, 'geeks' : 3 }

# Initialize N 
N = 3

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# N largest values in dictionary
# Using nlargest
res = nlargest(N, test_dict, key = test_dict.get)

# printing result
print("The top N value pairs are  " + str(res))
```

**Output :**

```py
The original dictionary is : {'gfg': 1, 'best': 6, 'geeks': 3, 'for': 7, 'is': 4}
The top N value pairs are  ['for', 'best', 'is']

```