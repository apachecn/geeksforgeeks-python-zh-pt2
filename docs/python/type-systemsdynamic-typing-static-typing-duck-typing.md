# 打字系统:动态打字，静态打字&鸭子打字

> 原文:[https://www . geesforgeks . org/type-system dynamic-typing-static-typing-duck-typing/](https://www.geeksforgeeks.org/type-systemsdynamic-typing-static-typing-duck-typing/)

**Dynamic Typing:**

在动态类型中，类型检查是在运行时执行的。例如，Python 是一种动态类型语言。这意味着变量的类型可以在它的生命周期内改变。其他动态类型的语言有——Perl、Ruby、PHP、Javascript 等。
我们来看一个 Python 代码示例，看看变量是否可以改变类型:

```py

## variable a is assigned to a string
a ="hello"
print(type(a))

## variable a is assigned to an integer
a = 5
print(type(a))
```

这确认了变量“a”的类型是允许改变的，并且 Python 在它改变时正确地推断了类型。

让我们以 Python 中的动态类型为例:

```py
## simple function
def add(a, b):
    return a + b

## calling the function with string
print(add('hello', 'world'))

## calling the function with integer
print(add(2, 4))
```

在 Python 中，我们对这个函数处理的类型以及返回值的类型并没有很好的了解。

**Static Typing:**

静态类型与动态类型相反。在静态类型中，类型检查是在编译时执行的。这意味着变量的类型在编译时是已知的。对于某些语言，程序员必须指定每个变量是什么类型(例如 C、C++、Java)，其他语言提供某种形式的类型推断(例如 Scala、Haskell)。
有了静态类型化，变量一般不允许改变类型。
我们来看一个静态类型语言的简单例子。考虑下面的 Java 代码片段；

```py
String a;
a = "Java is good";
```

第一行声明变量“a”在编译时绑定到字符串类型。在第二行，“a”被赋予一个不是字符串对象的值。例如，如果我们说，a =5，编译器会因为类型不兼容而引发错误。

**Duck Typing**

Duck Typing 是一个与动态类型相关的概念，其中对象的类型或类不如它定义的方法重要。使用鸭打字，我们根本不检查类型。相反，我们检查给定方法或属性的存在。
名字背后的原因是鸭子测试:“如果它长得像鸭子，游得像鸭子，嘎嘎叫得像鸭子，那么它很可能就是鸭子”。
让我们举一个简单的 Python 代码示例来清楚地理解它:

```py
class Duck:
    def quack(self):
        print("Quack")

class Goose:
    def quack(self):
        print("Quack Quack")

class Dog:
    def bark(self):
        print("I just bark")

class ItQuacks:
    def __init__(self, animal):
        animal.quack()

ItQuacks(Duck())
ItQuacks(Goose())
ItQuacks(Dog())
```

实现了“呱呱”方法的类将能够调用(Duck，Goose 对象)，但是对于没有实现“呱呱”方法的“Dog”类，如果我们试图传递一个对象，就会得到一个“AttributeError”。