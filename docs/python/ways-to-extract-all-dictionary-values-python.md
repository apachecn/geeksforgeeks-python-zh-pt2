# 提取所有字典值的方法| Python

> 原文:[https://www . geesforgeks . org/提取所有字典值的方法-python/](https://www.geeksforgeeks.org/ways-to-extract-all-dictionary-values-python/)

在使用 Python 字典时，可能会出现我们只关心获取值列表而不关心键的情况。这是另一个重要的用途，应该了解并讨论解决方案。让我们通过某些方法来执行这个任务。

**方法#1:使用循环+ `keys()`**
实现这个任务首先想到的方法是使用循环访问每个键的值，并将其追加到列表中并返回。这可以是执行该任务的方法之一。

```
# Python3 code to demonstrate working of
# Ways to extract all dictionary values
# Using loop + keys()

# initializing dictionary
test_dict = {'gfg' : 1, 'is' : 2, 'best' : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Extracting all dictionary values
# Using loop + keys()
res = []
for key in test_dict.keys() :
    res.append(test_dict[key])

# printing result
print("The list of values is : " +  str(res))
```

**Output :**

```
The original dictionary is : {'gfg': 1, 'is': 2, 'best': 3}
The list of values is : [1, 2, 3]

```