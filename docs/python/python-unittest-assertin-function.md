# Python unittest–assertIn()函数

> 原文:[https://www . geesforgeks . org/python-unittest-assertin-function/](https://www.geeksforgeeks.org/python-unittest-assertin-function/)

Python 中的 assertIn()是一个 [unittest 库](https://www.geeksforgeeks.org/unit-testing-python-unittest/)函数，在单元测试中用来检查一个字符串是否包含在其他中。该函数将采用三个字符串参数作为输入，并根据断言条件返回一个布尔值。如果密钥包含在容器字符串中，它将返回 true，否则返回 false。

> **语法:** assertIn(密钥、容器、消息)
> 
> **参数**:Asertin()接受以下列出的三个参数，并进行解释:
> 
> *   **键**:在给定容器中检查其存在的字符串
> *   **容器**:搜索关键字符串的字符串
> *   **消息**:作为测试用例失败时显示的消息的字符串。

下面列出了两个不同的例子，说明了给定断言函数的正测试用例和负测试用例:

**例 1:阴性测试案例**

## 蟒蛇 3

```py
# test suite
import unittest

class TestStringMethods(unittest.TestCase):
    # test function to test whether key is present in container
    def test_negative(self):
        key = "gfg"
        container = "geeksforgeeks"
        # error message in case if test case got failed
        message = "key is not in container."
        # assertIn() to check if key is in container
        self.assertIn(key, container, message)

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
  File "/home/e920f2cd9195a3fd72bd531f7f101754.py", line 12, in test_negative
    self.assertIn(key, container, message)
AssertionError: 'gfg' not found in 'geeksforgeeks' : key is not in container.

----------------------------------------------------------------------
Ran 1 test in 0.001s

FAILED (failures=1)

```

**例 2:阳性检测案例**

## 蟒蛇 3

```py
# test suite
import unittest

class TestStringMethods(unittest.TestCase):
    # test function to test whether key is present in container
    def test_positive(self):
        key = "geeks"
        container = "geeksforgeeks"
        # error message in case if test case got failed
        message = "key is not in container."
        # assertIn() to check if key is in container
        self.assertIn(key, container, message)

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