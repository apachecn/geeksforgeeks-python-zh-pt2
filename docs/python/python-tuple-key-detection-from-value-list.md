# Python–从值列表中检测元组密钥

> 原文:[https://www . geesforgeks . org/python-tuple-key-detection-from-value-list/](https://www.geeksforgeeks.org/python-tuple-key-detection-from-value-list/)

有时，在处理记录数据时，我们会遇到一个问题，即需要从其值列表中提取匹配值为 K 的键。这种问题可能发生在链接到数据的域中。让我们讨论执行这项任务的某些方法。
**方法#1:使用列表理解**
这个任务可以使用列表理解来执行。在这种情况下，我们遍历每个记录，并测试它的值列表。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# Tuple key detection from value list
# using List comprehension

# Initializing list
test_list = [('Gfg', [1, 3, 4]), ('is', [5, 8, 10]), ('best', [11, 9, 2])]

# printing original list
print("The original list is : " + str(test_list))

# Initializing K
K = 4

# Tuple key detection from value list
# using List comprehension
res = [sub[0] for sub in test_list if K in sub[1]]

# printing result
print ("The required key of list values : " + str(res))
```

**Output : **

```py
The original list is : [('Gfg', [1, 3, 4]), ('is', [5, 8, 10]), ('best', [11, 9, 2])]
The required key of list values : ['Gfg']
```

**方法 2:使用 filter() + lambda**
以上功能的组合也可以用来执行此任务。在这种情况下，filter()用于检查列表中是否存在，并在 lambda 的帮助下提取所需的密钥。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# Tuple key detection from value list
# using filter() + lambda

# Initializing list
test_list = [('Gfg', [1, 3, 4]), ('is', [5, 8, 10]), ('best', [11, 9, 2])]

# printing original list
print("The original list is : " + str(test_list))

# Initializing K
K = 4

# Tuple key detection from value list
# using filter() + lambda
res = list(filter(lambda sub, ele = K : ele in sub[1], test_list))

# printing result
print ("The required key of list values : " + str(res[0][0]))
```

**Output : **

```py
The original list is : [('Gfg', [1, 3, 4]), ('is', [5, 8, 10]), ('best', [11, 9, 2])]
The required key of list values : Gfg
```