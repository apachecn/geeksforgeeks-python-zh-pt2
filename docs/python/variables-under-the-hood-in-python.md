# Python 中引擎盖下的变量

> 原文:[https://www . geeksforgeeks . org/variables-under-in-hood-in-python/](https://www.geeksforgeeks.org/variables-under-the-hood-in-python/)

简单来说，变量是 Python 中附加到特定对象的名称。要创建一个变量，你只需要赋值，然后开始使用它。这个任务用一个等号(*=*):

## python 3

```py
# Variable named age
age = 20
print(age)

# Variable named id_number
id_no = 4067613
print(id_no)
```

**输出:**

```py
20
4067613

```

从上面的程序可以清楚地看出，“年龄被赋予值 20”和“身份证号被赋予值 4067613”。现在年龄和 *id_no* 可以用在语句或表达式中，其值将被替换。

在 python 中，变量是动态的，即**变量的类型在运行时是已知的，并且一个变量可以被赋予一个类型的值，然后被重新赋予一个不同类型的值。**

## 当您在 Python 中进行变量赋值时，实际上发生了什么？

Python 是一种面向对象的语言。Python 程序中的任何数据项都是某种类型或类的对象，如整数、浮点、字符串等。

从上面的变量示例中，当我们给变量 age 赋值 20 时，解释器执行以下操作:

1.  Create an integer object.
2.  Give it a value of 20.
3.  Show it to the console

## python 3

```py
# type() built in function 
# say the type of variable
age = 20
print(type(age))
```

**输出:**

```py
<class 'int'>

```

实际上 python 变量是一个符号名，是一个**引用或指向一个对象**的指针。当一个对象被分配给一个变量时，该对象的引用可以通过其名称来使用，数据也存储在对象本身中。

#### 多对象引用:

它指的是将对象引用到以前分配的对象。

下面我们来看看这段代码:

## 蟒蛇

T0T6】

**输出:**

```py
20
20

```

这里，Python 不创建另一个对象。它只是创建一个新的符号名称或引用， *new_age* ，它指向先前指定的同一对象。

如果我们更改 *new_age* 的值，例如 *new_age=30* ，那么 Python 会创建一个新的整数对象，值为 *30* ， *new_age* 成为它的引用。

#### [垃圾收集:](https://www.geeksforgeeks.org/garbage-collection-python/)

如果我们改变上述变量 *age=25，*的值，则创建一个新的整数对象，值为 *25* ，并引用 *age* 。现在里面有 *20* 的整数对象已经被孤立或者失去了引用。没有办法接近它。 **如果至少有一个对该对象的引用，那么它可以是活动的** 。当对一个对象的引用数降至零时，python 最终会注意到它是不可访问的，并回收分配的内存，以便将其用于其他用途。这就是 Python 中垃圾收集的方式。

**注意:**更多信息请参考 Python 中的[垃圾收集](https://www.geeksforgeeks.org/garbage-collection-python/)