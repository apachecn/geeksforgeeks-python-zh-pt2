# Python unittest–assertNotIsInstance()函数

> 原文:[https://www . geesforgeks . org/python-unittest-assertnotisinstance-function/](https://www.geeksforgeeks.org/python-unittest-assertnotisinstance-function/)

Python 中的 assertNotIsInstance ()是一个[单元测试库](https://www.geeksforgeeks.org/unit-testing-python-unittest/)函数，用于单元测试中检查对象是否不是给定类的实例。该函数将采用三个参数作为输入，并根据断言条件返回一个布尔值。如果对象不是给定类的实例，它将返回 true，否则返回 false。

> **语法:**资产实例(对象、类名、消息)
> 
> **参数** : 资产通知状态()接受三个参数，并解释如下:
> 
> *   **对象**:作为给定类的实例被检查的对象
> *   **类名**:对象实例要比较的类名
> *   **消息**:作为测试用例失败时显示的消息的字符串。

下面列出了两个不同的例子，说明了给定断言函数的正测试用例和负测试用例:

**例 1:阴性测试案例**

## 蟒蛇 3

```
# test suite
import unittest

# test class
class Myclass:
    x = 5

class TestClass(unittest.TestCase):
    # test function to test whether obj is instance of class
    def test_negative(self):
        objectName = Myclass()
        # error message in case if test case got failed
        message = "given object is  instance of Myclass."
        # assertIsInstance() to check if obj is instance of class
        self.assertNotIsInstance(objectName, Myclass, message)

if __name__ == '__main__':
    unittest.main()
```

**输出:**

```
F
======================================================================
FAIL: test_negative (__main__.TestClass)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "/home/73feafa72d632b19f11ac8251bb291d7.py", line 17, in test_negative
    self.assertNotIsInstance(objectName, Myclass, message)
AssertionError: <__main__.Myclass object at 0x7fab0d3affd0> is an instance of <class '__main__.Myclass'> : given object is  instance of Myclass.

----------------------------------------------------------------------
Ran 1 test in 0.001s

FAILED (failures=1)

```

**例 2:阳性检测案例**

## 蟒蛇 3

```
# test suite
import unittest

# test class
class Myclass:
    x = 5

class Myclass2:
    x = 5

class TestClass(unittest.TestCase):
    # test function to test whether obj is instance of class
    def test_negative(self):
        objectName = Myclass()
        # error message in case if test case got failed
        message = "given object is instance of Myclass."
        # assert function() to check if obj is instance of class
        self.assertNotIsInstance(objectName, Myclass2, message)

if __name__ == '__main__':
    unittest.main()
```

**输出:**

```
.
----------------------------------------------------------------------
Ran 1 test in 0.000s

OK

```

**参考**:https://docs.python.org/3/library/unittest.html