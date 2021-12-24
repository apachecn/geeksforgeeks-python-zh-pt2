# Python |将列表字典拆分为字典列表

> 原文:[https://www . geesforgeks . org/python-拆分-字典列表到字典列表/](https://www.geeksforgeeks.org/python-split-dictionary-of-lists-to-list-of-dictionaries/)

在编程的各个方面，从一种数据类型到另一种数据类型的转换是必不可少的。无论是开发还是竞争性编程。因此对它的了解是非常有用和必要的。

让我们来讨论某些方法，通过这些方法可以将字典列表转换为相应的字典列表。

**方法#1:使用列表理解**
我们可以使用列表理解作为一行替代来执行各种幼稚的任务，用更简洁的代码提供可读性。我们可以遍历每个字典元素，并相应地不断构建字典列表。

```py
# Python3 code to demonstrate 
# to convert dictionary of list to 
# list of dictionaries
# using list comprehension

# initializing dictionary
test_dict = { "Rash" : [1, 3], "Manjeet" : [1, 4], "Akash" : [3, 4] }

# printing original dictionary
print ("The original dictionary is : " + str(test_dict))

# using list comprehension
# to convert dictionary of list to 
# list of dictionaries
res = [{key : value[i] for key, value in test_dict.items()}
         for i in range(2)]

# printing result
print ("The converted list of dictionaries " +  str(res))
```

**Output:**

> 原始字典为:{'Rash': [1，3]，' Manjeet': [1，4]，' Akash': [3，4]}
> 转换后的字典列表[{'Rash': 1，' Manjeet': 1，' Akash': 3}，{'Rash': 3，' Manjeet': 4，' Akash': 4}]

**方法 2:使用`zip()`**
这种方法使用了`zip` 函数两次，第一次是我们需要将所有列表的特定索引值压缩为 1，第二次是获取特定索引的所有值并用相应的键进行压缩。

```py
# Python3 code to demonstrate 
# to convert dictionary of list to 
# list of dictionaries
# using zip()

# initializing dictionary
test_dict = { "Rash" : [1, 3], "Manjeet" : [1, 4], "Akash" : [3, 4] }

# printing original dictionary
print ("The original dictionary is : " + str(test_dict))

# using zip()
# to convert dictionary of list to 
# list of dictionaries
res = [dict(zip(test_dict, i)) for i in zip(*test_dict.values())]

# printing result
print ("The converted list of dictionaries " +  str(res))
```

**Output:**

> 原始字典为:{'Rash': [1，3]，' Akash': [3，4]，' Manjeet': [1，4]}
> 转换后的字典列表[{'Rash': 1，' Akash': 3，' Manjeet': 1}，{'Rash': 3，' Akash': 4，' Manjeet': 4}]