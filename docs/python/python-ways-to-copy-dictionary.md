# Python |复制字典的方法

> 原文:[https://www . geesforgeks . org/python-复制方式-字典/](https://www.geeksforgeeks.org/python-ways-to-copy-dictionary/)

是一部无序、多变、索引化的集子。在 Python 中，字典是用花括号写的，它们有键和值。它广泛用于日常编程、web 开发和机器学习。当我们简单地指定 dict1 = dict2 时，它指的是同一个字典。让我们讨论几个从另一个字典复制字典的方法。

**方法#1:使用`copy()`**
`copy()`方法返回字典的一个[浅拷贝](https://www.geeksforgeeks.org/copy-python-deep-copy-shallow-copy/)。
不取任何参数，返回一个不引用初始词典的新词典。

```
# Python3 code to demonstrate
# how to copy dictionary
# using copy() function

# initialising dictionary
test1 = {"name" : "akshat", "name1" : "manjeet", "name2" : "vashu"}

# method to copy dictionary using copy() function
test2 = test1.copy()

# updating test2
test2["name1"] ="nikhil"

# print initial dictionary
print("initial dictionary = ", test1)

# printing updated dictionary
print("updated dictionary = ", test2)
```

**输出**

```
initial dictionary =  {'name1': 'manjeet', 'name2': 'vashu', 'name': 'akshat'}
updated dictionary =  {'name1': 'nikhil', 'name': 'akshat', 'name2': 'vashu'}

```

**方法 2:使用`dict()`**
`dict()`是一个用 Python 创建字典的构造器。

```
# Python3 code to demonstrate
# how to copy dictionary
# using dict()

# initialising dictionary
test1 = {"name" : "akshat", "name1" : "manjeet", "name2" : "vashu"}

# method to copy dictionary using dict
test2 = dict(test1)

# updating test2
test2["name1"] ="nikhil"

# print initial dictionary
print("initial dictionary = ", test1)

# printing updated dictionary
print("updated dictionary = ", test2)
```

**输出**

```
initial dictionary =  {'name2': 'vashu', 'name': 'akshat', 'name1': 'manjeet'}
updated dictionary =  {'name2': 'vashu', 'name': 'akshat', 'name1': 'nikhil'}

```

**方法三:利用词典理解**

```
# Python3 code to demonstrate
# how to copy dictionary
# using dictionary comprehension

# initialising dictionary
test1 = {"name" : "akshat", "name1" : "manjeet", "name2" : "vashu"}

# method to copy dictionary using dictionary comprehension
test2 = {k:v for k, v in test1.items()}

# updating test2
test2["name1"] ="ayush"

# print initial dictionary
print("initial dictionary = ", test1)

# printing updated dictionary
print("updated dictionary = ", test2)
```

**输出**

```
initial dictionary =  {'name': 'akshat', 'name2': 'vashu', 'name1': 'manjeet'}
updated dictionary =  {'name': 'akshat', 'name2': 'vashu', 'name1': 'ayush'}

```