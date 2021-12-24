# Python 元类

> 原文:[https://www.geeksforgeeks.org/python-metaclasses/](https://www.geeksforgeeks.org/python-metaclasses/)

python 的关键概念是对象。python 中几乎所有的东西都是对象，包括函数和类。因此，函数和类可以作为参数传递，可以作为实例存在，等等。最重要的是，对象的概念让类在生成其他类。

生成其他类的类被定义为元类。在本节中，我们将讨论元类的概念以及使用它们的具体方法。在本节中，我们将涵盖以下主题:

*   type
*   Write metaclass
*   Meta use case

## 类型

一个类定义了它的对象的属性和可用的动作，并且它还充当了对象创建的工厂。让我们通过直接使用类型创建一个类来理解这个过程。用于类实例化的确切类称为类型。通常，我们使用一种称为*类关键字*的特殊语法来定义一个类，但是这种语法是*类型类*的替代。让我们用一个例子来说明:

首先，我们研究使用*类关键字*创建类的场景。我们来查一下下面的代码:

T5】python 3T7

```
class FoodType(object):
  def __init__(self, ftype):
    self.ftype = ftype

  def getFtype(self):
    return self.ftype

def main():
  fType = FoodType(ftype = 'Vegetarian')
  print(fType.getFtype())

main()
```

T8T10**输出**T1

在这里，我们使用*类*关键字创建了一个名为 *FoodType* 的类。这个*类*关键字充当类型语法的替代。现在我们来看看，如何使用 *typ* e 关键字。下面我们来看下代码:

## python 3

```
def init(self, ftype):
    self.ftype = ftype

def getFtype(self):
    return self.ftype 

FoodType = type('FoodType', (object, ), {
    '__init__': init,
    'getFtype' : getFtype,
    })

fType = FoodType(ftype ='Vegetarian')
print(fType.getFtype())
```

**输出**

```
Vegetarian

```

让我们关注*类型*。它有三个参数，如下所示:

*   The first parameter is a string- *foodtype* . The string is specified as the class name.
*   The second parameter is a tuple- *(object),* . This shows that the *foodtype* class inherits from the object class. Here, trailing commas help python interpreter identify them as tuples.
*   Here, the third parameter is a dictionary that refers to the attributes of the class. In this case, the class has two methods- *init* and *getftype.*

### 使用类型创建子类

让我们看看创建子类的正常场景，即使用 class 关键字。在这里，我们将创建一个子类*蔬菜类型*，其中主类是*食物类型*。

## python 3

```
class FoodType(object):
  def __init__(self, ftype):
    self.ftype = ftype

  def getFtype(self):
    return self.ftype

class VegType(FoodType):
  def vegFoods(self):
    return {'Spinach', 'Bitter Guard'}

def main():
  vType = VegType(ftype = 'Vegetarian')
  print(vType.getFtype())
  print(vType.vegFoods())

main()
```

**输出**

```
Vegetarian
{'Spinach', 'Bitter Guard'}

```

现在让我们看看如何使用*类型*转换上面的代码。对于 *FoodType* 类，*类型*的第二个参数是对象类——超类，即 *FoodType* 是对象类的子类。同样的， *VegType* 类是 *FoodType* 的子类，因此在创建 *VegType* 类时，*类型*的第二个参数是指 *FoodType* 类。

## 蟒蛇 3

```
def init(self, ftype):
    self.ftype = ftype

def getFtype(self):
    return self.ftype 

FoodType = type('FoodType', (object, ), {
    '__init__': init,
    'getFtype' : getFtype,
    })

def vegFoods(self):
    return {'Spinach', 'Bitter Guard'}

## creating subclass using type
VegType = type('VegType', (FoodType, ), {
    'vegFoods' : vegFoods,
    })

vType = VegType(ftype ='Vegetarian')
print(vType.getFtype())
print(vType.vegFoods())
```

**Output**

```
Vegetarian
{'Spinach', 'Bitter Guard'}

```

## 编写元类

元类是直接从类型继承的类。自定义元类应该实现的方法是 __new__ 方法。元类的 __new__ 方法中提到的参数反映在类型类的 __new__ 方法中。它有四个位置参数。它们如下:

1.  The first parameter is the metaclass itself.
2.  The second argument is the class name.
3.  The third parameter is superclass (in the form of tuple)
4.  The fourth parameter is the property of the class (in the form of a dictionary).

让我们看看下面的代码。

T3】蟒 3T5

```
class MetaCls(type):
    """A sample metaclass without any functionality"""
    def __new__(cls, clsname, superclasses, attributedict):
        print("clsname:", clsname)
        print("superclasses:", superclasses)
        print("attrdict:", attributedict)
        return super(MetaCls, cls).__new__(cls, \
                       clsname, superclasses, attributedict)

C = MetaCls('C', (object, ), {})
print("class type:", type(C))
```

T6T8**输出**T1

你可以注意到 C 类的类型是一个元类–*元类*。让我们检查一下普通类的类型。

T5】蟒 3T7

```
class S(object):
  pass

print(type(S))
```

T8T10**输出**T1

### 元类继承

让我们看看，如何从元类继承。

## 蟒 3

```
class MetaCls(type):
    """A sample metaclass without any functionality"""
    def __new__(cls, clsname, supercls, attrdict):

        return super(MetaCls, cls).__new__(cls, clsname, supercls, attrdict)

C = MetaCls('C', (object, ), {})
## class A inherits from MetaCls       
class A(C):
  pass

print(type(A))
```

**输出**

```
<class '__main__.MetaCls'>

```

在这种情况下，您可以看到类 A 是元类的一个实例。这是因为它的超类 C 是元类的一个实例。现在我们将考虑这样的场景，其中类子类有两个或更多不同的类。让我们来看看下面的示例代码:

## python 3

```
class MetaCls(type):
    """A sample metaclass without any functionality"""
    def __new__(cls, clsname, supercls, attrdict):

        return super(MetaCls, cls).__new__(cls, clsname, supercls, attrdict)

## a class of the type metclass
A = MetaCls('A', (object, ), {})
print('Type of class A:', type(A))

class B(object):
    pass
print('Type of class B:', type(B))

## class C inherits from both the class, A and B
class C(A, B):
    pass
print('Type of class C:', type(C))
```

输出

```
Type of class A: <class '__main__.MetaCls'>
Type of class B: <class 'type'>
Type of class C: <class '__main__.MetaCls'>

```