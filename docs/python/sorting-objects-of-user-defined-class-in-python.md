# 对 Python 中自定义类的对象进行排序

> 原文:[https://www . geesforgeks . org/python 中用户定义类的排序对象/](https://www.geeksforgeeks.org/sorting-objects-of-user-defined-class-in-python/)

下面的文章讨论了如何基于类的任何变量来排列用户定义的类的对象，这显然会为每个对象保留一些值。到目前为止，我们知道如何对列表中的元素进行排序，这里的概念或多或少与相同，只是它是一个进步，或者我们可以说它是排序元素的高级版本，但是我们处理的不是列表，而是类的对象。

这里将使用[排序()](https://www.geeksforgeeks.org/sorted-function-python/)方法。

**语法:**

> 已排序(可迭代、关键(可选)、反向(可选) )

**示例:**这只是一个普通的示例，展示了如何使用此方法

## python 3

```
print(sorted([1,26,3,9]))

print(sorted("Geeks foR gEEks".split(), key=str.lower))
```

**输出:**

```
[1, 3, 9, 26]
['foR', 'Geeks', 'gEEks']
```

## 对用户定义类的对象进行排序

**方法 1:**

为了对用户定义类的对象进行排序，需要为已排序的方法设置一个键，这样该键将是对象应该如何排序的指示符。参考下面给出的例子，这里为键提供了一个函数，该函数逐个比较每个对象的指定变量值，并返回一个类的对象排序列表。

**示例 1:** 按照给定整数值的升序对元素进行排序

## python 3

```
class GFG:
    def __init__(self, a, b):
        self.a = a
        self.b = b

    def __repr__(self):
        return str((self.a, self.b))

# list of objects
gfg = [GFG("geeks", 1),
       GFG("computer", 3),
       GFG("for", 2),
       GFG("geeks", 4),
       GFG("science", 3)]

# sorting objects on the basis of value 
# stored at variable b
print(sorted(gfg, key=lambda x: x.b))
```