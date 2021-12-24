# Python staticmethod()函数

> 原文:[https://www.geeksforgeeks.org/python-staticmethod-function/](https://www.geeksforgeeks.org/python-staticmethod-function/)

**Python staticmethod()函数**用于将函数转换为静态函数。静态方法是属于类而不是类实例的方法。静态方法不需要实例化。

> **语法:** staticmethod(函数)
> 
> **参数:**
> 
> staticmethod()方法采用单个参数，即它采用一个函数作为参数。
> 
> **返回:**
> 
> staticmethod()返回作为参数传递的函数的静态方法。

### **例 1:**static method()应用的实现

## 蟒蛇 3

```py
class demoClass:

    def greet(msg):
        return msg

# convert the add to a static method
demoClass.greet = staticmethod(demoClass.greet)

# we can access the method without
# creating the instance of class
print(demoClass.greet("hai"))
```

**输出:**

```py
hai
```

在上面的代码中，创建了一个带有方法 greet()的类，然后使用 static method()将其转换为静态方法，并且在不创建实例的情况下调用它，正如我们前面讨论的，不需要创建类的实例来调用静态方法。

### **例 2:**static method()应用的实现

## 蟒蛇 3

```py
class demoClass:

    def __init__(self, a, b):
        self.a = a
        self.b = b

    def add(a, b):
        return a+b

    def diff(self):
        return self.a-self.b

# convert the add to a static method
demoClass.add = staticmethod(demoClass.add)

# we can access the method without creating
# the instance of class
print(demoClass.add(1, 2))

# if we want to use properties of a class
# then we need to create a object
Object = demoClass(1, 2)
print(Object.diff())
```

**输出:**

```py
3
-1
```

如果我们不需要使用类属性，那么我们可以使用静态方法，在上面的代码中，add()方法不使用任何类属性，因此使用 staticmethod()使其成为静态的，并且需要通过创建实例来调用 diff 方法，因为它使用类属性。