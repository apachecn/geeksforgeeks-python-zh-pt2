# Python |跳过测试失败

> 原文:[https://www . geesforgeks . org/python-跳过-测试-失败/](https://www.geeksforgeeks.org/python-skipping-test-failures/)

**问题–**跳过或标记所选测试为单元测试中的预期失败。

**单元测试模块**具有装饰器，可应用于选定的测试方法，以控制其处理，如下面给出的代码所示。

**代码#1 :**

```py
import unittest
import os
import platform

class Tests(unittest.TestCase):
    def test_0(self):
        self.assertTrue(True)
        @unittest.skip('skipped test')

    def test_1(self):
        self.fail('should have failed !')
        @unittest.skipIf(os.name =='posix', 'Not supported on Unix')

    def test_2(self):
        import winreg
    @unittest.skipUnless(platform.system() == 'Darwin', 'Mac specific test')

    def test_3(self):
        self.assertTrue(True)
        @unittest.expectedFailure
    def test_4(self):
        self.assertEqual(2 + 2, 5)

if __name__ == '__main__':
    unittest.main()
```

**输出:**

```py

bash % python3 testsample.py -v
test_0 (__main__.Tests) ... ok
test_1 (__main__.Tests) ... skipped 'skipped test'
test_2 (__main__.Tests) ... skipped 'Not supported on Unix'
test_3 (__main__.Tests) ... ok
test_4 (__main__.Tests) ... expected failure
----------------------------------------------------------------------
Ran 5 tests in 0.002s
OK (skipped = 2, expected failures = 1)

```

**工作原理:**

*   **skip ()** Decorator can be used to skip a test that doesn't need to be run at all.
*   **skipif ()** and **skiplesson ()** can be useful methods for writing tests that are only applicable to some platforms or Python versions or have other dependencies.

使用 **@expectedFailure** 装饰器标记已知失败的测试，但是测试框架不需要报告更多的信息。

**代码#2:应用装饰器跳过整个测试类的方法**

```py
@unittest.skipUnless(platform.system() == 'Darwin', 'Mac specific tests')
class DarwinTests(unittest.TestCase):
    ...
```