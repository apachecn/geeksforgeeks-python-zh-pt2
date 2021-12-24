# Python unittest–assertAlmostEqual()函数

> 原文:[https://www . geesforgeks . org/python-unittest-assertalmostequal-function/](https://www.geeksforgeeks.org/python-unittest-assertalmostequal-function/)

Python 中的 assertAlmostEqual ()是一个[单元测试库](https://www.geeksforgeeks.org/unit-testing-python-unittest/)函数，用于单元测试中检查两个给定值是否几乎相等。该函数将接受五个参数作为输入，并根据断言条件返回一个布尔值。

该功能通过计算差值，舍入到给定的小数位数*位*(默认为 7)，并与零进行比较，检查*第一位*和*第二位*是否大致相等。

如果提供的是*δ*而不是*位置*，那么*第一个*和*第二个*之间的差值必须小于或等于*δ*。

> **语法:** assertAlmostEqual(第一，第二，位置=7，消息=无，增量=无)
> 
> **参数** : assertAlmostEqual ()接受下面列出的三个参数并给出解释:
> 
> *   **First** : The first input value (integer)
> *   **Second** : the second input value (integer)
> *   **Bit** : Decimal digit of approximate value
> *   **Message** A string statement is used as the message displayed when the test case fails.
> *   **δ** : The δ value is approximate.

下面列出了两个不同的例子，说明了给定断言函数的正测试用例和负测试用例:

**例:**

## 蟒 3

```
# test suite
import unittest

class TestStringMethods(unittest.TestCase):
    # negative test function to test if values are almost equal with place
    def test_negativeWithPlaces(self):
        first = 4.4555
        second = 4.4566
        decimalPlace = 3
        # error message in case if test case got failed
        message = "first and second are not almost equal."
        # assert function() to check if values are almost equal
        self.assertAlmostEqual(first, second, decimalPlace, message)

    # positive test function to test if values are almost equal with place
    def test_positiveWithPlaces(self):
        first = 4.4555
        second = 4.4566
        decimalPlace = 2
        # error message in case if test case got failed
        message = "first and second are not almost equal."
        # assert function() to check if values are almost equal
        self.assertAlmostEqual(first, second, decimalPlace, message)

    # negative test function to test if values are almost equal with delta
    def test_negativeWithDelta(self):
        first = 4.4555
        second = 4.4566
        delta = 0.0001
        # error message in case if test case got failed
        message = "first and second are not almost equal."
        # assert function() to check if values are almost equal
        self.assertAlmostEqual(first, second, None, message, delta)

    # positive test function to test if values are almost equal with delta
    def test_positiveWithDelta(self):
        first = 4.4555
        second = 4.4566
        delta = 0.002
        # error message in case if test case got failed
        message = "first and second are not almost equal."
        # assert function() to check if values are almost equal
        self.assertAlmostEqual(first, second, None, message, delta)

if __name__ == '__main__':
    unittest.main()
```

**输出:**

```
FF..
======================================================================
FAIL: test_negativeWithDelta (__main__.TestStringMethods)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "/home/2c36bbd2c940a6c7b81a901ebfdd2ad8.py", line 34, in test_negativeWithDelta
    self.assertAlmostEqual(first, second, None, message, delta)
AssertionError: 4.4555 != 4.4566 within 0.0001 delta : first and second are not almost equal.

======================================================================
FAIL: test_negativeWithPlaces (__main__.TestStringMethods)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "/home/2c36bbd2c940a6c7b81a901ebfdd2ad8.py", line 14, in test_negativeWithPlaces
    self.assertAlmostEqual(first, second, decimalPlace, message)
AssertionError: 4.4555 != 4.4566 within 3 places : first and second are not almost equal.

----------------------------------------------------------------------
Ran 4 tests in 0.001s

FAILED (failures=2)

```

**参考**:https://docs.python.org/3/library/unittest.html