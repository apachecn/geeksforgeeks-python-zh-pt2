# Python–测试字典值列表中的第 Kth 索引

> 原文:[https://www . geesforgeks . org/python-test-kth-index-in-dictionary-value-list/](https://www.geeksforgeeks.org/python-test-kth-index-in-dictionary-value-list/)

有时，在使用 Python 字典时，我们会遇到一个问题，我们需要测试通过字典，字典中所有值的第 k 个索引是否等于 n。这种问题可能发生在网络开发领域。让我们讨论一下解决这个问题的某些方法。

> **输入** : test_dict = {'Gfg' : [10，4，8，17]，' best' : [90，4]}
> 输出:真
> 
> **输入** : test_dict = {'Gfg' : [10，7]}
> 输出 : False

**方法#1:使用 loop + `items()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用 items()检查字典的所有项，并使用循环来迭代字典键和测试是否相等。

```
# Python3 code to demonstrate working of 
# Test Kth index in Dictionary value list
# Using  items() + loop

# initializing dictionary
test_dict = {'Gfg' : [1, 4, 8], 'is' : [8, 4, 2], 'best' : [7, 4, 9]}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing K 
K = 2

# initializing N 
N = 4

# Test Kth index in Dictionary value list
# Using  items() + loop
res = True
for key, val in test_dict.items():
    if val[K - 1] != N:
        res = False

# printing result 
print("Are all Kth index equal to N : " + str(res)) 
```

**Output :**

```
The original dictionary : {'is': [8, 4, 2], 'best': [7, 4, 9], 'Gfg': [1, 4, 8]}
Are all Kth index equal to N : True

```

**方法 2:使用`all()` +生成器表达式**
以上功能的组合也可以用来解决这个问题。在本文中，我们使用 all()来测试所有元素与 n 的相等性。

```
# Python3 code to demonstrate working of 
# Test Kth index in Dictionary value list
# Using all() + generator expression

# initializing dictionary
test_dict = {'Gfg' : [1, 4, 8], 'is' : [8, 4, 2], 'best' : [7, 4, 9]}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing K 
K = 2

# initializing N 
N = 4

# Test Kth index in Dictionary value list
# Using all() + generator expression
res = all([val[K - 1] == N for idx, val in test_dict.items()])

# printing result 
print("Are all Kth index equal to N : " + str(res)) 
```

**Output :**

```
The original dictionary : {'is': [8, 4, 2], 'best': [7, 4, 9], 'Gfg': [1, 4, 8]}
Are all Kth index equal to N : True

```