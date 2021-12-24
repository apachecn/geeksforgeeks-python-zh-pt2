# Python–键的同步排序

> 原文:[https://www . geesforgeks . org/python-synchronized-排序关键字/](https://www.geeksforgeeks.org/python-synchronized-sorting-of-keys/)

有时，在使用 Python Dictionaries 时，我们可能会遇到一个问题，即我们需要执行字典的某个键的排序，以及对相应的键执行类似的更改。这种类型在 web 开发和竞争性编程中有应用。让我们讨论一下执行这项任务的具体方法。

> **输入**:test _ dict = {“Gfg”:[3，2，1]，‘best’:[17，10，20]}，sort _ key =“Gfg”
> **输出**:{‘Gfg’:[1，2，3]，‘best’:[20，10，17]}
> 
> **输入**:test _ dict = {“Gfg”:[3，1]，‘best’:[10，20]，‘CS’:[12，43]}，sort _ key =“Gfg”
> **输出**:{“Gfg”:[1，3]，‘best’:[20，10]，‘CS’:[43，12]}

**方法一:使用词典理解+ `sorted()` +列表理解**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 sorted()执行排序，并使用字典理解来复制到其他字典。

```
# Python3 code to demonstrate working of 
# Synchronized Sorting 
# Using dictionary comprehension + sorted() + list comprehension

# initializing dictionary
test_dict = {"Gfg" : [4, 6, 7, 3, 10], 
             'is' : [7, 5, 9, 10, 11],
             'best' : [1, 2, 10, 21, 12]}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing sort key
sort_key = "Gfg"

# Synchronized Sorting 
# Using dictionary comprehension + sorted() + list comprehension
temp = [ele for ele, idx in sorted(enumerate(test_dict[sort_key]),
                                          key = lambda x : x[1])]

res = {key : [val[idx] for idx in temp] for key, val in test_dict.items()}

# printing result 
print("The Synchronized sorted dictionary : " + str(res)) 
```

**Output :**

> 原始字典:{'best': [1，2，10，21，12]，' Gfg': [4，6，7，3，10]，' is': [7，5，9，10，11]}
> 同步排序字典:{'best': [21，1，2，10，12]，' Gfg': [3，4，6，7，10]，' is': [10，7，5，9，11]}