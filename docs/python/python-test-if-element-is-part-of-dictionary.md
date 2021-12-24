# Python–测试元素是否是字典的一部分

> 原文:[https://www . geesforgeks . org/python-test-if-element-is-part-dictionary/](https://www.geeksforgeeks.org/python-test-if-element-is-part-of-dictionary/)

给定一个字典，测试 K 是否是字典的键或值的一部分。

> **输入**:test _ dict = {“Gfg”:1、“is”:3、“Best”:2 }、K =“Best”
> **输出** : True
> **解释**:“Best”作为 Key 出现在字典中。
> 
> **输入**:test _ dict = {“Gfg”:1、“is”:3、“Best”:2 }、K =“Geeks”
> **输出** : False
> **解释**:“Geeks”作为 Key 不在字典中。

**方法#1:使用任意()+ items() +生成器表达式**

上述功能的组合可以用来解决这个问题。在本例中，我们使用 any()检查任何元素，items()用于提取字典的所有键和值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Test if element is part of dictionary
# Using any() + generator expression + items()

# initializing dictionary
test_dict = {"Gfg" : 1, "is" :  3, "Best" : 2}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = "Gfg"

# using any() to check for both keys and values 
res = any(K == key or K == val for key, val in test_dict.items())

# printing result 
print("Is K present in dictionary? : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': 1, 'is': 3, 'Best': 2}
Is K present in dictionary? : True

```

**方法 2:使用 chain . from _ iterables()+items()**

上述功能的组合可以用来解决这个问题。在这种情况下，我们展平所有项目，然后检查是否存在 K 是任何项目()。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Test if element is part of dictionary
# Using chain.from_iterables() + items()
from itertools import chain

# initializing dictionary
test_dict = {"Gfg" : 1, "is" :  3, "Best" : 2}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = "Gfg"

# flattening key-values and then checking
# using in operator
res = K in chain.from_iterable(test_dict.items())

# printing result 
print("Is K present in dictionary? : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': 1, 'is': 3, 'Best': 2}
Is K present in dictionary? : True

```