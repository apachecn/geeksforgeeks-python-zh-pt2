# Python |排序字典键列表

> 原文:[https://www . geesforgeks . org/python-sort-dictionary-key-to-list/](https://www.geeksforgeeks.org/python-sort-dictionary-keys-to-list/)

有时，我们希望将字典展平为列表，简单的展平相对容易一些，但当我们希望以排序的方式(即按值排序)对齐键和值时，这就变成了一个相当复杂的问题。让我们讨论执行这项任务的某些方法。

**方法#1:使用`sum() + sorted() + items()`+λ**
上述功能的组合可用于执行该特定任务。在这种情况下，我们首先使用`sorted()`按照所需的顺序按键对字典进行排序，然后通过`items()` 函数提取键和值，这些键和值由 lambda 函数成对返回。sum 函数执行填充元组的任务。

```
# Python3 code to demonstrate working of
# Sort dictionary keys to list 
# Using sum() + sorted() + items() + lambda

# initializing dictionary
test_dict = {'Geeks' : 2, 'for' : 1, 'CS' : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Using sum() + sorted() + items() + lambda
# Sort dictionary keys to list 
res = list(sum(sorted(test_dict.items(), key = lambda x:x[1]), ()))

# printing result 
print("List after conversion from dictionary : " + str(res))
```

**Output :**

```
The original dictionary is : {'Geeks': 2, 'for': 1, 'CS': 3}
List after conversion from dictionary : ['for', 1, 'Geeks', 2, 'CS', 3]

```