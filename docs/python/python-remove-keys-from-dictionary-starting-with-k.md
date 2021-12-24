# Python |从字典中删除以 K 开头的键

> 原文:[https://www . geesforgeks . org/python-remove-key-from-dictionary-以-k 开头/](https://www.geeksforgeeks.org/python-remove-keys-from-dictionary-starting-with-k/)

有时，在使用字典时，我们可能会遇到需要移除某些键的特定用例。我们可能需要根据许多标准来执行这项任务。一个这样的标准可以是基于起始子串的移除。让我们讨论执行这项任务的某些方法。

**方法#1:使用 Naive 方法+ `startswith() + pop()`**
这个特定的任务可以使用上述函数的组合来执行，这是一个执行这个任务的蛮力方法。`pop`功能用于删除键值对，`startswith`提供必须执行该操作的条件。

```
# Python3 code to demonstrate working of
# Remove Keys from dictionary starting with K
# Using Naive Method + startswith() + pop()

# initializing dictionary
test_dict = {"Apple" : 1, "Star" : 2, "App" : 4, "Gfg" : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing Substring 
K = "Ap"

# Using Naive Method + startswith() + pop()
# Remove Keys from dictionary starting with K
res = list(test_dict.keys())
for key in res:
  if key.startswith(K):
    test_dict.pop(key)

# printing result 
print("Dictionary after key removal : " + str(test_dict))
```

**Output :**

```
The original dictionary is : {'Apple': 1, 'Star': 2, 'App': 4, 'Gfg': 3}
Dictionary after key removal : {'Star': 2, 'Gfg': 3}

```