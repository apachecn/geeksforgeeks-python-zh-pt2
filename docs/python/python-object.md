# Python 对象

> 原文:[https://www.geeksforgeeks.org/python-object/](https://www.geeksforgeeks.org/python-object/)

一个**对象**是一个类的实例。一个类就像一个蓝图，而一个实例是一个有实际值的类的副本。Python 是面向对象的编程语言，它强调对象，即它主要强调函数。对象基本上是将数据变量和作用于该数据的方法封装成一个实体。
**注:**更多信息， [Python 类和对象](https://www.geeksforgeeks.org/python-classes-and-objects/)

## 对客体的理解

为了更好地理解对象的概念，考虑一个例子，你们中的许多人都玩过 CLASH OF CLANS，所以让我们假设基础布局是包含所有建筑、防御、资源等的类。基于这些描述，我们制作了一个村庄，这里的村庄是对象。
**语法:**

```
obj = MyClass()
print(obj.x)
```

**实例**定义表示存储变量实际数据所需的内存分配。每次创建类的对象时，都会创建该类中定义的每个数据变量的副本。用简单的语言，我们可以说一个类的每个对象都有它自己的在那个类中定义的数据成员的副本。

## 创建对象

## 蟒蛇 3

```
class Cars:
  def __init__(self, m, p):
    self.model = m
    self.price = p

Audi = Cars("R8", 100000)

print(Audi.model)
print(Audi.price)
```

**输出:**

```
R8
100000
```

**程序工作:**
奥迪=汽车():

*   在堆上分配一块内存。分配的内存大小由该类(Cars)中可用的属性和方法决定。
*   内存块分配后，内部调用特殊方法 [__init__](https://www.geeksforgeeks.org/__init__-in-python/) ()进行调用。初始数据通过这种方法存储到变量中。
*   实例的已分配内存地址的位置被返回到对象(Cars)中。
*   记忆位置传递给[自身](https://www.geeksforgeeks.org/self-in-python-class/)。

**使用对象访问类成员:**
类的变量和方法可以通过使用类对象或实例来访问。
**语法:**

```
obj_name.var_name
Audi.model

obj_name.method_name()
Audi.ShowModel();

obj_name.method_name(parameter_list)
Audi.ShowModel(100);
```

**例 1:**

## 蟒蛇 3

```
# Python program to create instance
# variables inside methods

class Car:

    # Class Variable
    vehicle = 'car'   

    # The init method or constructor
    def __init__(self, model):

        # Instance Variable
        self.model = model            

    # Adds an instance variable
    def setprice(self, price):
        self.price = price

    # Retrieves instance variable    
    def getprice(self):    
        return self.price    

# Driver Code
Audi = Car("R8")
Audi.setprice(1000000)
print(Audi.getprice())
```

**输出:**

```
1000000
```

**例 2:**

## 蟒蛇 3

```
class Car:

    # Class Variable
    vehicle = 'Car'           

    # The init method or constructor
    def __init__(self, model, price):

        # Instance Variable    
        self.model = model
        self.price = price        

# Objects of class
Audi = Car("R8", 100000)
BMW = Car("I8", 10000000)

print('Audi details:')
print('Audi is a', Audi.vehicle)
print('Model: ', Audi.model)
print('price: ', Audi.price)

print('\n BMW details:')
print('BMW is a', BMW.vehicle)
print('Model: ', BMW.model)
print('Color: ', BMW.price)

# Class variables can be
# accessed using class
# name also
print("\nAccessing class variable using class name")
print(Car.audi)        
```

**输出:**

```
Audi details:
Audi is a Car
Model:  R8
price:  100000

 BMW details:
BMW is a Car
Model:  I8
Color:  10000000

Accessing class variable using class name
Car
```

**Self 变量:**
SELF 是默认变量，包含当前对象的内存地址。自变量可以引用实例变量和方法。创建类的对象时，对象的内存位置由其对象名包含。这个内存位置在内部传递给 SELF，因为 SELF 知道对象的内存地址，所以对象的变量和方法是可访问的。任何对象方法的第一个参数都是 SELF，因为第一个参数总是对象引用。无论你是否调用，这个过程都会自动发生。
**例:**

## 蟒蛇 3

```
class Test:
  def __init__(Myobject, a, b):
    Myobject.country = a
    Myobject.capital = b

  def myfunc(abc):
    print("Capital of  " + abc.country +" is:"+abc.capital)

x = Test("India", "Delhi")
x.myfunc()
```

**输出**T2】

```
Capital of India is: Delhi
```

**注意:**更多信息请参考 Python 类中的[self](https://www.geeksforgeeks.org/self-in-python-class/)
**删除对象:**
可以使用 del 关键字删除对象属性:
**语法:**

```
del obj_name.property
```

也可以通过 del 关键字删除对象:
**语法:**

```
del obj_name
```