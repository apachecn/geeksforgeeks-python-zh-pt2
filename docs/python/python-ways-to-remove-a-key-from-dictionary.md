# Python |从字典中移除密钥的方法

> 原文:[https://www . geesforgeks . org/python-从字典中移除密钥的方法/](https://www.geeksforgeeks.org/python-ways-to-remove-a-key-from-dictionary/)

[字典](https://www.geeksforgeeks.org/python-dictionary/)在日常编程、web 开发、AI/ML 编程等多种实际应用中都有使用，整体来说是一个有用的容器。因此，了解人手不足以完成与词典使用相关的不同任务总是一个优势。本文讨论了从字典中删除字典键值对的任务。

**方法一:使用`del`**

`del`关键字可用于就地删除字典中存在的关键字。使用这种方法的一个缺点是，如果找不到密钥，就会引发异常，因此必须处理密钥不存在的问题。

**代码#1 :** 使用`del`演示键值对删除

```py
# Python code to demonstrate
# removal of dict. pair 
# using del

# Initializing dictionary
test_dict = {"Arushi" : 22, "Anuradha" : 21, "Mani" : 21, "Haritha" : 21}

# Printing dictionary before removal
print ("The dictionary before performing remove is : " + str(test_dict))

# Using del to remove a dict
# removes Mani
del test_dict['Mani']

# Printing dictionary after removal
print ("The dictionary after remove is : " + str(test_dict))

# Using del to remove a dict
# raises exception
del test_dict['Manjeet']
```

**输出:**

```py
The dictionary before performing remove is : {'Anuradha': 21, 'Haritha': 21, 'Arushi': 22, 'Mani': 21}
The dictionary after remove is : {'Anuradha': 21, 'Haritha': 21, 'Arushi': 22}

```

例外:

```py
Traceback (most recent call last):
  File "/home/44db951e7011423359af4861d475458a.py", line 20, in 
    del test_dict['Manjeet']
KeyError: 'Manjeet'

```

**方法二:使用`pop()`**

**pop()** 可以用来删除某个键及其在原地的值。使用`del`的优势在于，如果试图删除不存在的字典，它提供了打印所需值的机制。配对。其次，除了执行简单的删除操作之外，它还返回要删除的键的值。

**代码#2 :** 使用`pop()`
演示键值对删除

```py
# Python code to demonstrate
# removal of dict. pair 
# using pop()

# Initializing dictionary
test_dict = {"Arushi" : 22, "Anuradha" : 21, "Mani" : 21, "Haritha" : 21}

# Printing dictionary before removal
print ("The dictionary before performing remove is : " + str(test_dict))

# Using pop() to remove a dict. pair
# removes Mani
removed_value = test_dict.pop('Mani')

# Printing dictionary after removal
print ("The dictionary after remove is : " + str(test_dict))
print ("The removed key's value is : " + str(removed_value))

print ('\r')

# Using pop() to remove a dict. pair
# doesn't raise exception
# assigns 'No Key found' to removed_value
removed_value = test_dict.pop('Manjeet', 'No Key found')

# Printing dictionary after removal
print ("The dictionary after remove is : " + str(test_dict))
print ("The removed key's value is : " + str(removed_value))
```

**输出:**

```py
The dictionary before performing remove is : {'Arushi': 22, 'Anuradha': 21, 'Mani': 21, 'Haritha': 21}
The dictionary after remove is : {'Arushi': 22, 'Anuradha': 21, 'Haritha': 21}
The removed key's value is : 21

The dictionary after remove is : {'Arushi': 22, 'Anuradha': 21, 'Haritha': 21}
The removed key's value is : No Key found

```

**方法三:使用 `items()` +字典理解**

`items()`结合 dict 理解也可以帮助我们完成键值对删除的任务，但是它有不是原地 dict 的缺点。技术。实际上，除了我们不希望包含的密钥之外，如果创建了新的字典。

**代码#3 :** 使用`items()` +字典演示键值对删除。领悟

```py
# Python code to demonstrate
# removal of dict. pair 
# using items() + dict comprehension

# Initializing dictionary
test_dict = {"Arushi" : 22, "Anuradha" : 21, "Mani" : 21, "Haritha" : 21}

# Printing dictionary before removal
print ("The dictionary before performing remove is : " + str(test_dict))

# Using items() + dict comprehension to remove a dict. pair
# removes Mani
new_dict = {key:val for key, val in test_dict.items() if key != 'Mani'}

# Printing dictionary after removal
print ("The dictionary after remove is : " + str(new_dict))
```

**输出:**

```py
The dictionary before performing remove is : {'Anuradha': 21, 'Haritha': 21, 'Arushi': 22, 'Mani': 21}
The dictionary after remove is : {'Anuradha': 21, 'Haritha': 21, 'Arushi': 22}

```