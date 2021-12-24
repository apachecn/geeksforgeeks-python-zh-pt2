# 测试 Python 中某个函数是否抛出异常

> 原文:[https://www . geesforgeks . org/test-if-a-function-throw-exception-in-python/](https://www.geeksforgeeks.org/test-if-a-function-throws-an-exception-in-python/)

**单元测试**单元测试框架用于验证代码是否按照设计执行。为了实现这一点，unittest 以面向对象的方式支持一些重要的方法:

*   试验夹具
*   判例案件
*   测试套
*   测试运行程序

从[https://www.geeksforgeeks.org/unit-testing-python-unittest/](https://www.geeksforgeeks.org/unit-testing-python-unittest/)可以对上述术语有更深入的了解

**assertrails()**–它允许封装一个异常，这意味着测试可以在不退出执行的情况下抛出一个异常，这通常是未处理异常的情况。如果引发异常，测试将通过；如果引发另一个异常，测试将出错；如果没有引发异常，测试将失败。

有两种方法可以使用资产提升:

1.  using keyword arguments.

    ```py
    assertRaises(exception, function, *args, **keywords)

    ```

    只需将异常、可调用函数和可调用函数的参数作为引发异常的关键字参数传递。

2.  using context manager 

    ```py
    assertRaises(exception)

    ```

    进行一个函数调用，该调用应该用上下文引发异常。上下文管理器将捕获一个异常，并将其存储在对象的异常属性中。当我们必须对引发的异常执行额外检查时，这很有用。

当 assert 语句引发的异常不同于预期异常时，如果函数或**没有引发异常，我们编写的 unittest 将失败**。因此，通过这种方法，我们可以检查一个函数是否引发了异常。****

**例 1 :**

## 蟒蛇 3

```py
import unittest

class MyTestCase(unittest.TestCase):

   # Returns true if 1 + '1' raises a TypeError
   def test_1(self):
      with self.assertRaises(Exception):
         1 + '1'

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

这里，在输出中。在输出的第一行意味着测试已经通过，并且函数在添加一个**整数**值和一个**字符串**值时抛出了一个**类型错误**的异常。

**例 2 :**

## 蟒蛇 3

```py
import unittest

class MyTestCase(unittest.TestCase):

   # Returns false if 1 + 1 raises no Exception
   def test_1(self):
      with self.assertRaises(Exception):
         1 + 1

if __name__ == '__main__': 
    unittest.main()
```

**输出:**

```py
F
======================================================================
FAIL: test_1 (__main__.MyTestCase)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "/home/5bc65171e57a3294596f5333f4b7ed53.py", line 6, in test_1
    1 + 1
AssertionError: Exception not raised

----------------------------------------------------------------------
Ran 1 test in 0.001s

FAILED (failures=1)
```

因为将整数加到整数(在本例中为 1 + 1)上不会引发任何异常，所以会导致 unittest 失败。

**例 3:**

## **蟒蛇 3**

```py
import unittest

class MyTestCase(unittest.TestCase):

  # Returns true if 100 / 0 raises an Exception
   def test_1(self):
      with self.assertRaises(ZeroDivisionError):
         100 / 0

if __name__ == '__main__': 
    unittest.main()
```

****输出:****

 ```py
.
----------------------------------------------------------------------
Ran 1 test in 0.000s

OK
```

任何被 0 除的数都会给**零除错误或**例外。因此，在示例 3 中，当 100 被 0 除时，它会引发零除错误类型的异常，导致 unittest 通过。因此。in 输出表示测试已经通过。

**例 4 :**

## 蟒蛇 3

```py
import unittest

class MyTestCase(unittest.TestCase):

  # Returns true if GeeksforGeeks.txt file is not present and raises an EnvironmentError
  # Exception
  # In this example expected exception is RuntimeError while generated exception is
  # EnvironmentError, thus returns false
    def test_1(self):
        with self.assertRaises(RuntimeError):
            file = open("GeeksforGeeks.txt", 'r')

if __name__ == '__main__':
    unittest.main()
```

**输出:**

```py
E
======================================================================
ERROR: test_1 (__main__.MyTestCase)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "/home/8520c06939bb0023b4f76f381b2c8cf2.py", line 11, in test_1
    file = open("GeeksforGeeks.txt", 'r')
FileNotFoundError: [Errno 2] No such file or directory: 'GeeksforGeeks.txt'

----------------------------------------------------------------------
Ran 1 test in 0.001s

FAILED (errors=1)
```

当我们试图打开一个不存在的文件时，它会引发一个 **IOError** ，它是**环境错误**的子类。在上面的例子中，unittest 失败了，因为函数引发的异常类型应该是 **RuntimeError** 类型，相反它引发了 **EnvironmentError** 的异常。由于**异常引发的**和**异常预期的**不同，因此会产生错误。**