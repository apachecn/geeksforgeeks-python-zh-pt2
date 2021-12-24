# Python |使用 __ 个插槽 __

> 原文:[https://www.geeksforgeeks.org/python-use-of-__slots__/](https://www.geeksforgeeks.org/python-use-of-__slots__/)

当我们为类创建对象时，它需要内存，并且属性以字典的形式存储。万一我们需要分配成千上万的对象，会占用大量的内存空间。
**插槽**提供了一种特殊的机制来减小对象的大小。这是一个对象内存优化的概念。

**无槽 python 对象示例:**

```
class GFG(object):
      def __init__(self, *args, **kwargs):
                self.a = 1
                self.b = 2

if __name__ == "__main__":
     instance = GFG()
     print(instance.__dict__)
```

**输出:**

```
{'a': 1, 'b': 2}
```

因为 Python 中的每个对象都包含一个允许添加属性的动态字典。对于每个实例对象，我们将有一个消耗更多空间和浪费大量内存的字典实例。在 Python 中，在创建对象以存储其所有属性时，没有分配静态内存量的默认功能。
使用 __slots__ 通过为固定数量的属性分配空间来减少空间浪费并加快程序运行速度。

**带槽 python 对象示例:**

```
class GFG(object):
      __slots__=['a', 'b']
      def __init__(self, *args, **kwargs):
                self.a = 1
                self.b = 2

if __name__ == "__main__":
     instance = GFG()
     print(instance.__slots__)
```

**输出:**

```
['a', 'b']
```

**python 的例子如果我们使用 dict :**

```
class GFG(object):
      __slots__=['a', 'b']
      def __init__(self, *args, **kwargs):
                self.a = 1
                self.b = 2

if __name__ == "__main__":
     instance = GFG()
     print(instance.__dict__)
```

**输出:**

```
AttributeError: 'GFG' object has no attribute '__dict__'
```

将导致此错误。

**使用 __ 个插槽 _ _ 的结果:**

1.  快速访问属性
2.  节省内存空间