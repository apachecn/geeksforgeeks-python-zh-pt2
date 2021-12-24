# Python unittest–assertinstance()函数

> 原文:[https://www . geeksforgeeks . org/python-unittest-assert instance-function/](https://www.geeksforgeeks.org/python-unittest-assertisinstance-function/)

Python 中的assertisinge()是一个 [unittest 库](https://www.geeksforgeeks.org/unit-testing-python-unittest/)函数，用于单元测试中检查一个对象是否是给定类的实例。该函数将采用三个参数作为输入，并根据断言条件返回一个布尔值。如果对象是给定类的实例，它将返回 true，否则返回 false。

> **语法:**资产实例(对象、类名、消息)
> 
> **参数** : 广告实例()接受下面列出的三个参数，并给出解释:
> 
> *   **对象**:作为给定类的实例被检查的对象
> *   **类名**:对象实例要比较的类名
> *   **消息**:作为测试用例失败时显示的消息的字符串。

下面列出了两个不同的例子，说明了给定断言函数的正测试用例和负测试用例:

**例 1:阴性测试案例**

## 蟒蛇 3

```py
# test suite
import unittest

# test class

class Myclass:
    x = 5

class Myclass2:
    x = 6

class TestClass(unittest.TestCase):
    # test function to test whether obj is instance of class
    def test_negative(self):
        objectName = Myclass()
        # error message in case if test case got failed
        message = "given object is not instance of Myclass."
        # assertIsInstance() to check if obj is instance of class
        self.assertIsInstance(objectName, Myclass2, message)

if __name__ == '__main__':
    unittest.main()
```

**输出:**

```py
F
======================================================================
FAIL: test_negative (__main__.TestStringMethods)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "/home/a2e9f97d79f7d8c1fbd00c4df704d402.py", line 22, in test_negative
    self.assertIsInstance(objectName, Myclass2, message)
AssertionError: <__main__.Myclass object at 0x7f1e9bead0b8> is not an instance of <class '__main__.Myclass2'> : given object is not instance of Myclass.

----------------------------------------------------------------------
Ran 1 test in 0.001s

FAILED (failures=1)

```

**例 2:阳性检测案例**

## 蟒蛇 3

```py
# test suite
import unittest

# test class
class Myclass:
    x = 5

class TestClass(unittest.TestCase):
    # test function to test whether obj is instance of class
    def test_positive(self):
        objectName = Myclass()
        # error message in case if test case got failed
        message = "given object is not instance of Myclass."
        # assertIsInstance() to check if obj is instance of class
        self.assertIsInstance(objectName, Myclass, message)

if __name__ == '__main__':
    unittest.main()
```

**输出:**

```py
.
----------------------------------------------------------------------
Ran 1 test in 0.000s

OK

```

**参考**:https://docs.python.org/3/library/unittest.html