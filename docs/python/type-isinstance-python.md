# Python 中的类型和实例

> 哎哎哎:# t0]https://www . geeksforgeeks . org/type-isinstance-python/

**Python 中的类型**

Python 有一个名为 as type 的内置方法，通常在计算运行时程序中使用的变量类型时会派上用场。

**Syntax:**

```
type(object)
type(name, bases, dict)
```

1.  **type() With a Single Object Parameter**

    ```
    # Python code type() with a single object parameter
    x = 5
    s = "geeksforgeeks"
    y = [1,2,3]
    print(type(x))
    print(type(s))
    print(type(y))
    ```

    **输出:**

    ```
    class 'int'
    class 'str'
    class 'list'

    ```

2.  **type() With a name, bases and dict Parameter**

    ```
    # Python code for type() with a name, 
    # bases and dict parameter

    o1 = type('X', (object,), dict(a='Foo', b=12))

    print(type(o1))
    print(vars(o1))

    class test:
          a = 'Foo'
      b = 12

    o2 = type('Y', (test,), dict(a='Foo', b=12))
    print(type(o2))
    print(vars(o2))
    ```

    **输出:**

    ```
    {'b': 12, 'a': 'Foo', '__dict__': , '__doc__': None, '__weakref__': }
    {'b': 12, 'a': 'Foo', '__doc__': None}

    ```

    如果需要检查对象的类型，建议改用 Python isinstance()函数。这是因为 isinstance()函数还会检查给定的对象是否是子类的实例。

**情况()**

isinstance()函数检查对象(第一个参数)是否是 classinfo 类(第二个参数)的实例或子类。

**语法:**

```
isinstance(object, classinfo) 
isinstance()接受两个参数:**对象:**要检查的对象**类信息**:类、类型或类和类型的元组
```

**返回值:**
**true** 如果对象是类的实例或子类，或者元组的任何元素 **false** 否则。如果类信息不是类型或类型元组，则会引发类型错误异常。

```
# Python code for  isinstance()
class Test:
    a = 5

TestInstance = Test()

print(isinstance(TestInstance, Test))
print(isinstance(TestInstance, (list, tuple)))
print(isinstance(TestInstance, (list, tuple, Test)))
```

输出:

```
True
False
True
```

**type()与 isince()**的比较

人们犯的一个基本错误是使用 type()函数，其中 isinstance()更合适。

*   如果您正在检查某个对象是否具有某个类型，您需要 isinstance()，因为它会检查在第一个参数中传递的对象是否属于在第二个参数中传递的任何类型对象。因此，它可以像预期的那样处理子类化和旧式类，所有这些类都有遗留类型对象实例。
*   type(), on the other hand, simply returns the type object of an object and comparing what it returns to another type object will only yield True when you use the exact same type object on both sides.
    In Python, it’s preferable to use Duck Typing( type checking be deferred to run-time, and is implemented by means of dynamic typing or reflection) rather than inspecting the type of an object.

    ```
    #Python code to illustrate duck typing

    class User(object):
        def __init__(self, firstname):
            self.firstname = firstname

        @property
        def name(self):
            return self.firstname

    class Animal(object):
        pass

    class Fox(Animal):
        name = "Fox"

    class Bear(Animal):
        name = "Bear"

    # Use the .name attribute (or property) regardless of the type
    for a in [User("Geeksforgeeks"), Fox(), Bear()]:
        print(a.name)
    ```

    输出:

    ```
    Geeksforgeeks
    Fox
    Bear
    ```

*   不使用 type()的下一个原因是缺乏对继承的支持。

    ```
    #python code to illustrate the lack of
    #support for inheritance in type()

    class MyDict(dict):
        """A normal dict, that is always created with an "initial" key"""
        def __init__(self):
            self["initial"] = "some data"

    d = MyDict()
    print(type(d) == dict)
    print(type(d) == MyDict)

    d = dict()
    print(type(d) == dict)
    print(type(d) == MyDict)
    ```

    **输出:**

    ```
    False
    True
    True
    False

    ```

    MyDict 类具有 Dict 的所有属性，没有任何新方法。它的行为将完全像一本字典。但是 type()不会返回预期的结果。
    在这种情况下，使用 isinstance()更好，因为它会给出预期的结果:

    ```
    #python code to show isintance() support
    #inheritance
    class MyDict(dict):
        """A normal dict, that is always created with an "initial" key"""
        def __init__(self):
            self["initial"] = "some data"

    d = MyDict()
    print(isinstance(d, MyDict))
    print(isinstance(d, dict))

    d = dict()
    print(isinstance(d, MyDict))
    print(isinstance(d, dict))
    ```

    输出:

    ```
    True
    True
    False
    True
    ```

参考链接:

**1。** [堆栈溢出–python 中 isinstance()和 type()的区别](https://stackoverflow.com/questions/1549801/differences-between-isinstance-and-type-in-python)
**2。**[Programiz is instance()](https://www.programiz.com/python-programming/methods/built-in/isinstance)
**3。** [Programiz 类型](https://www.programiz.com/python-programming/methods/built-in/type)
本文由 **[Subhajit Saha](https://www.linkedin.com/in/subhajit-saha-06aa29131/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。