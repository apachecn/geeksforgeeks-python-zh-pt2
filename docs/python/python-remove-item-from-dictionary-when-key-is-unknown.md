# Python |当关键字未知时从字典中删除项目

> 原文:[https://www . geesforgeks . org/python-当密钥未知时从字典中删除项目/](https://www.geeksforgeeks.org/python-remove-item-from-dictionary-when-key-is-unknown/)

**[【词典】](https://www.geeksforgeeks.org/python-dictionary/)** 是一个无序、多变、有索引的集合。在 Python 中，字典是用花括号写的，它们有键和值。它广泛用于日常编程、web 开发和机器学习。

让我们讨论当关键字未知时从字典中删除项目的各种方法。

**方法#1 :** 使用幼稚+ `del`

`del`关键字可用于就地删除字典中存在的关键字。使用这种方法的一个缺点是，如果找不到密钥，就会引发异常，因此必须处理密钥不存在的问题。

```py
# Python code to demonstrate how to remove 
# an item from the dictionary without knowing 
# a key using naive + del method

# Initialising dictionary
test1 = {"akshat" : 21, "nikhil" : 22, "akash" : 23, "manjeet" : 27}

# Printing dictionary before removal 
print ("Original Dictionary : " + str(test1))

# using naive + del method
# remove key nikhil
item_to_remove = 23

for key, item in test1.items():
    if item is item_to_remove:
        del test1[key]
        break

# Printing dictionary after removal 
print ("Dictionary after remove is : " + str(test1))
```

**Output:**

```py
Original Dictionary : {'akshat': 21, 'manjeet': 27, 'nikhil': 22, 'akash': 23}
Dictionary after remove is : {'akshat': 21, 'manjeet': 27, 'nikhil': 22}

```

**方法二:**利用字典理解。

```py
# Python code to demonstrate how to remove 
# item from dictionary without knowing key
# using dictionary comprehension

# Initialising dictionary
test1 = {"akshat" : 21, "nikhil" : 22, "akash" : 23, "manjeet" : 27}

# Printing dictionary before removal 
print ("Original Dictionary : " + str(test1))

# using dictionary comprehension method
# remove key akash
value_to_remove = 23

res = {key: value for key, value in test1.items() 
             if value is not value_to_remove}

# Printing dictionary after removal 
print ("Dictionary after remove is : " + str(res))
```

**Output:**

```py
Original Dictionary : {'nikhil': 22, 'akash': 23, 'akshat': 21, 'manjeet': 27}
Dictionary after remove is : {'nikhil': 22, 'manjeet': 27, 'akshat': 21}

```

**方法三:**使用幼稚+ `pop()` +幼稚

Python 语言为几乎所有容器指定了`pop()`，无论是列表、集合等。

```py
# Python code to demonstrate how to remove
# item from dictionary without knowing key
# using naive + pop()

# Initialising dictionary
test1 = {"akshat" : 21, "nikhil" : 22, "akash" : 23, "manjeet" : 27}

# Printing dictionary before removal 
print ("Original dictionary : " + str(test1))

# using naive + pop()
# remove key akash
value_to_remove = 23

for key in test1.keys():
    if test1[key] == value_to_remove:
        test1.pop(key)
        break

# Printing dictionary after removal 
print ("Dictionary after remove is : " + str(test1))
```

**Output:**

```py
Original dictionary : {'manjeet': 27, 'nikhil': 22, 'akshat': 21, 'akash': 23}
Dictionary after remove is : {'manjeet': 27, 'nikhil': 22, 'akshat': 21}

```