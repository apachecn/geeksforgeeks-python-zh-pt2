# Python 中的包装类

> 原文:[https://www.geeksforgeeks.org/wrapper-class-in-python/](https://www.geeksforgeeks.org/wrapper-class-in-python/)

**装饰**是指定功能和类的管理代码的一种方式。装饰者本身采取可调用对象的形式，处理其他可调用对象。**类装饰器**类似于函数装饰器，但它们运行在类语句的末尾，将类名重新绑定到可调用的(例如函数)上。因此，它们可以用来管理刚创建的类，也可以在以后创建实例时插入一层包装逻辑来管理实例。类装饰器可以用来直接管理类对象，而不是实例调用——用新方法增加/修改类。类装饰器与函数装饰器密切相关，事实上，它们使用几乎相同的语法和非常相似的编码模式，但在某些地方逻辑不同。

**注意:**更多信息请参考 Python 中的[装饰者](https://www.geeksforgeeks.org/decorators-in-python/)

**语法:**
在语法上，类修饰词就出现在类语句之前。

```py
@decorator
class Class_Name:       
      ...

inst = Class_Name(50)

This piece of code is equivalent to

class Class_Name:
      ...

Class_Name = decorator(Class_Name)
inst = Class_Name(50);

```

让我们通过一个例子来了解语法及其工作原理:

**示例:**

```py
# decorator accepts a class as 
# a parameter
def decorator(cls):

    class Wrapper:

        def __init__(self, x):

            self.wrap = cls(x)

        def get_name(self):

            # fetches the name attribute
            return self.wrap.name

    return Wrapper

@decorator
class C:
    def __init__(self, y):
        self.name = y

# its equivalent to saying
# C = decorator(C)
x = C("Geeks")
print(x.get_name())   
```

**输出:**

```py
Geeks

```

在本例中，装饰器将类 C 重新绑定到另一个类 Wrapper，该类将原始类保留在封闭范围内，并在调用时创建和嵌入原始类的实例(Wrapper)。用更简单的语言来说，`@decorator`相当于`C = decorator(C)`，在 C 类定义的末尾执行，在装饰器主体中，包装器类修改 C 类保持原创性或者不改变 C，`cls(x)`返回 C 类的一个对象(其名称属性初始化为 x 值)。方法 get_name 返回包装对象的名称属性。最后在输出中，“极客”被打印出来。

这是对类的装饰器或包装器的概述。类装饰器用于向类添加额外的功能，而无需更改原始类以在任何情况下按需使用。