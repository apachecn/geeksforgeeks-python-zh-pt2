# Python 嵌套词典

> 原文:[https://www.geeksforgeeks.org/python-nested-dictionary/](https://www.geeksforgeeks.org/python-nested-dictionary/)

**先决条件–**[Python 词典](https://www.geeksforgeeks.org/python-dictionary/)

Python 中的字典的工作方式类似于现实世界中的字典。字典的键必须是唯一的并且是不可变的数据类型，例如字符串、整数和元组，但是键值可以重复并且是任何类型。

**嵌套词典:**嵌套词典就是把一个词典放在另一个词典里面。嵌套非常有用，因为我们可以在程序中建模的信息种类大大扩展了。

```
nested_dict = { 'dict1': {'key_A': 'value_A'},
                'dict2': {'key_B': 'value_B'}}
```

![](img/2c08c89afa97f069699e36a29090c453.png)

```
# As shown in image

# Creating a Nested Dictionary 
Dict = {1: 'Geeks', 2: 'For', 3: {'A' : 'Welcome', 'B' : 'To', 'C' : 'Geeks'}}
```

#### 创建嵌套字典

在 Python 中，嵌套字典可以通过将逗号分隔的字典放在大括号中来创建。

```
# Empty nested dictionary
Dict = { 'Dict1': { }, 
         'Dict2': { }}
print("Nested dictionary 1-")
print(Dict)

# Nested dictionary having same keys
Dict = { 'Dict1': {'name': 'Ali', 'age': '19'},
         'Dict2': {'name': 'Bob', 'age': '25'}}
print("\nNested dictionary 2-")
print(Dict)

# Nested dictionary of mixed dictionary keys
Dict = { 'Dict1': {1: 'G', 2: 'F', 3: 'G'}, 
         'Dict2': {'Name': 'Geeks', 1: [1, 2]} }
print("\nNested dictionary 3-")
print(Dict)
```

**输出:**

```
Nested dictionary 1-
{'Dict1': {}, 'Dict2': {}}

Nested dictionary 2-
{'Dict1': {'name': 'Ali', 'age': '19'}, 'Dict2': {'name': 'Bob', 'age': '25'}}

Nested dictionary 3-
{'Dict1': {1: 'G', 2: 'F', 3: 'G'}, 'Dict2': {1: [1, 2], 'Name': 'Geeks'}}

```

#### 向嵌套字典添加元素

可以通过多种方式向嵌套词典中添加元素。在嵌套字典中添加字典的一种方法是添加值 one be one，`Nested_dict[dict][key] = 'value'`。另一种方法是一次性添加整个词典，`Nested_dict[dict] = { 'key': 'value'}`。

```
Dict = { }
print("Initial nested dictionary:-")
print(Dict)

Dict['Dict1'] = {}

# Adding elements one at a time 
Dict['Dict1']['name'] = 'Bob'
Dict['Dict1']['age'] = 21
print("\nAfter adding dictionary Dict1")
print(Dict)

# Adding whole dictionary
Dict['Dict2'] = {'name': 'Cara', 'age': 25}
print("\nAfter adding dictionary Dict1")
print(Dict)
```

**输出:**

```
Initial nested dictionary:-
{}

After adding dictionary Dict1
{'Dict1': {'age': 21, 'name': 'Bob'}}

After adding dictionary Dict1
{'Dict1': {'age': 21, 'name': 'Bob'}, 'Dict2': {'age': 25, 'name': 'Cara'}}

```

#### 访问嵌套字典的元素

要访问嵌套字典中任意键的值，请使用索引`[]`语法。

```
# Nested dictionary having same keys
Dict = { 'Dict1': {'name': 'Ali', 'age': '19'},
         'Dict2': {'name': 'Bob', 'age': '25'}}

# Prints value corresponding to key 'name' in Dict1
print(Dict['Dict1']['name'])

# Prints value corresponding to key 'age' in Dict2
print(Dict['Dict2']['age'])
```

**输出:**

```
Ali
25
```

#### 从嵌套词典中删除词典

从嵌套词典中删除词典可以通过使用`del`关键字或使用`pop()`功能来完成。

```
Dict = {'Dict1': {'name': 'Ali', 'age': 19},
        'Dict2': {'name': 'Bob', 'age': 21}}
print("Initial nested dictionary:-")
print(Dict)

# Deleting dictionary using del keyword 
print("\nDeleting Dict2:-")
del Dict['Dict2']
print(Dict)

# Deleting dictionary using pop function
print("\nDeleting Dict1:-")
Dict.pop('Dict1') 
print (Dict)
```

**输出:**

```
Initial nested dictionary:-
{'Dict2': {'name': 'Bob', 'age': 21}, 'Dict1': {'name': 'Ali', 'age': 19}}

Deleting Dict2:-
{'Dict1': {'name': 'Ali', 'age': 19}}

Deleting Dict1:-
{}
```