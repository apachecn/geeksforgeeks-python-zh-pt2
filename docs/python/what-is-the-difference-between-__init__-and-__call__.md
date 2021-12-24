# 【_ _ init _ _ 和 __call__ 有什么区别？

> 原文:[https://www . geesforgeks . org/什么是-init _ _-和-call _ _/](https://www.geeksforgeeks.org/what-is-the-difference-between-__init__-and-__call__/)的区别

Python 中的 Dunder 或 magic 方法是在方法名中有两个前缀和后缀下划线的方法。邓德在这里的意思是“双下划线”。这些通常用于运算符重载。魔术方法的几个例子是:`__init__, __add__, __len__, __repr__`等。在本文中，我们将看到这两种方法之间的区别。

**注意:**更多信息请参考[邓德或者 Python 中的魔法方法](http://geeksforgeeks.org/dunder-magic-methods-python/)

### __init__()

这个 Python 方法类似于任何其他编程语言中的构造函数。构造函数是与类同名的定义，在定义该类的对象时会自动调用。构造函数初始化程序的所有必需实体，使其更加可靠。
类似于这个定义 __init__()作为一个 Python 构造函数工作，当类的一个对象被定义时，它会被自动调用。它用提供的默认值初始化所需的成员。它也可以用声明类的对象时提供的值来调用。

**示例:**

```
class A:
    def __init__(self, x):
        print("inside __init__()")
        self.y = x

    def __str__(self):
        print("inside __str__()")
        print("value of y:", str(self.y))

# declaration of instance of class A
a = A(3)

# calling __str__() for object a
a.__str__()

# declaration of another instance 
# of class A
b = A(10)

# calling __str__() for b
b.__str__()
```

**输出:**

```
inside __init__()
inside __str__()
('value of y:', '3')
inside __init__()
inside __str__()
('value of y:', '10')

```

### __ 呼叫 _ _()

在开始应用`__call__()`之前，我们需要了解什么是可调用对象。
可调用对象是可以像函数一样调用的对象。
在 Python 中，__call__()用于解析与可调用对象相关联的代码。只要以函数调用格式编写，任何对象都可以转换为可调用对象。这类对象调用 __call__()方法并执行与之关联的代码。这并不会使对象不能像正常对象一样工作。该对象可以用作正常使用。
有一点要记住，对象本身是作为函数使用的，所以语法要正确。

**示例:**

```
class A:
    def __init__(self, x):
        print("inside __init__()")
        self.y = x

    def __str__(self):
        print("inside __str__()")
        print("value of y:", str(self.y))

    def __call__(self):
        res = 0
        print("inside __call__()")
        print("adding 2 to the value of y")
        res = self.y + 2
        return res

# declaration of instance of class A
a = A(3)

# calling __str__() for a
a.__str__()

# calling __call__() for a 
r = a()
print(r)

# declaration of another instance
# of class A
b = A(10)

# calling __str__() for b
b.__str__()

# calling __call__() for b
r = b()
print(r)
```

**输出:**

```
inside __init__()
inside __str__()
('value of y:', '3')
inside __call__()
adding 2 to the value of y
5
inside __init__()
inside __str__()
('value of y:', '10')
inside __call__()
adding 2 to the value of y
12
```

## __init__()和 VS __call__()的区别

| __init__() | __ 呼叫 _ _() |
| 与构造函数相同，它初始化值 | 它用于使用对象的直接调用 |
| 当一个对象被声明时，它被自动调用 | 它由可调用 |
| 由常规对象调用 | 由可调用对象调用 |
| 示例:
A = A(3)#语句 1
A()#语句 2
__init__()由语句 1 调用 | 示例:
A = A(3)#语句 1
A()#语句 2
__call__()由语句 2 调用 |