# Python 类中的自我

> 原文:[https://www.geeksforgeeks.org/self-in-python-class/](https://www.geeksforgeeks.org/self-in-python-class/)

self 表示类的实例。通过使用“self”关键字，我们可以在 python 中访问类的属性和方法。它将属性与给定的参数绑定在一起。
你需要用自我的原因。是因为 Python 不使用@语法来引用实例属性。Python 决定以一种方式来做方法，这种方式使得方法所属的实例可以自动传递，但不能自动接收:方法的第一个参数是调用该方法的实例。

更清楚地说，你可以说自我有以下特征-

> 自我总是指向当前对象。

## 蟒蛇 3

```
#it is clearly seen that self and obj is referring to the same object

class check:
    def __init__(self):
        print("Address of self = ",id(self))

obj = check()
print("Address of class object = ",id(obj))

# this code is Contributed by Samyak Jain
```

**Output**

```
Address of self =  140124194801032
Address of class object =  140124194801032
```

另一个使用自我的例子:

## 蟒蛇 3

```
# Write Python3 code here

class car():

    # init method or constructor
    def __init__(self, model, color):
        self.model = model
        self.color = color

    def show(self):
        print("Model is", self.model )
        print("color is", self.color )

# both objects have different self which
# contain their attributes
audi = car("audi a4", "blue")
ferrari = car("ferrari 488", "green")

audi.show()     # same output as car.show(audi)
ferrari.show()  # same output as car.show(ferrari)

# Behind the scene, in every instance method
# call, python sends the instances also with
# that method call like car.show(audi)
```

**Output**

```
Model is audi a4
color is blue
Model is ferrari 488
color is green
```

> Self 是构造函数和实例方法中传递的第一个参数。

Self 必须作为实例方法和构造函数的第一个参数提供。如果不提供，会造成错误。

## 蟒蛇 3

```
# Self is always required as the first argument
class check:
    def __init__():
        print("This is Constructor")

object = check()
print("Worked fine")

# Following Error is produced if Self is not passed as an argument
Traceback (most recent call last):
  File "/home/c736b5fad311dd1eb3cd2e280260e7dd.py", line 6, in <module>
    object = check()
TypeError: __init__() takes 0 positional arguments but 1 was given

  # this code is Contributed by Samyak Jain
```

> Self 是约定，不是 Python 关键字。

self 是实例方法中的参数，用户可以使用另一个参数名来代替它。但是最好使用 self，因为它增加了代码的可读性，也是一种很好的编程实践。

## 蟒蛇 3

```
# Write Python3 code here

class this_is_class:
    def __init__(in_place_of_self):
        print("we have used another "
        "parameter name in place of self")

object = this_is_class()
```

**Output**

```
we have used another parameter name in place of self
```