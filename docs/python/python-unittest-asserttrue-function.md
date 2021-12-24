# Python unittest–assertTrue()函数

> 原文:[https://www . geesforgeks . org/python-unittest-asserttrue-function/](https://www.geeksforgeeks.org/python-unittest-asserttrue-function/)

Python 中的 assertTrue()是一个 [unittest 库](https://www.geeksforgeeks.org/unit-testing-python-unittest/)函数，在单元测试中用来比较测试值和 True。该函数将采用两个参数作为输入，并根据断言条件返回一个布尔值。如果测试值为真，则 assertTrue()将返回真，否则返回假。

> **语法:** assertTrue(测试值，消息)
> 
> **参数** : assertTrue()接受两个参数，并解释如下:
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
        testValue = False
        # error message in case if test case got failed
        message = "Test value is not true."
        # assertTrue() to check true of test value
        self.assertTrue( testValue, message)

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
    self.assertTrue( testValue, message)
AssertionError: False is not true : Test value is not true.

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
        testValue = True
        # error message in case if test case got failed
        message = "Test value is not true."
        # assertTrue() to check true of test value
        self.assertTrue( testValue, message)

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

**参考**:[https://docs.python.org/3/library/unittest.html](https://docs.python.org/3/library/unittest.html)