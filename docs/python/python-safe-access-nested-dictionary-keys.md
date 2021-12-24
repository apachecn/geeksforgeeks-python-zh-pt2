# Python |安全访问嵌套字典键

> 原文:[https://www . geesforgeks . org/python-safe-access-nested-dictionary-keys/](https://www.geeksforgeeks.org/python-safe-access-nested-dictionary-keys/)

有时候，在使用 Python 时，我们会遇到一个问题，我们需要获取字典的二级键，即嵌套键。这种类型的问题在 web 开发中很常见，尤其是随着 NoSQL 数据库的出现。让我们讨论在字典中安全获取嵌套可用键的某些方法。

**方法#1:使用嵌套`get()`**

这个方法就是用来解决这个特定的问题，我们只是利用`get()`的功能性，在没有值的情况下进行检查和赋值来实现这个特定的任务。如果没有任何键，只返回无错误。

```py
# Python3 code to demonstrate working of
# Safe access nested dictionary key
# Using nested get()

# initializing dictionary
test_dict = {'Gfg' : {'is' : 'best'}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# using nested get()
# Safe access nested dictionary key
res = test_dict.get('Gfg', {}).get('is')

# printing result
print("The nested safely accessed value is :  " + str(res))
```

**Output :**

```py
The original dictionary is : {'Gfg': {'is': 'best'}}
The nested safely accessed value is :  best

```

**方法 2:使用`reduce()`+λ**

上述功能的组合可用于执行该特定任务。它只是使用 lambda 函数检查可用的键。这个方法的优点是一次可以查询 1 个以上的键，即更多的嵌套级别键，但缺点是它只适用于 Python2。

```py
# Python code to demonstrate working of
# Safe access nested dictionary key
# Using reduce() + lambda

# initializing dictionary
test_dict = {'Gfg' : {'is' : 'best'}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# using reduce() + lambda
# Safe access nested dictionary key
keys = ['Gfg', 'is']
res = reduce(lambda val, key: val.get(key) if val else None, keys, test_dict)

# printing result
print("The nested safely accessed value is :  " + str(res))
```

**Output :**

```py
The original dictionary is : {'Gfg': {'is': 'best'}}
The nested safely accessed value is :  best

```