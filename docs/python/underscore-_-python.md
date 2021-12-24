# Python 中的下划线(_)

> 原文:[https://www.geeksforgeeks.org/underscore-_-python/](https://www.geeksforgeeks.org/underscore-_-python/)

下面是 Python 中使用 _ 的不同地方:

1.  单下划线:
    *   翻译中
    *   名字后面
    *   名字前
2.  双下划线:
    1.  _ _ 前导双下划线
    2.  __ 之前 _ 之后 _ _

**单下划线**

**在解释器中:**
_ 返回 Python 提示符/解释器中最后执行的表达式值

```py
>>> a = 10
>>> b = 10
>>> _
Traceback (most recent call last):
File "<stdin>", line 1, in <module>
NameError: name '_' is not defined
>>> a+b
20
>>> _
20
>>> _ * 2
40
>>> _
40
>>> _ / 2
20
```

**对于忽略值:**
多次我们不希望返回值在那个时候将那些值赋给下划线。它用作一次性变量。

```py
# Ignore a value of specific location/index
for _ in range(10)
    print ("Test")

# Ignore a value when unpacking
a,b,_,_ = my_method(var1)
```

**在一个名字后面**
Python 默认有它们的关键字，我们不能用它们作为变量名。为了避免 python 关键字和变量之间的冲突，我们在名称后使用下划线

示例:

```py
>>> class MyClass():
...     def __init__(self):
...             print ("OWK")

>>> def my_defination(var1 = 1, class_ = MyClass):
...     print (var1)
...     print (class_)

>>> my_defination()
1
__main__.MyClass
>>>
```

**名称前**
变量/函数/方法名称前的前导下划线向程序员表明，它仅供内部使用，可以随时修改类。

在这里，带下划线的名称前缀被视为非公共的。如果从导入* 中指定**，所有以 _ 开头的名称都不会导入。Python 并没有指定真正的私有，所以如果在 __all__ 中指定的话，可以从其他模块直接调用这些模块，我们也称之为**弱私有****

```py
class Prefix:
...     def __init__(self):
...             self.public = 10
...             self._private = 12
>>> test = Prefix()
>>> test.public
10
>>> test._private
12
```

Python 类 _file.py

```py
def public_api():
    print ("public api")

def _private_api():
    print ("private api")
```

从提示符调用文件

```py
>>> from class_file import *
>>> public_api()
public api

>>> _private_api()
Traceback (most recent call last):
File "<stdin>", line 1, in <module>
NameError: name '_private_api' is not defined

>>> import class_file
>>> class_file.public_api()
public api
>>> class_file._private_api()
private api
```

**双下划线(__)**

**_ _ 前导双下划线**
前导双下划线告诉 python 解释器重写名称，避免子类冲突。解释器通过类扩展改变变量名，这个特性被称为 Mangling。
测试文件. py

```py
class Myclass():
    def __init__(self):
        self.__variable = 10
```

口译员呼叫

```py
>>> import testFile
>>> obj = testFile.Myclass()
>>> obj.__variable
Traceback (most recent call last):
File "", line 1, in
AttributeError: Myclass instance has no attribute '__variable'
nce has no attribute 'Myclass'
>>> obj._Myclass__variable
10
```

在 Mangling python 解释器中，用 __ 修改变量名。所以多次使用它作为私有成员，因为另一个类不能直接访问那个变量。__ 的主要目的是只在类中使用变量/方法。如果你想在类外使用它，你可以使用公共 api

```py
class Myclass():
    def __init__(self):
        self.__variable = 10
    def func(self)
        print (self.__variable)
```

口译员呼叫

```py
>>> import testFile
>>> obj = testFile.Myclass()
>>> obj.func()
10
```

**__BEFORE_AFTER__**
名称以 __ 开头，以 __ 结尾考虑 Python 中的特殊方法。Python 提供了这些方法，根据用户的不同将其用作运算符重载。

Python 提供了这个约定来区分用户定义的函数和模块的函数

```py
class Myclass():
    def __add__(self,a,b):
        print (a*b)
```

口译员呼叫

```py
>>> import testFile
>>> obj = testFile.Myclass()
>>> obj.__add__(1,2)
2
>>> obj.__add__(5,2)
10
```

本文由 **Nirmi Shah** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。