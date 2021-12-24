# Python |值列表联盟

> 原文:[https://www.geeksforgeeks.org/python-union-of-value-lists/](https://www.geeksforgeeks.org/python-union-of-value-lists/)

联合的功能已经被讨论过很多次了。但是有时，我们可以有一个更复杂的容器，在其中我们需要检查以字典关键字形式出现的列表的联合。让我们讨论解决这类问题的某些方法。

**方法#1:使用循环**
使用循环是执行这一特定任务的一种天真的蛮力方法。在这种方法中，我们检查两个列表中的键，并检查要添加到结果中的非重复值。我们甚至检查在其他中完全不存在的键来添加它的整个列表值。

```py
# Python3 code to demonstrate
# Union of Value Lists
# using loops

# initializing dicts
test_dict1 = { "Key1" : [1, 3, 4], "key2" : [4, 5] }
test_dict2 = { "Key1" : [1, 7, 8] }

# printing original dicts
print("The original dict 1 : " + str(test_dict1))
print("The original dict 2 : " + str(test_dict2))

# using loops
# Union of Value Lists
for key in test_dict1: 
    if key in test_dict2: 
        for val in test_dict1[key]:
            if val not in test_dict2[key]:  
                test_dict2[key].append(val)
    else: 
        test_dict2[key] = test_dict1[key][:]

# print result
print("The dicts after union is : " + str(test_dict2))
```

**Output :**

```py
The original dict 1 : {'Key1': [1, 3, 4], 'key2': [4, 5]}
The original dict 2 : {'Key1': [1, 7, 8]}
The dicts after union is : {'Key1': [1, 7, 8, 3, 4], 'key2': [4, 5]}

```