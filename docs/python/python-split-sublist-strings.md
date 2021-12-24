# Python |拆分子列表字符串

> 原文:[https://www.geeksforgeeks.org/python-split-sublist-strings/](https://www.geeksforgeeks.org/python-split-sublist-strings/)

拆分字符串的另一种变体是拆分作为子列表元素的字符串。这是一个非常特殊的问题，但是人们可以得到这种格式的数据，并且无论如何，拆分数据的知识非常有用。让我们讨论一下执行这项特殊任务的某些方法。

**方法一:使用列表理解+ `split()`**

这个方法是较长循环版本的简写版本，人们可以选择它来解决这个特殊的问题。我们只是在使用 split 函数的列表理解中使用循环来分割获取子列表的字符串。

```
# Python3 code to demonstrate
# Split Sublist Strings
# using split() + list comprehension

# initializing list
test_list = [['GfG is best'], ['All love Gfg'], ['Including me']]

# printing original list
print("The original list : " + str(test_list))

# using split() + list comprehension
# Split Sublist Strings
res = [sub.split() for subl in test_list for sub in subl]

# print result
print("The list after splitting strings : " + str(res))
```

**Output :**

> 原列表:[['GfG 最好']，['All love Gfg']，['Including me']]
> 拆串后的列表:['GfG '，' is '，' best']，['All '，' love '，' Gfg']，['Including '，' me']

**方法二:使用`map()`+λ+`split()`+T3】**

该任务也可以使用上述 3 个功能的组合来执行。map 函数将拆分逻辑绑定到使用 lambda 函数编写的每个元素，lambda 函数使用 split 函数来执行拆分。

```
# Python3 code to demonstrate
# Split Sublist Strings
# using map() + lambda + split()

# initializing list
test_list = [['GfG is best'], ['All love Gfg'], ['Including me']]

# printing original list
print("The original list : " + str(test_list))

# using map() + lambda + split()
# Split Sublist Strings
res = list(map(lambda sub: sub[0].split(' '), test_list))

# print result
print("The list after splitting strings : " + str(res))
```

**Output :**

> 原列表:[['GfG 最好']，['All love Gfg']，['Including me']]
> 拆串后的列表:['GfG '，' is '，' best']，['All '，' love '，' Gfg']，['Including '，' me']