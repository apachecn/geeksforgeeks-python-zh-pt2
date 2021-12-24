# Python–排序字典项目配对

> 原文:[https://www . geesforgeks . org/python-sorted-order-dictionary-items-pairing/](https://www.geeksforgeeks.org/python-sorted-order-dictionary-items-pairing/)

有时，在使用 Python 字典时，我们可能会遇到这样的问题，即我们需要对字典项目进行重新排序，以排序顺序对键和值进行配对，最小对最小值，最大对最大值等等。这种应用可以出现在竞争领域和日常编程中。让我们讨论执行这项任务的某些方法。

**方法#1:使用`zip() + sort() + keys() + values()`**
以上功能的组合可以用来解决这个问题。在本例中，我们使用 zip()执行配对任务，排序由 sort()处理。

```py
# Python3 code to demonstrate working of 
# Sorted order Dictionary items pairing
# Using zip() + sort() + keys() + values()

# initializing dictionary
test_dict = {45 : 3, 7 : 8, 98 : 4, 10 : 12, 65 : 90, 15 : 19}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Sorted order Dictionary items pairing
# Using zip() + sort() + keys() + values()
vals = list(test_dict.values())
vals.sort()
keys = list(test_dict.keys())
keys.sort()
res = dict(zip(keys, vals))

# printing result 
print("The sorted order pairing : " + str(res)) 
```

**Output :**

```py
The original dictionary is : {65: 90, 98: 4, 7: 8, 10: 12, 45: 3, 15: 19}
The sorted order pairing : {65: 19, 98: 90, 7: 3, 10: 4, 45: 12, 15: 8}

```