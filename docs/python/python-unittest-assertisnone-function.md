# Python unittest–assertione()函数

> 原文:[https://www . geesforgeks . org/python-unittest-assertione-function/](https://www.geeksforgeeks.org/python-unittest-assertisnone-function/)

Python 中的assertione()是一个[单元测试库](https://www.geeksforgeeks.org/unit-testing-python-unittest/)函数，用于单元测试中检查输入值是否为 **None** 。该函数将采用两个参数作为输入，并根据断言条件返回一个布尔值。如果输入值等于无无()将返回真，否则返回假。

> **语法:**断言(测试值，消息)
> 
> **参数:** 阿赛司通()接受两个参数，并解释如下:
> 
> *   **测试值**:测试变量作为输入值，检查是否与无相等
> *   **消息**:作为测试用例失败时显示的消息的字符串。

下面列出了两个不同的例子，说明了给定断言函数的正测试用例和负测试用例:

**例 1:阴性测试案例**

## 蟒蛇 3

```py
# unit test case
import unittest

class TestMethods(unittest.TestCase):
    # test function 
    def test_negative(self):
        firstValue = "geeks"
        # error message in case if test case got failed
        message = "Test value is not none."
        # assertIsNone() to check that if input value is none
        self.assertIsNone(firstValue, message)

if __name__ == '__main__':
    unittest.main()
```

**输出:**

```py
F
======================================================================
FAIL: test_negative (__main__.TestMethods)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "p1.py", line 14, in test_negative
    self.assertIsNone(firstValue, message)
AssertionError: 'geeks' is not None : Test value is not none.

----------------------------------------------------------------------
Ran 1 test in 0.000s

FAILED (failures=1)

```

**例 2:阳性检测案例**

## 蟒蛇 3

```py
# unit test case
import unittest

class TestMethods(unittest.TestCase):
    # test function 
    def test_positive(self):
        firstValue = None
        # error message in case if test case got failed
        message = "Test value is not none."
        # assertIsNone() to check that if input value is none
        self.assertIsNone(firstValue, message)

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