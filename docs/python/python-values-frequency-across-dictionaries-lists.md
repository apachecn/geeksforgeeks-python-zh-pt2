# Python–字典列表中的值频率

> 原文:[https://www . geesforgeks . org/python-values-frequency-trans-dictionary-list/](https://www.geeksforgeeks.org/python-values-frequency-across-dictionaries-lists/)

给定两个字典列表，计算字典 1 到 2 中每个值对应的频率。

> **输入**:test _ list 1 =[{“Gfg”:6 }、{“best”:10 }]、test _ list 2 =[{“a”:6 }、{“b”:10 }、{“d”:6 } }]
> **输出**:{“Gfg”:2、‘best】:1 }
> **解释** : 6 在第 2 个列表中有 2 个出现，10 有 1 个。
> 
> **输入**:test _ list 1 =[{“Gfg”:6 }]，test _ list 2 =[{“a”:6 }，{“b”:6 }，{“d”:6 } }]
> **输出**:{“Gfg”:3 }
> **解释** : 6 在第 2 个列表中有 3 个出现。

**方法:使用词典理解+计数()+列表理解**

上述功能的组合可以用来解决这个问题。在本例中，我们使用两个步骤来执行此任务，首先从第二个列表中提取所有值，然后使用列表理解和计数()使用第一个字典执行频率映射。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Values frequency across Dictionaries lists
# Using list comprehension + dictionary comprehension + count()

# initializing lists
test_list1 = [{"Gfg" : 6}, {"is" : 9}, {"best" : 10}]
test_list2 = [{"a" : 6}, {"b" : 10}, {"c" : 9}, {"d" : 6}, {"e" : 9}, {"f" : 9}]

# printing original list
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# extracting values from target dictionary
temp = [val for sub in test_list2 for key, val in sub.items()]

# frequency mapping from 1st dictionary keys 
res = {key : temp.count(val) for sub in test_list1 for key, val in sub.items()}

# printing result 
print("The frequency dictionary : " + str(res))
```

**Output**

```
The original list 1 : [{'Gfg': 6}, {'is': 9}, {'best': 10}]
The original list 2 : [{'a': 6}, {'b': 10}, {'c': 9}, {'d': 6}, {'e': 9}, {'f': 9}]
The frequency dictionary : {'Gfg': 2, 'is': 3, 'best': 1}

```