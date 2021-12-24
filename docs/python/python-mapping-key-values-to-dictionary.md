# Python–将键值映射到字典

> 原文:[https://www . geesforgeks . org/python-映射-键值到字典/](https://www.geeksforgeeks.org/python-mapping-key-values-to-dictionary/)

有时，在处理 Python 记录时，我们可能会遇到一个问题，即我们需要提取关键字的值作为所需的字典值。这可以应用于我们需要减少数据存储的领域和 web 开发领域。让我们讨论执行这项任务的某些方法。

**方法一:利用字典理解**
这是我们解决这个问题的方法之一。在这种情况下，我们迭代列表键，并使用字典理解来构造所需键值对的字典。

```
# Python3 code to demonstrate working of 
# Mapping key values to Dictionary
# Using dictionary comprehension

# initializing list
test_list = [{'name' : 'Manjeet', 'age' : 23}, 
             {'name' : 'Akshat',  'age' : 22},
             {'name' : 'Nikhil', 'age' : 21}]

# printing original list
print("The original list is : " + str(test_list))

# Mapping key values to Dictionary
# Using dictionary comprehension
res = {sub['name'] : sub['age'] for sub in test_list}

# printing result 
print("The flattened dictionary is : " + str(dict(res))) 
```

**Output :**

> 原列表为:[{'age': 23，' name': 'Manjeet'}，{'age': 22，' name': 'Akshat'}，{'age': 21，' name': 'Nikhil'}]
> 拼合词典为:{'Manjeet': 23，' Akshat': 22，' Nikhil': 21}