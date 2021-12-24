# Python 对象

> 原文:[https://www.geeksforgeeks.org/python-objects/](https://www.geeksforgeeks.org/python-objects/)

类是用户定义的蓝图或原型，从中创建对象。类提供了一种将数据和功能捆绑在一起的方法。创建一个新类会创建一个新类型的对象，从而允许创建该类型的新实例。每个类实例都可以附加属性来维护其状态。类实例也可以有方法(由其类定义)来修改其状态。

> 参考下面的文章来了解 Python 类的基础知识。
> 
> *   [Python 类](https://www.geeksforgeeks.org/python-classes-and-objects/)

#### 类对象

对象是类的一个实例。一个类就像一个蓝图，而一个实例是一个有实际值的类的副本。

为了理解对象，让我们考虑一个例子，假设有一个类名狗，它包含某些属性，如品种、年龄、颜色和行为，如吠叫、睡觉和进食。这个类的一个对象就像一只真正的狗，比方说一只七岁的哈巴狗。你可以让许多狗创建许多不同的实例，但是如果没有这个类作为向导，你会迷失方向，不知道需要什么信息。

一个对象包括:

*   **状态:**由对象的属性表示。它还反映了对象的属性。
*   **行为:**用一个对象的方法来表示。它还反映了一个对象与其他对象的反应。
*   **身份:**它为一个对象赋予唯一的名称，并使一个对象能够与其他对象交互。

![python-objects](img/37fdd7e0e5dfab24d64a8895b5c188f9.png)

#### 声明对象(也称为实例化类)

当一个类的对象被创建时，这个类被称为实例化。所有实例共享类的属性和行为。但是这些属性值，即状态对于每个对象都是唯一的。一个类可以有任意数量的实例。

![python-objects](img/accf1a2d728e7b06b00cad2e4e7307ec.png)

**示例:**

```py
# Python program to 
# demonstrate instantiating 
# a class 

class Dog:  

    # A simple class 
    # attribute 
    attr1 = "mamal"
    attr2 = "dog"

    # A sample method   
    def fun(self):  
        print("I'm a", self.attr1) 
        print("I'm a", self.attr2) 

# Driver code 
# Object instantiation 
Rodger = Dog() 

# Accessing class attributes 
# and method through objects 
print(Rodger.attr1) 
Rodger.fun() 
```

**输出:**

```py
mamal
I'm a mamal
I'm a dog

```