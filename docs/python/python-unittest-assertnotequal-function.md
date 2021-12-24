# Python unittest–assertnoteqal()函数

> 原文:[https://www . geesforgeks . org/python-unittest-assertnoteqal-function/](https://www.geeksforgeeks.org/python-unittest-assertnotequal-function/)

Python 中的 assertNotEqual()是一个 [unittest 库](https://www.geeksforgeeks.org/unit-testing-python-unittest/)函数，用于单元测试中检查两个值的不等式。该函数将采用三个参数作为输入，并根据断言条件返回一个布尔值。如果两个输入值不相等，assertNotEqual()将返回 true，否则返回 false。

**语法:**

> assertequal(first value、secondValue、message)

**参数:**assertnoteqal()接受下面列出的三个参数，并给出解释:

*   **第一个值:**函数比较中使用的任何类型的变量
*   **秒值:**在函数比较中使用的任何类型的变量
*   **消息:**作为测试用例失败时显示的消息的字符串。

下面列出了两个不同的例子，说明了给定断言函数的正测试用例和负测试用例:

**例 1:阴性测试案例**

## 蟒蛇 3

```py
# unit test case
import unittest

class TestStringMethods(unittest.TestCase):
    # test function to test equality of two value
    def test_negative(self):
        firstValue = "geeks"
        secondValue = "geeksg"
        # error message in case if test case got failed
        message = "First value and second value are not unequal !"
        # assertNotEqual() to check unequality of first & second value
        self.assertNotEqual(firstValue, secondValue, message)

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
  File "p1.py", line 12, in test_negative
    self.assertNotEqual(firstValue, secondValue, message)
AssertionError: 'geeks' == 'geeks' : First value and second value are not unequal!

----------------------------------------------------------------------
Ran 1 test in 0.000s

FAILED (failures=1)

```

**例 2:阳性检测案例**

## 蟒蛇 3

```py
# unit test case
import unittest

class TestStringMethods(unittest.TestCase):
    # test function to test equality of two value
    def test_positive(self):
        firstValue = "geeks"
        secondValue = "geeks"
        # error message in case if test case got failed
        message = "First value and second value are not unequal !"
        # assertNotEqual() to check equality of first & second value
        self.assertNotEqual(firstValue, secondValue, message)

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