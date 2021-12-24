# Python 属性()函数

> 原文:[https://www.geeksforgeeks.org/python-property-function/](https://www.geeksforgeeks.org/python-property-function/)

**Python 属性()函数**返回属性类的对象，用于创建类的属性。

> **语法:**属性(fget，fset，fdel，doc)
> 
> **参数:**
> 
> *   **fget()**–用于获取属性值
> *   **fset()**–用于设置属性值
> *   **fdel()**–用于删除属性值
> *   **文档()**–包含属性文档(文档字符串)的字符串
> 
> **返回:**从给定的**获取器、设置器和删除器返回属性属性。**

**注:**

*   如果没有给定参数，**属性()**方法返回一个不包含任何 getter、setter 或 deleter 的基本属性属性。
*   如果没有提供 doc，property()方法将获取 getter 函数的 docstring。

### **示例#1:** 使用属性()方法

## 蟒蛇 3

```py
# Python program to explain property() function
# Alphabet class

class Alphabet:
    def __init__(self, value):
        self._value = value

    # getting the values
    def getValue(self):
        print('Getting value')
        return self._value

    # setting the values
    def setValue(self, value):
        print('Setting value to ' + value)
        self._value = value

    # deleting the values
    def delValue(self):
        print('Deleting value')
        del self._value

    value = property(getValue, setValue,
                     delValue, )

# passing the value
x = Alphabet('GeeksforGeeks')
print(x.value)

x.value = 'GfG'

del x.value
```

**输出:**

```py
Getting value
GeeksforGeeks
Setting value to GfG
Deleting value
```

## Python 属性**使用** [**装饰器**](https://www.geeksforgeeks.org/decorators-in-python/)

装饰者的主要工作是用来给现有代码添加功能。也称为元编程，因为程序的一部分试图在编译时修改程序的另一部分。

### **示例#2:** 使用@property 装饰器

## 蟒蛇 3

```py
# Python program to explain property()
# function using decorator

class Alphabet:
    def __init__(self, value):
        self._value = value

    # getting the values
    @property
    def value(self):
        print('Getting value')
        return self._value

    # setting the values
    @value.setter
    def value(self, value):
        print('Setting value to ' + value)
        self._value = value

    # deleting the values
    @value.deleter
    def value(self):
        print('Deleting value')
        del self._value

# passing the value
x = Alphabet('Peter')
print(x.value)

x.value = 'Diesel'

del x.value
```

**输出:**

```py
Getting value
Peter
Setting value to Diesel
Deleting value
```

使用@property decorator 的工作方式与 property()方法相同。

首先，指定 value()方法也是 Alphabet 的一个属性，然后，我们使用属性值来指定 **Python 属性设置器**和删除器。请注意，相同的方法值()用于定义 getter、setter 和 deleter 的不同定义。每当我们使用 x.value 时，它都会在内部调用适当的 getter、setter 和 deleter。

## Python 属性与属性

**类属性:**类属性对于每个类都是唯一的。该类的每个实例都将具有此属性。

## 蟒蛇 3

```py
# declare a class
class Employee:

    # class attribute
    count = 0

    # define a method
    def increase(self):
        Employee.count += 1

# create an Employee
# class object
a1 = Employee()

# calling object's method
a1.increase()

# print value of class attribute
print(a1.count)

a2 = Employee()

a2.increase()

print(a2.count)

print(Employee.count)
```

**输出:**

```py
1
2
2
```

在上面的例子中，count 变量是一个类属性。

**Python 属性():**返回属性类的对象

## 蟒蛇 3

```py
# create a class
class gfg:

    # constructor
    def __init__(self, value):
        self._value = value

    # getting the values
    def getter(self):
        print('Getting value')
        return self._value

    # setting the values
    def setter(self, value):
        print('Setting value to ' + value)
        self._value = value

    # deleting the values
    def deleter(self):
        print('Deleting value')
        del self._value

    # create a properties
    value = property(getter, setter, deleter, )

# create a gfg class object
x = gfg('Happy Coding!')
print(x.value)

x.value = 'Hey Coder!'

# deleting the value
del x.value
```

**输出:**

```py
Getting value
Happy Coding!
Setting value to Hey Coder!
Deleting value
```

## **应用程序**

通过使用 property()方法，我们可以修改我们的类并实现值约束，而不需要对客户端代码进行任何更改。以便实现向后兼容。