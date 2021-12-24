# Python 对象()方法

> 原文:[https://www.geeksforgeeks.org/python-object-method/](https://www.geeksforgeeks.org/python-object-method/)

**Python 对象()函数**返回空对象， **Python 对象不带参数。**

在 python 中，我们赋予值/容器的每个变量都被视为一个对象。对象本身就是一个类。让我们讨论这个类的属性和演示如何用于日常编程。

> **语法:**对象()
> 
> **参数:**无
> 
> **返回:**无特征类的对象。充当所有对象的基础

### **示例 1:** 演示对象()的工作

## 蟒蛇 3

```
# Python 3 code to demonstrate
# working of object()

# declaring the object of class object
obj = object()

# printing its type
print("The type of object class object is : ")
print(type(obj))

# printing its attributes
print("The attributes of its class are : ")
print(dir(obj))
```

**输出:**

> 对象类对象的类型为:
> 其类的属性为:
> ['__class__ '，' __delattr__ '，' __dir__ '，' __doc__ '，' __eq__ '，' __format__ '，' __ge__ '，' __getattribute_ '，' __gt__ '，' __hash_ '，' __init_ '，' __le_ '，' __lt_ '，' __ne__ '，'

## 对象的属性()

*   对象类的对象不能向其中添加新属性。
*   这些物体都是独一无二的，并不等同于其他物体，也就是说，一旦比较就不会返回真。
*   该对象充当我们制作的所有自定义对象的基类。

### **示例 2 :** 演示对象的属性()

## 蟒蛇 3

```
# Python 3 code to demonstrate
# properties of object()

# declaring the objects of class object
obj1 = object()
obj2 = object()

# checking for object equality
print("Is obj1 equal to obj2 : " + str(obj1 == obj2))

# trying to add attribute to object
obj1.name = "GeeksforGeeks"
```

**输出:**

```
Is obj1 equal to obj2 : False
```

例外:

```
Traceback (most recent call last):
  File "/home/46b67ee266145958c7cc22d9ee0ae759.py", line 12, in 
    obj1.name = "GeeksforGeeks"
AttributeError: 'object' object has no attribute 'name'
```