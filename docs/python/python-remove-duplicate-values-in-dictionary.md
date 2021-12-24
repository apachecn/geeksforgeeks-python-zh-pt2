# Python–删除字典中的重复值

> 原文:[https://www . geesforgeks . org/python-remove-重复值-in-dictionary/](https://www.geeksforgeeks.org/python-remove-duplicate-values-in-dictionary/)

有时，在使用 Python 字典时，我们可能会遇到这样的问题，即我们需要删除字典的所有重复值，并且我们不关心在此过程中是否有任何键被删除。这种应用可以出现在学校编程和日常编程中。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是我们执行这个任务的蛮力方式。在这种情况下，我们跟踪发生的值，如果它重复，就将其删除。

```py
# Python3 code to demonstrate working of 
# Remove duplicate values in dictionary
# Using loop

# initializing dictionary
test_dict = { 'gfg' : 10, 'is' : 15, 'best' : 20, 'for' : 10, 'geeks' : 20}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Remove duplicate values in dictionary
# Using loop
temp = []
res = dict()
for key, val in test_dict.items():
    if val not in temp:
        temp.append(val)
        res[key] = val

# printing result 
print("The dictionary after values removal : " + str(res)) 
```

**Output :**

> 原词典为:{'gfg': 10，' for': 10，' geeks': 20，' is': 15，' best': 20}
> 值删除后的词典:{'gfg': 10，' geeks': 20，' is': 15}