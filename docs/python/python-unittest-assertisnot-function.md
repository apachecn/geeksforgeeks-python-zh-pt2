# Python unittest–assertinot()函数

> 原文:[https://www . geesforgeks . org/python-unittest-assertison-function/](https://www.geeksforgeeks.org/python-unittest-assertisnot-function/)

Python 中的 assertIsNot()是一个 [unittest 库](https://www.geeksforgeeks.org/unit-testing-python-unittest/)函数，在单元测试中用来测试第一个和第二个输入值是否对同一个对象求值。该函数将采用三个参数作为输入，并根据断言条件返回一个布尔值。如果两个输入没有对同一个对象求值，那么 assertIsNot()将返回 true，否则返回 false。

> **语法:**assert not(first value，secondValue，message)
> 
> **参数**:assertinot()接受三个参数，并解释如下:
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
    # test function 
    def test_negative(self):
        firstValue = DummyClass()
        secondValue = firstValue
        # error message in case if test case got failed
        message = "First value & second value evaluates to same object !"
        # assertIs() to check that if first & second don't evaluated to same object
        self.assertIsNot(firstValue, secondValue, message)

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
    self.assertIsNot(firstValue, secondValue, message)
AssertionError: unexpectedly identical: <__main__.DummyClass object at 0x7f75c2e33b70> 
: First value & second value evaluates to same object!

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
        secondValue = DummyClass()
        # error message in case if test case got failed
        message = "First value and second value evaluated to same object !"
        # assertIs() to check that if first & second don't evaluates to same object
        self.assertIsNot(firstValue, secondValue, message)

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