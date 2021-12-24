# Python |测试元组密钥字典中是否存在密钥

> 原文:[https://www . geesforgeks . org/python-test-if-key-exists-in-tuple-keys-dictionary/](https://www.geeksforgeeks.org/python-test-if-key-exists-in-tuple-keys-dictionary/)

有时，在处理字典数据时，我们需要检查字典中是否存在特定的键。如果键是初等的，那么问题的解决方案在讨论中更容易解决。但是有时候，我们可以用元组作为字典的关键字。让我们讨论执行这项任务的某些方法。

**方法#1:使用`any()` +生成器表达式**

上述功能的组合可用于执行该任务。在这种情况下，我们检查目标键的每个键内的每个元素。any()用于检入字典的任何键。

```
# Python3 code to demonstrate working of
# Test if key exists in tuple keys dictionary
# using any() + generator expression

# initialize dictionary
test_dict = {(4, 5) : '1', (8, 9) : '2', (10, 11) : '3'}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Test key 
key = 10

# Test if key exists in tuple keys dictionary
# using any() + generator expression
res = any(key in sub for sub in test_dict)

# printing result
print("Does key exists in dictionary? : " + str(res))
```

**Output :**

```
The original dictionary : {(4, 5): '1', (8, 9): '2', (10, 11): '3'}
Does key exists in dictionary? : True

```

**方法 2:使用`from_iterable()`**

也可以使用该功能执行该任务。在这种情况下，我们将键展平，然后检查是否存在。

```
# Python3 code to demonstrate working of
# Test if key exists in tuple keys dictionary
# using from_iterable()
from itertools import chain

# initialize dictionary
test_dict = {(4, 5) : '1', (8, 9) : '2', (10, 11) : '3'}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Test key 
key = 10

# Test if key exists in tuple keys dictionary
# using from_iterable()
res = key in chain.from_iterable(test_dict)

# printing result
print("Does key exists in dictionary? : " + str(res))
```

**Output :**

```
The original dictionary : {(4, 5): '1', (8, 9): '2', (10, 11): '3'}
Does key exists in dictionary? : True

```