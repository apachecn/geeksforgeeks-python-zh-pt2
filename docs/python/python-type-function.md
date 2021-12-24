# Python 中的 type()函数

> 原文:[https://www.geeksforgeeks.org/python-type-function/](https://www.geeksforgeeks.org/python-type-function/)

`**type()**`方法返回作为参数传递的参数(对象)的类类型。type()函数主要用于调试目的。

两种不同类型的参数可以传递给 type()函数，单参数和三参数。如果传递单个参数`type(obj)`，则返回给定对象的类型。如果传递三个参数`type(name, bases, dict)`，则返回一个新的类型对象。

**语法:**

```
type(object)
type(name, bases, dict)
```

> **参数:**
> 
> **名称:**类的名称，后面对应该类的 __name__ 属性。
> **base:**当前类从中派生的类的元组。Later 对应于 _ _ bases _ _ 属性。
> **字典:**保存类的名称空间的字典。Later 对应于 __dict__ 属性。

**返回类型:**

```
returns a new type class or essentially a metaclass.
```

**代码#1 :**

```
# Python3 simple code to explain
# the type() function
print(type([]) is list)

print(type([]) is not list)

print(type(()) is tuple)

print(type({}) is dict)

print(type({}) is not list)
```

**输出:**

```
True
False
True
True
True
```

**代码#2 :**

```
# Python3 code to explain
# the type() function

# Class of type dict
class DictType:
    DictNumber = {1:'John', 2:'Wick',
                  3:'Barry', 4:'Allen'}

    # Will print the object type
    # of existing class
    print(type(DictNumber))

# Class of type list    
class ListType:
    ListNumber = [1, 2, 3, 4, 5]

    # Will print the object type
    # of existing class
    print(type(ListNumber))

# Class of type tuple    
class TupleType:
    TupleNumber = ('Geeks', 'for', 'geeks')

    # Will print the object type
    # of existing class
    print(type(TupleNumber))

# Creating object of each class    
d = DictType()
l = ListType()
t = TupleType()
```

**输出:**

```
<class 'dict'>
<class 'list'>
<class 'tuple'>
```

**代码#3 :**

```
# Python3 code to explain
# the type() function

# Class of type dict
class DictType:
    DictNumber = {1:'John', 2:'Wick', 3:'Barry', 4:'Allen'}

# Class of type list    
class ListType:
    ListNumber = [1, 2, 3, 4, 5]

# Creating object of each class   
d = DictType()
l = ListType()

# Will print accordingly whether both
# the objects are of same type or not  
if type(d) is not type(l):
    print("Both class have different object type.")
else:
    print("Same Object type")
```

**输出:**

```
Both class have different object type.
```

**代码#4 :** 使用`type(name, bases, dict)`

```
# Python3 program to demonstrate
# type(name, bases, dict)

# New class(has no base) class with the
# dynamic class initialization of type()
new = type('New', (object, ),
      dict(var1 ='GeeksforGeeks', b = 2009))

# Print type() which returns class 'type'
print(type(new))
print(vars(new))

# Base class, incorporated
# in our new class
class test:
    a = "Geeksforgeeks"
    b = 2009

# Dynamically initialize Newer class
# It will derive from the base class test
newer = type('Newer', (test, ),
        dict(a ='Geeks', b = 2018))

print(type(newer))
print(vars(newer))
```

**输出:**

```
{'__module__': '__main__', 'var1': 'GeeksforGeeks', '__weakref__': , 'b': 2009, '__dict__': <attribute of="" objects="">, '__doc__': None}

{'b': 2018, '__doc__': None, '__module__': '__main__', 'a': 'Geeks'}</attribute> 
```

**应用:**

*   **type()** 功能基本用于调试目的。当使用其他字符串函数时。上()，。下()，。split()使用从网络爬虫提取的文本，它可能不起作用，因为它们可能是不支持字符串函数的不同类型。并且结果会不断抛出错误，非常难调试*【把错误看成:GeneratorType 没有属性 low()】*。 **type()** 函数可以在这一点上使用，以确定提取的文本类型，然后在我们对其使用字符串函数或任何其他操作之前，将其更改为其他形式的字符串。
*   **带有三个参数的 type()** 可用于动态初始化类或带有属性的现有类。它也用于用 SQL 注册数据库表。