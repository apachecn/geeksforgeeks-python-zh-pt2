# Python |测试元素是否为字典值

> 原文:[https://www . geesforgeks . org/python-test-if-element-is-dictionary-value/](https://www.geeksforgeeks.org/python-test-if-element-is-dictionary-value/)

有时候，在使用 Python 字典时，我们有一个特定的用例，在这个用例中，我们只需要找到字典中是否存在某个特定的值，因为它是任何键的值。这可以在你能想到的任何编程领域中有用例。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用循环**
这是解决这个问题的蛮法。在本文中，我们使用循环遍历整个字典，并使用条件语句检查每个键的值是否匹配。

```py
# Python3 code to demonstrate working of
# Test if element is dictionary value
# Using loops

# initializing dictionary
test_dict = {'gfg' : 1, 'is' : 2, 'best' : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Test if element is dictionary value
# Using loops
res = False
for key in test_dict:
    if(test_dict[key] == 3):
        res = True 
        break

# printing result
print("Is 3 present in dictionary : " + str(res))
```

**Output :**

```py
The original dictionary is : {'best': 3, 'is': 2, 'gfg': 1}
Is 3 present in dictionary : True

```