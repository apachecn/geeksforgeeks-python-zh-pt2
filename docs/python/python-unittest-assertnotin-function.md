# Python unittest–assertNotIn()函数

> 原文:[https://www . geesforgeks . org/python-unittest-assertnotin-function/](https://www.geeksforgeeks.org/python-unittest-assertnotin-function/)

Python 中的 assertNotIn ()是一个[单元测试库](https://www.geeksforgeeks.org/unit-testing-python-unittest/)函数，用于单元测试中检查一个字符串是否不包含在其他中。该函数将采用三个字符串参数作为输入，并根据断言条件返回一个布尔值。如果密钥不包含在容器字符串中，它将返回 true，否则返回 false。

> **语法:**资产通知(密钥、容器、消息)
> 
> **参数** : 资产通知()接受三个参数，并解释如下:
> 
> *   **键**:在给定容器中检查其存在的字符串
> *   **容器**:搜索关键字符串的字符串
> *   **消息**:作为测试用例失败时显示的消息的字符串。

下面列出了两个不同的例子，说明了给定断言函数的正测试用例和负测试用例:

**例 1:阴性测试案例**

## 蟒蛇 3

```
# test suite
import unittest

class TestStringMethods(unittest.TestCase):
    # test function to test whether key is present in container
    def test_negative(self):
        key = "geeks"
        container = "geeksforgeeks"
        # error message in case if test case got failed
        message = "key is present in container."
        # assertNotIn() to check if key is in container
        self.assertNotIn(key, container, message)

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
  File "/home/e99e85838dde0c8ef29ab17fef478979.py", line 12, in test_negative
    self.assertNotIn(key, container, message)
AssertionError: 'geeks' unexpectedly found in 'geeksforgeeks' : key is present in container.

----------------------------------------------------------------------
Ran 1 test in 0.000s

FAILED (failures=1)
```

**例 2:阳性检测案例**

## 蟒蛇 3

```
# test suite
import unittest

class TestStringMethods(unittest.TestCase):
    # test function to test whether key is present in container
    def test_positive(self):
        key = "gfgs"
        container = "geeksforgeeks"
        # error message in case if test case got failed
        message = "key is present in container."
        # assertNotIn() to check if key is in container
        self.assertNotIn(key, container, message)

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