# Python | super()中单继承

> 原文:[https://www . geesforgeks . org/python-超单中继承/](https://www.geeksforgeeks.org/python-super-in-single-inheritance/)

先决条件:[继承](https://www.geeksforgeeks.org/inheritance-in-python/)、[功能覆盖](https://www.geeksforgeeks.org/function-overloading-vs-function-overriding-in-cpp/)

在相当抽象的层次上，`super()`提供了对超类(父类)的那些方法的访问，这些方法已经在继承自它的子类(子类)中被覆盖。考虑下面给出的代码示例，这里我们有一个名为`Square`的类和一个名为`Cube`的继承了类`Square`的类。

```
class Square:
     def __init__(self, side):
         self.side = side

     def area(self):
         return self.side * self.side

class Cube(Square):
      def area(self):
         face_area = self.side * self.side
         return face_area * 6

     def volume(self):
         face_area = self.side * self.side
         return face_area * self.side
```

**注意:**由于`Cube class`没有`__init__()`方法，`Square class`的`__init__()`将用于`Cube`实例的初始化(继承的基本属性)。

考虑这个例子，我们知道立方体的每个面都是正方形，因此立方体的`face_area`代表正方形的`area`。现在，使用类`Square`的`area()`方法评估`face_area`而不是手动计算它是有意义的，这不仅可以避免我们重写代码，还可以从一个地方改变`area()`逻辑。但是由于我们已经覆盖了`Cube`中的`area()`方法，我们不能使用`self.area()`调用`Square`的`area()`方法。
现在，这是 **`super()`** 出手相救的情况。`super()`返回父类的代理对象，然后在该代理对象上调用您选择的方法，这样，我们就可以使用`super()` as、 **`super().area()`** 调用`Square class`的`area()`方法。以下是`class Cube`的修改定义。

```
class Cube(Square):
     def area(self):
         return super().area() * 6

     def volume(self):
         return super().area() * self.side()
```

请注意，我们可以将`Square`方法的`area()`称为`Square.area()`而不是`super().area()`，但是后者更容易换出超类或在需要时重命名它，从而使代码更容易维护。

**在`super()`–**
中传递参数在上一节中，我们讨论了如何在没有任何参数的情况下使用`super()`，但这只能让我们访问作为子类直接父类的那个超类的方法。

要访问不是子类的直接父类的超类的方法，我们使用带有两个参数的`super()`。让我们考虑一个名为`Square`、`SquarePrism`和`Cube`的三个类的例子，以了解如何将`super()`用于参数。
现在，立方体只是一种特殊类型的方形棱镜，其高度等于其底部的边长，因此立方体更像方形棱镜，而不是正方形。因此，在本例中`class Cube`将继承`class SquarePrism`，而`class
SquarePrism`将继承`class Square`。对于类`Square`，我们将使用上一节中使用的相同定义。下面是我们新定义的类`SquarePrism`的定义。

```
class SquarePrism(Square):
     def __init__(self, side, height):
         self.side = side
         self.height = height

     def face_area(self):
         base_area = super().area()
         lateral_area = self.side * self.height
         return base_area, lateral_area

     def area(self):
         base_area = super().area()
         lateral_area = self.side * self.height
         return 2 * base_area + 4 * lateral_area
```

一个`SquarePrism`实例有两个属性，它的正方形底部的边和正方形棱柱的高度。实例方法`face_area()`返回一个由两个数字组成的元组，表示正方形棱柱的底部面积和正方形棱柱的侧面面积。由于基底是正方形，对于正方形棱柱的基底面积，我们称方法`Square.area()`为`super().area()`。`area()`方法返回方形棱镜的总表面积。

到目前为止，我们使用的`super()`没有任何参数，现在遵循新类`Cube`的定义，它将演示带参数的`super()`的使用。

```
class Cube(SquarePrism):
     def __init__(self, side)
         super().__init__(side = side, height = side)

     def face_area(self):
         return super(SquarePrism, self).area()

     def area(self):
         return super().area()
```

不同于`__init__()`、`area()`的方法，`Cube`的`face_area()`方法与其对应物`SquarePrism.face_area()`有些不同。对于立方体，横向面积等于基础面积，因此`face_area()`方法返回元组没有意义，因此`class Cube`的`face_area()`将返回立方体面之一的面积。
现在，既然立方体的每个面都是正方形，那么使用`class Square`的`area()`方法又有意义了。现在，由于`class Square`不是`class Cube`的直系父代，我们无法将`class Square`的`area()`方法作为`super().area()`访问，因为它将改为调用方法`SquarePrism.area()`。

这里我们用 **`super(SquarePrism, self).face_area()`** 来称呼`class Square`的`area()`法。在第一个参数中，`SquarePrism`表示`super()`在类`SquarePrism,`的直接父类`class Square`中搜索`area()`方法。使用`self`作为第二个参数为所请求的`area()`方法提供了当前`Cube`对象到`super()`的上下文。

请记住，要在两个参数形式中使用`super()`，作为第二个参数传递的对象必须是作为第一个参数传递的`type`的实例。

**注:**由于类`Cube`是`class SquarePrism`的子类，`Cube`实例也是`class SquarePrism`和`class Square`的实例。

尝试下面的代码片段，并观察输出以澄清上述观点。

```
class Square:
    def __init__(self):
        pass

class SquarePrism(Square):
    def __init__(self):
        pass

class Cube(SquarePrism):
    def __init__(self):
        pass

square = Square()
squareprism = SquarePrism()
cube = Cube()

print(isinstance(squareprism, Square))
print(isinstance(cube, Square))
```

值得注意的是，`super()`的零参数形式只能在类定义中使用，因为它是由编译器用适当的参数自动填充的，也就是说，如果我们在类中使用`super()`，比如说`X`，`super()`将被编译器转换成`super(X, self)`。

虽然`super()`的零参数形式在开发人员中很流行，但这两种参数形式目前似乎没有多大用处。但是在多重继承中，这两种论证形式起着非常重要的作用。