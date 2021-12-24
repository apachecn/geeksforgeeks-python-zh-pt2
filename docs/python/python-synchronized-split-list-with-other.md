# Python–与其他

同步拆分列表

> 原文:[https://www . geesforgeks . org/python-synchronized-split-list-with-other/](https://www.geeksforgeeks.org/python-synchronized-split-list-with-other/)

有时，在使用 Python 数据时，我们可能会遇到这样的问题，即我们需要对一个字符串执行拆分，该字符串与其他列表中的元素有映射，因此需要对由于拆分而形成的不同单词执行映射。这种类型的问题很特殊，但可以应用于许多领域。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [5，6]，str_list = ['Gfg 最好'，'我爱 Gfg']
> **输出** : [5，5，5，6，6，6]
> 
> **输入** : test_list = [5]，str_list = ['Gfg 最好']
> T3】输出 : [5，5，5]

**方法#1:使用`map() + zip() + enumerate() + split()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 split()执行拆分值的任务，并使用 zip()和 map()执行相应的元素映射。迭代使用枚举()进行。

```py
# Python3 code to demonstrate working of 
# Synchronized Split list with other
# Using map() + zip() + enumerate() + split()

# initializing list
test_list = [5, 6, 3, 7, 4] 

# printing original list
print("The original list is : " + str(test_list))

# initializing String list 
str_list = ['Gfg', 'is best', 'I love', 'Gfg', 'and CS']

# Synchronized Split list with other
# Using map() + zip() + enumerate() + split()
temp = list(map(list, zip(*[(idx, sub) for idx, val in 
            enumerate(map(lambda x: x.split(), str_list), 1) for sub in val])))
res = []
for ele in temp[0]:
    res.append(test_list[ele - 1])

# printing result 
print("Mapped list elements : " + str(res))
```

**Output :**

```py
The original list is : [5, 6, 3, 7, 4]
Mapped list elements : [5, 6, 6, 3, 3, 7, 4, 4]

```

**方法 2:使用`chain.from_iterables() + zip()`**
这是可以执行该任务的另一种方式。在本例中，我们使用 chain.from_iterables()执行展平任务，zip()用于执行并行迭代。

```py
# Python3 code to demonstrate working of 
# Synchronized Split list with other
# Using chain.from_iterables() + zip()
from itertools import chain

# initializing list
test_list = [5, 6, 3, 7, 4] 

# printing original list
print("The original list is : " + str(test_list))

# initializing String list 
str_list = ['Gfg', 'is best', 'I love', 'Gfg', 'and CS']

# Synchronized Split list with other
# Using chain.from_iterables() + zip()
res = list(chain.from_iterable([[sub1] * len(sub2.split()) for sub1, sub2 in zip(test_list, str_list)]))

# printing result 
print("Mapped list elements : " + str(res))
```

**Output :**

```py
The original list is : [5, 6, 3, 7, 4]
Mapped list elements : [5, 6, 6, 3, 3, 7, 4, 4]

```