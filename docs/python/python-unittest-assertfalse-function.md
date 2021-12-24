# Python unittest–assertFalse()函数

> 原文:[https://www . geesforgeks . org/python-unittest-assertfalse-function/](https://www.geeksforgeeks.org/python-unittest-assertfalse-function/)

Python 中的 assertFalse ()是一个[单元测试库](https://www.geeksforgeeks.org/unit-testing-python-unittest/)函数，用于单元测试中比较测试值与 False。该函数将采用两个参数作为输入，并根据断言条件返回一个布尔值。如果测试值为假，则为假()将返回真，否则返回假。

> **语法:** assertFalse(测试值，消息)
> 
> **参数** : 资产假()接受两个参数，并解释如下:
> 
> *   **测试值**:布尔型变量，用于函数比较
> *   **消息**:作为测试用例失败时显示的消息的字符串。

下面列出了两个不同的例子，说明了给定断言函数的正测试用例和负测试用例:

**例 1:阴性测试案例**

## 蟒蛇 3

```
# unit test case
import unittest

class TestStringMethods(unittest.TestCase):
    # test function 
    def test_negative(self):
        testValue = True
        # error message in case if test case got failed
        message = "Test value is not false."
        # assetFalse() to check test value as false
        self.assertFalse( testValue, message)

if __name__ == '__main__':
    unittest.main()
```

**输出:**

```
F
======================================================================
FAIL: test_negative (__main__.TestStringMethods)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "p1.py", line 11, in test_negative
    self.assertFalse( testValue, message)
AssertionError: True is not false : Test value is not false.

----------------------------------------------------------------------
Ran 1 test in 0.000s

FAILED (failures=1)

```

**例 2:阳性检测案例**

## 蟒蛇 3

```
# unit test case
import unittest

class TestStringMethods(unittest.TestCase):
    # test function 
    def test_positive(self):
        testValue = False
        # error message in case if test case got failed
        message = "Test value is not false."
        # assertFalse() to check test value as false
        self.assertFalse( testValue, message)

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