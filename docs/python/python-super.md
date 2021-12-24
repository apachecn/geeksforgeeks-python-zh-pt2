# Python 超级()

> 原文:[https://www.geeksforgeeks.org/python-super/](https://www.geeksforgeeks.org/python-super/)

OOP 的一个重要特性是 Python 中的[继承](https://www.geeksforgeeks.org/inheritance-in-python/)。当一个类继承另一个类的部分或全部行为时，称为继承。在这种情况下，继承的类是子类，后者是父类。
在继承的子类中，可以使用 super()函数引用父类。super 函数返回超类的一个临时对象，该对象允许子类访问它的所有方法。

**注意:**更多信息请参考 Python 中的[继承](https://www.geeksforgeeks.org/inheritance-in-python/)

此外，使用超级功能的好处是:-

*   不需要记住或指定父类名来访问它的方法。这个函数既可以用于单个继承，也可以用于多个继承。
*   这实现了模块化(隔离变化)和代码可重用性，因为不需要重写整个功能。
*   Python 中的超级函数是动态调用的，因为 Python 是一种动态语言，不同于其他语言。

使用超级函数有 3 个限制:-

*   超函数引用的类及其方法
*   超级函数和被调用函数的参数应该匹配。
*   使用该方法后，它的每次出现都必须包含 super()。

**单一继承中的超级功能**

**例:**我们以动物为例。狗、猫和牛是动物的一部分。它们也有共同的特征，例如–

*   它们是哺乳动物。
*   它们有一条尾巴和四条腿。
*   它们是家畜。

所以，狗、猫和马是动物类的子类。这是一个单一继承的例子，因为许多子类是从单一父类继承而来的。

## 蟒蛇 3

```
# Python program to demonstrate
# super function

class Animals:

    # Initializing constructor
    def __init__(self):
        self.legs = 4
        self.domestic = True
        self.tail = True
        self.mammals = True

    def isMammal(self):
        if self.mammals:
            print("It is a mammal.")

    def isDomestic(self):
        if self.domestic:
            print("It is a domestic animal.")

class Dogs(Animals):
    def __init__(self):
        super().__init__()

    def isMammal(self):
        super().isMammal()

class Horses(Animals):
    def __init__(self):
        super().__init__()

    def hasTailandLegs(self):
        if self.tail and self.legs == 4:
            print("Has legs and tail")

# Driver code
Tom = Dogs()
Tom.isMammal()
Bruno = Horses()
Bruno.hasTailandLegs()
```

**输出:**

```
It is a mammal.
Has legs and tail
```

**多重继承中的超级功能**

**例:**我们再举一个例子。假设一个类可以从哺乳动物类继承 fly 和 canswim，这些类被动物类继承。所以动物类继承自多个基类。让我们看看 super 在这种情况下的用法。

## 蟒蛇 3

```
class Mammal():

    def __init__(self, name):
        print(name, "Is a mammal")

class canFly(Mammal):

    def __init__(self, canFly_name):
        print(canFly_name, "cannot fly")

        # Calling Parent class
        # Constructor
        super().__init__(canFly_name)

class canSwim(Mammal):

    def __init__(self, canSwim_name):

        print(canSwim_name, "cannot swim")

        super().__init__(canSwim_name)

class Animal(canFly, canSwim):

    def __init__(self, name):

        # Calling the constructor
        # of both thr parent
        # class in the order of
        # their inheritance
        super().__init__(name)

# Driver Code
Carol = Animal("Dog")
```

**输出:**

```
Dog cannot fly
Dog cannot swim
Dog Is a mammal
```

动物类继承自双亲类——can fly 和 canSwim。因此，子类实例 Carol 可以访问两个父类构造函数。