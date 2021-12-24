# Python–值列表键展平

> 原文:[https://www . geesforgeks . org/python-value-list-key-扁平化/](https://www.geeksforgeeks.org/python-value-list-key-flattening/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即需要对每个键值执行配对来提取扁平字典。这种问题可以在数据领域得到应用。让我们讨论执行这项任务的特定方式。

**方法#1:使用循环**
这是一种可以执行该任务的暴力方式。在这种情况下，我们迭代每个键的值，并将其分配给它的键，并构造新的键-值对。

```py
# Python3 code to demonstrate working of 
# Value List Key Flattening
# Using loop

# initializing dictionary
test_dict = {'gfg' : [4, 5, 7], 'best' : [10, 12]}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Value List Key Flattening
# Using loop
res = []
for key, vals in test_dict.items():
    for ele in vals:
        res.append({"key": key, "value": ele})

# printing result 
print("The flattened dictionary : " + str(res)) 
```

**Output :**

```py
The original dictionary : {'best': [10, 12], 'gfg': [4, 5, 7]}
The flattened dictionary : [{'value': 10, 'key': 'best'}, {'value': 12, 'key': 'best'}, {'value': 4, 'key': 'gfg'}, {'value': 5, 'key': 'gfg'}, {'value': 7, 'key': 'gfg'}]

```