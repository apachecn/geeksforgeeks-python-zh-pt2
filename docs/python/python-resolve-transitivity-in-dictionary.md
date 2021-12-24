# Python–解析字典中的传递性

> 原文:[https://www . geesforgeks . org/python-resolve-transity-in-dictionary/](https://www.geeksforgeeks.org/python-resolve-transitivity-in-dictionary/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，我们需要解决悬空及物性，即移除具有类型关系 **a- > b，b- > c = a- > c** 的键，移除该关系中不需要的“b”。这种问题可能发生在许多核心的计算机科学领域，也可能发生在网络开发领域或图形领域。让我们讨论执行这项任务的特定方式。

**方法:使用反向字典+循环**
这是解决这个这个问题的一种方法。在这种情况下，我们构建反向字典，然后运行循环来检查重复项并执行删除。

```
# Python3 code to demonstrate working of 
# Resolve Transitivity in Dictionary
# Using reverse dictionary + loop

# initializing dictionary
test_dict = {'a' : 3, 'b' : 4, 3 : 5, 'l' : 7, 4 : 'd', 7 : 'k'}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Resolve Transitivity in Dictionary
# Using reverse dictionary + loop
temp = {val: key for key, val in test_dict.items()}
for val in temp:
    if val in test_dict:
       test_dict.pop(temp[val])
       test_dict[temp[val]] = test_dict[val]
       test_dict.pop(val)

# printing result 
print("The resolved dictionary : " + str(test_dict)) 
```

**Output :**

```
The original dictionary : {3: 5, 4: 'd', 7: 'k', 'b': 4, 'l': 7, 'a': 3}
The resolved dictionary : {'b': 'd', 'l': 'k', 'a': 5}

```