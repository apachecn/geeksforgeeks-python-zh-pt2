# Python |字典中的逆序键

> 原文:[https://www . geesforgeks . org/python-逆序-字典中的键/](https://www.geeksforgeeks.org/python-reversed-order-keys-in-dictionary/)

在使用字典时，我们有时会遇到一个问题，那就是我们要求按照字典出现的相反顺序打印字典。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`reversed() + sorted() + keys()` +循环**
上述功能的组合可用于执行该特定任务。`sorted`功能用于对按键进行排序，`reversed`获取使用`keys()`提取的按键，按降序排列，并使用循环打印。

```py
# Python3 code to demonstrate working of
# Reversed Order keys in dictionary
# Using sorted() + keys() + reversed() + loop

# initializing dictionary
test_dict = {1 : "Gfg", 5 : "is", 4 : "the", 2 : "best"}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Using sorted() + keys() + reversed() + loop
# Reversed Order keys in dictionary
res = []
for ele in reversed(sorted(test_dict.keys())):
    res.append(ele)

# printing result 
print("The reversed order of dictionary keys : " + str(res))
```

**Output :**

```py
The original dictionary is : {1: 'Gfg', 2: 'best', 4: 'the', 5: 'is'}
The reversed order of dictionary keys : [5, 4, 2, 1]

```