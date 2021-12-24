# Python | super()多级继承的函数

> 原文:[https://www . geesforgeks . org/python-带多级继承的超级函数/](https://www.geeksforgeeks.org/python-super-function-with-multilevel-inheritance/)

**Python 中的 super()函数:**
Python*super function*为我们提供了显式引用父类的工具。在我们必须调用超类函数的地方，它基本上是有用的。它返回代理对象，允许我们通过**‘super’**引用父类。

要了解 Python 超级函数，我们必须了解 **[继承](https://www.geeksforgeeks.org/inheritance-in-python/)** 。在 Python 继承中，子类是从超类继承的。

Python 超级函数为我们提供了进行单级或多级继承的灵活性，使我们的工作更加轻松和舒适。请记住一点，当从子类引用超类时，没有必要显式地编写超类的名称。

下面是如何在 Python3 中调用超级函数的一个例子:

```
# parent class also sometime called the super class
class Parentclass():
    def __init__(self):
        pass

# derived or subclass
# initialize the parent or base class within the subclass
class subclass(Parentclass):
    def __init__(self):
        # calling super() function to make process easier
        super()
```

**Python 超()函数具有多级继承。**

正如我们已经研究过的，Python `super()`函数允许我们隐式引用超类。但是在多级继承中，出现了这么多类的问题，那么`super()`函数会引用哪个类呢？
嗯，`super()`函数有一个属性，它总是引用*直接超类*。还有，`super()` 函数不只是引用 *__init__()* 还可以在需要的时候调用超类的其他函数。

下面是解释多重继承的例子。

```
# Program to define the use of super()
# function in multiple inheritance
class GFG1:
    def __init__(self):
        print('HEY !!!!!! GfG I am initialised(Class GEG1)')

    def sub_GFG(self, b):
        print('Printing from class GFG1:', b)

# class GFG2 inherits the GFG1
class GFG2(GFG1):
    def __init__(self):
        print('HEY !!!!!! GfG I am initialised(Class GEG2)')
        super().__init__()

    def sub_GFG(self, b):
        print('Printing from class GFG2:', b)
        super().sub_GFG(b + 1)

# class GFG3 inherits the GFG1 ang GFG2 both
class GFG3(GFG2):
    def __init__(self):
        print('HEY !!!!!! GfG I am initialised(Class GEG3)')
        super().__init__()

    def sub_GFG(self, b):
        print('Printing from class GFG3:', b)
        super().sub_GFG(b + 1)

# main function
if __name__ == '__main__':

    # created the object gfg
    gfg = GFG3()

    # calling the function sub_GFG3() from class GHG3
    # which inherits both GFG1 and GFG2 classes
    gfg.sub_GFG(10)
```

**Output:**

```
HEY !!!!!! GfG I am initialised(Class GEG3)
HEY !!!!!! GfG I am initialised(Class GEG2)
HEY !!!!!! GfG I am initialised(Class GEG1)
Printing from class GFG3: 10
Printing from class GFG@: 11
Printing from class GFG1: 12

```