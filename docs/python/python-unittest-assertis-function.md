# Python unittest–assertIs()函数

> 原文:[https://www . geesforgeks . org/python-unittest-assertis-function/](https://www.geeksforgeeks.org/python-unittest-assertis-function/)

Python 中的 assertIs()是一个 [unittest 库](https://www.geeksforgeeks.org/unit-testing-python-unittest/)函数，在单元测试中用来测试第一个和第二个输入值是否评估为同一个对象。该函数将采用三个参数作为输入，并根据断言条件返回一个布尔值。如果两个输入评估为同一个对象，那么 assertIs()将返回 true，否则返回 false。

> **语法:** assertIs(第一个值，第二个值，消息)
> 
> **参数** : assertIs()接受以下列出的三个参数，并进行解释:
> 
> *   **第一个值**函数比较中使用的任何类型的变量
> *   **秒值**:函数比较中使用的任何类型的变量
> *   **消息**:作为测试用例失败时显示的消息的字符串。

下面列出了两个不同的例子，说明了给定断言函数的正测试用例和负测试用例:

**例 1:阴性测试案例**

## 蟒蛇 3

```
# unit test case
import unittest

class DummyClass:
  x = 5

class TestMethods(unittest.TestCase):
    # test function to test object equality of two value
    def test_negative(self):
        firstValue = DummyClass()
        secondValue = DummyClass()
        # error message in case if test case got failed
        message = "First value & second value are not evaluated to same object !"
        # assertIs() to check that if first & second evaluated to same object
        self.assertIs(firstValue, secondValue, message)

if __name__ == '__main__':
    unittest.main()
```

**输出:**

```
F
======================================================================
FAIL: test_negative (__main__.TestMethods)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "p1.py", line 15, in test_negative
    self.assertIs(firstValue, secondValue, message)
AssertionError: <__main__.DummyClass object at 0x7f1d20251b70> is 
not <__main__.DummyClass object at 0x7f1d20251ba8> :
 First value and second value are not evaluated to same object!

----------------------------------------------------------------------
Ran 1 test in 0.000s

FAILED (failures=1)

```

**例 2:阳性检测案例**

## 蟒蛇 3

```
# unit test case
import unittest

class DummyClass:
  x = 5

class TestMethods(unittest.TestCase):
    # test function to test object equality of two value
    def test_positive(self):
        firstValue = DummyClass()
        secondValue = firstValue
        # error message in case if test case got failed
        message = "First value and second value are not evaluated to same object !"
        # assertIs() to check that if first & second evaluated to same object
        self.assertIs(firstValue, secondValue, message)

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