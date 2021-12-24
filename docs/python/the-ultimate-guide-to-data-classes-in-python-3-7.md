# Python 3.7 中数据类的终极指南

> 原文:[https://www . geesforgeks . org/python 中数据类的终极指南-3-7/](https://www.geeksforgeeks.org/the-ultimate-guide-to-data-classes-in-python-3-7/)

本文讨论 Python 3.7 中的数据类，并为 Python 3.7 及更高版本中的数据类提供介绍性指南。

[数据类](https://www.geeksforgeeks.org/data-classes-in-python-an-introduction/)是 Python 3.7 版本引入的新概念。您不仅可以将数据类用作知识容器，还可以为您编写锅炉板代码，并简化创建类的过程，因为它附带了一些免费实现的方法。数据类也可以被认为是一个通常包含数据的类别，但它们并不仅限于此。

## 基本数据类

以下方式显示了如何创建基本数据类:

**1。使用装饰器:**它们是使用新的 **@dataclass** [装饰器创建的。](https://www.geeksforgeeks.org/decorators-in-python/)

**例:**

## 蟒 3

```
# import package
from dataclasses import dataclass

# make a dataclass with decorator
@dataclass
class DataClassGFG:
    Job: str
    Salary: float

# make an object with values required by dataclass
DataClassObject = DataClassGFG("Author",50000.00)

# view dataclass object
print(DataClassObject)
```

**输出:**

> DataClassGFG(Job= '作者'，薪资=50000.0)

**2。使用 make_dataclass():**

**例:**

## 蟒 3

```
# import package
from dataclasses import make_dataclass

# make a dataclass with make_dataclass

DataClassGFG = make_dataclass("DataClassGFG",["Job","Salary"])

# make an object with values required by dataclass
DataClassObject = DataClassGFG("Author",50000.00)

# view dataclass object
print(DataClassObject)
```