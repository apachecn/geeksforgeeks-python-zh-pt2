# Python @staticmethod

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-static method/

可以有一些与类相关的功能，但不需要任何实例来完成一些工作，在这种情况下可以使用静态方法。静态方法是绑定到类而不是类的对象的方法。它不能访问或修改类状态。它存在于类中，因为方法存在于类中是有意义的。静态方法不接收隐式的第一个参数。

```
Syntax:

class C(object):
    @staticmethod
    def fun(arg1, arg2, ...):
        ...

Returns: a static method for function fun.

```

当调用用`@staticmethod`修饰的函数时，我们不会像通常使用方法那样将类的实例传递给它。这意味着函数被放在类中，但它不能访问该类的实例。

**示例#1:**

```
# Python program to 
# demonstrate static methods

class Maths():

    @staticmethod
    def addNum(num1, num2):
        return num1 + num2

# Driver's code
if __name__ == "__main__":

    # Calling method of class
    # without creating instance
    res = Maths.addNum(1, 2)
    print("The result is", res)
```

**输出:**

```
The result is 3

```

**例 2:**

```
# Python program to
# demonstrate static methods

class Person: 
    def __init__(self, name, age): 
        self.name = name 
        self.age = age 

    # a static method to check if a Person is adult or not. 
    @staticmethod
    def isAdult(age): 
        return age > 18

# Driver's code
if __name__ == "__main__":
    res = Person.isAdult(12)
    print('Is person adult:', res)

    res = Person.isAdult(22)
    print('\nIs person adult:', res)
```

**输出:**

```
Is person adult: False

Is person adult: True

```