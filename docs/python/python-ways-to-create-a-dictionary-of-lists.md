# Python |创建列表字典的方法

> 原文:[https://www . geesforgeks . org/python-创建列表词典的方法/](https://www.geeksforgeeks.org/python-ways-to-create-a-dictionary-of-lists/)

到目前为止，我们已经看到了在[字典](https://www.geeksforgeeks.org/python-dictionary/)中，通过多种方式和对键和值的不同操作来创建[字典](https://www.geeksforgeeks.org/python-dictionary/)的方法。现在，让我们看看创建列表字典的不同方法。

请注意，Python 字典中对键的限制是只有不可变的数据类型才能用作键，这意味着我们不能将列表字典用作`key`。

```py
# Creating a dictionary
myDict = {[1, 2]: 'Geeks'}

print(myDict)
```

**输出:**

```py
TypeError: unhashable type: 'list'
```

但是用字典中的`values` 也可以非常明智地做到这一点。让我们看看创建列表字典的所有不同方法。

**方法#1:** 使用下标

```py
# Creating an empty dictionary
myDict = {}

# Adding list as value
myDict["key1"] = [1, 2]
myDict["key2"] = ["Geeks", "For", "Geeks"] 

print(myDict)
```

**输出:**

```py
{'key2': ['Geeks', 'For', 'Geeks'], 'key1': [1, 2]}
```

**方法#2:** 使用 append()方法将嵌套列表作为值添加。

创建一个新列表，我们可以简单地将该列表附加到值中。

```py
# Creating an empty dictionary
myDict = {}

# Adding list as value
myDict["key1"] = [1, 2]

# creating a list
lst = ['Geeks', 'For', 'Geeks']

# Adding this list as sublist in myDict
myDict["key1"].append(lst)

print(myDict)
```

**输出:**

```py
{'key1': [1, 2, ['Geeks', 'For', 'Geeks']]}
```

**方法#3:** 使用`setdefault()`方法

使用`setdefault()`方法迭代列表并继续添加元素直到给定范围。

```py
# Creating an empty dict
myDict = dict()

# Creating a list
valList = ['1', '2', '3']

# Iterating the elements in list
for val in valList:
    for ele in range(int(val), int(val) + 2): 
        myDict.setdefault(ele, []).append(val)

print(myDict)
```

**输出:**

```py
{1: ['1'], 2: ['1', '2'], 3: ['2', '3'], 4: ['3']}
```

**方法#4:** 使用列表理解

```py
# Creating a dictionary of lists
# using list comprehension
d = dict((val, range(int(val), int(val) + 2))
                  for val in ['1', '2', '3'])

print(d)
```

**输出:**

```py
{'1': [1, 2], '3': [3, 4], '2': [2, 3]}
```

**方法 5:** 使用默认值

请注意，同样的事情也可以用简单的字典来完成，但是使用`defaultdict` 在这种情况下更有效。

```py
# Importing defaultdict
from collections import defaultdict

lst = [('Geeks', 1), ('For', 2), ('Geeks', 3)]
orDict = defaultdict(list)

# iterating over list of tuples
for key, val in lst:
    orDict[key].append(val)

print(orDict)
```

**输出:**

```py
defaultdict(, {'For': [2], 'Geeks': [1, 3]})
```

请注意，输出字典中只有两个`key:value`对，但输入列表包含三个元组。第一个元素(即`key`)对于第一个和第三个元组是相同的，两个键永远不能相同。

**方法 6:** 使用 Json

```py
#importing json
import json

#Initialisation of list
lst = [('Geeks', 1), ('For', 2), ('Geeks', 3)]

#Initialisation of dictionary
dict = {}

#using json.dump()
hash = json.dumps(lst)

#creating a hash
dict[hash] = "converted"

#Printing dictionary
print(dict)

#Added by Paras Jain(everythingispossible)
```

**输出:**

```py
{'[["Geeks", 1], ["For", 2], ["Geeks", 3]]': 'converted'}
```