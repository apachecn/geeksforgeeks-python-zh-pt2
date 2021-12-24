# python unit test–asserteisnotnone()函数

> 原文:[https://www . geeksforgeeks . org/python-unittest-assertinonone-function/](https://www.geeksforgeeks.org/python-unittest-assertisnotnone-function/)

Python 中的assertinotnone()是一个[单元测试库](https://www.geeksforgeeks.org/unit-testing-python-unittest/)函数，用于单元测试中检查输入值是否不是 **None** 。该函数将采用两个参数作为输入，并根据断言条件返回一个布尔值。如果输入值不等于无无()将返回真，否则返回假。

> **语法:**asserteisnotnone(test value，message)
> 
> **参数:** 无()接受两个参数，并解释如下:
> 
> *   **测试值**:测试变量作为输入值，检查是否与无相等
> *   **消息**:作为测试用例失败时显示的消息的字符串。

下面列出了两个不同的例子，说明了给定断言函数的正测试用例和负测试用例:

**例 1:阴性测试案例**

## 蟒蛇 3

```
# unit test case
import unittest

class TestMethods(unittest.TestCase):
    # test function 
    def test_negative(self):
        firstValue = None
        # error message in case if test case got failed
        message = "Test value is none."
        # assertIsNotNone() to check that if input value is not none
        self.assertIsNotNone(firstValue, message)

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
  File "p1.py", line 11, in test_negative
    self.assertIsNotNone(firstValue, message)
AssertionError: unexpectedly None : Test value is none.

----------------------------------------------------------------------
Ran 1 test in 0.000s

FAILED (failures=1)

```

**例 2:阳性检测案例**

## 蟒蛇 3

```
# unit test case
import unittest

class TestMethods(unittest.TestCase):
    # test function 
    def test_positive(self):
        firstValue = "geeks"
        # error message in case if test case got failed
        message = "Test value is  none."
        # assertIsNotNone() to check that if input value is not none
        self.assertIsNotNone(firstValue, message)

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