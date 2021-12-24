# Python–排序字典忽略键

> 原文:[https://www . geesforgeks . org/python-sort-dictionary-忽略-key/](https://www.geeksforgeeks.org/python-sort-dictionary-ignoring-key/)

有时，在使用 Python 字典时，我们可能会遇到需要对字典元素进行排序的问题。这是非常直接的，但有时，我们可能会有某些杂散键，我们不希望在排序时改变顺序。这适用于 Python >= 3.6，因为从这个版本开始，密钥在字典中是有序的。这可以在数据域中得到应用。让我们讨论一下执行这项任务的方法。

> **输入**:test _ dict = {“*-*”:“流浪”，70:“是”}
> **输出**:{“*-*:“流浪”，70:“是”}
> 
> **输入**:test _ dict = { 54:“gfg”、“*-*”:“流浪”，20:“最佳”}
> **输出** : {20:“最佳”、“*-*”:“流浪”，54:“gfg”}

**方法:使用`next() + sorted() + insert()`**
以上方法的结合，可以用来解决这个问题。在这种情况下，我们使用 sorted()执行排序，insert()用于在其位置插入杂散元素，next()用于在初始杂散键的情况下按顺序获取下一个键。

```py
# Python3 code to demonstrate working of 
# Sort Dictionary ignoring Key
# Using next() + sorted() + insert()

# initializing dictionary
test_dict = {45 : 'is', 12 : 'gfg', 100 : 'best', 
             "*-*" : "stray", 150 : 'geeks', 120 : 'for'}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# strary key 
stray_key = '*-*'

# Sort Dictionary ignoring Key
# Using next() + sorted() + insert()
temp = next(idx for idx, val in enumerate(test_dict) if val == stray_key)
idx = sorted(ele for ele in test_dict if ele != stray_key)
idx.insert(temp, stray_key)
res = {ele: test_dict[ele] for ele in idx}

# printing result 
print("The dictionary after sorting : " + str(res)) 
```

**Output :**

> 原始字典为:{45: 'is '，12: 'gfg '，100: 'best '，' *-* ' ' stray '，150: 'geeks '，120: 'for'}
> 
> 排序后的字典:{ 12:“gfg”，45:“is”，100:“best”，“*-*”:“stray”，120:“for”，150:“geeks”}