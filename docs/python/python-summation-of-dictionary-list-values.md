# Python |字典列表值求和

> 原文:[https://www . geesforgeks . org/python-字典列表值求和/](https://www.geeksforgeeks.org/python-summation-of-dictionary-list-values/)

有时，在使用 Python 字典时，我们可以将它的值作为列表。在这种情况下，我们可能会遇到一个问题，那就是我们只需要将这些列表中的元素计数作为一个整体。这可能是数据科学中的一个问题，在数据科学中，我们需要获得观察中的全部记录。让我们讨论执行这项任务的某些方法。

**方法#1:使用`sum()` +列表理解**
这个任务可以使用求和函数来执行，求和函数可以用来得到求和，内部列表理解可以提供一个机制来将这个逻辑迭代到字典的所有键。

```
# Python3 code to demonstrate working of
# Summation of dictionary list values
# using sum() + list comprehension

# initialize dictionary
test_dict = {'gfg' : [5, 6, 7], 'is' : [10, 11], 'best' : [19, 31, 22]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Summation of dictionary list values
# using sum() + list comprehension
res = sum(len(sub) for sub in test_dict.values())

# printing result
print("Summation of dictionary list values are : " + str(res))
```

**Output :**

```
The original dictionary is : {'best': [19, 31, 22], 'is': [10, 11], 'gfg': [5, 6, 7]}
Summation of dictionary list values are : 8

```