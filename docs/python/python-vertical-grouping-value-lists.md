# Python–垂直分组值列表

> 原文:[https://www . geesforgeks . org/python-垂直-分组-值列表/](https://www.geeksforgeeks.org/python-vertical-grouping-value-lists/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要将所有列表值垂直分组，即 w.r.t 相似索引。这种问题在很多领域都有应用，比如 web 开发。让我们讨论一下解决这个问题的某些方法。

> **输入** : test_dict = {'Gfg': [4，8]，' is': [87，2]，' best' : [14，1]}
> **输出** : [(4，87，14)，(8，2，1)]
> 
> **输入** : test_dict = {'Gfg': [4，6，7，8]}
> **输出** : [(4)、(6)、(7)、(8、]

**方法#1:使用列表理解+ `zip() + *`运算符**
以上功能的组合可以解决这个问题。在本例中，我们使用 values()执行提取值的任务，使用*运算符解包后使用 zip()执行垂直分组。

```py
# Python3 code to demonstrate working of 
# Vertical Grouping Value Lists
# Using list comprehension + zip() + * operator

# initializing dictionary
test_dict = {'Gfg': [4, 5, 7], 'is': [8, 9, 10], 'best' : [10, 12, 14]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Vertical Grouping Value Lists
# Using list comprehension + zip() + * operator
res = [tuple(idx) for idx in zip(*test_dict.values())]

# printing result 
print("The grouped values : " + str(res)) 
```

**Output :**

```py
The original dictionary is : {'Gfg': [4, 5, 7], 'is': [8, 9, 10], 'best': [10, 12, 14]}
The grouped values : [(4, 8, 10), (5, 9, 12), (7, 10, 14)]

```

**方法 2:使用`list() + zip() + values()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们执行类似于上述方法的任务，不同之处在于使用 list()而不是 list intelligence。

```py
# Python3 code to demonstrate working of 
# Vertical Grouping Value Lists
# Using list() + zip() + values()

# initializing dictionary
test_dict = {'Gfg': [4, 5, 7], 'is': [8, 9, 10], 'best' : [10, 12, 14]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Vertical Grouping Value Lists
# Using list() + zip() + values()
res = list(zip(*test_dict.values()))

# printing result 
print("The grouped values : " + str(res)) 
```

**Output :**

```py
The original dictionary is : {'Gfg': [4, 5, 7], 'is': [8, 9, 10], 'best': [10, 12, 14]}
The grouped values : [(4, 8, 10), (5, 9, 12), (7, 10, 14)]

```