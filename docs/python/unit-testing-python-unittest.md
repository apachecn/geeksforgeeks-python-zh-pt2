# Python 中的单元测试–单元测试

> 原文:[https://www.geeksforgeeks.org/unit-testing-python-unittest/](https://www.geeksforgeeks.org/unit-testing-python-unittest/)

**什么是单元测试？**
单元测试是软件测试的第一级，测试软件中最小的可测试部分。这用于验证软件的每个单元是否按设计运行。
unittest 测试框架是 python 的[xuit](https://en.wikipedia.org/wiki/XUnit)风格框架。

**方法:**
白盒测试法用于单元测试。

**unittest 框架支持的 OOP 概念:**

*   **测试夹具:**
    测试夹具被用作运行测试的基线，以确保有一个运行测试的固定环境，以便结果是可重复的。
    示例:
    *   创建临时数据库。
    *   启动服务器进程。
*   **测试用例:**
    测试用例是一组用于确定被测系统是否正常工作的条件。
*   **测试套件:**
    测试套件是测试用例的集合，用于测试一个软件程序，通过一起执行聚合的测试来显示它有一些特定的行为集。
*   **测试运行者:**
    测试运行者是设置测试执行并向用户提供结果的组件。

**基本测试结构:**
unittest 通过以下两种方式定义测试:

*   使用代码管理测试“夹具”。
*   自我测试。

```
import unittest

class SimpleTest(unittest.TestCase):

    # Returns True or False. 
    def test(self):        
        self.assertTrue(True)

if __name__ == '__main__':
    unittest.main()
```

这是使用 unittest 框架的基本测试代码，它只有一个测试。如果真为假，此测试()方法将失败。

**运行测试**

```
if __name__ == '__main__':
    unittest.main()

```

最后一个块通过命令行运行文件来帮助运行测试。

```
.
----------------------------------------------------------------------
Ran 1 test in 0.000s

OK

```

这里，在输出中。在输出的第一行意味着测试通过。
-v”选项在运行测试时被添加到命令行中，以获得更详细的测试结果。

```
test (__main__.SimpleTest) ... ok

----------------------------------------------------------------------
Ran 1 test in 0.000s

OK

```

**可能的结果:**
有三种可能的测试结果:

*   好的–这意味着所有测试都通过了。
*   失败–这意味着测试没有通过，并且引发了 AssertionError 异常。
*   错误–这意味着测试引发了一个异常，而不是 AssertionError。

让我们通过一个例子来理解 unittest 框架的实现。

**实施:**

```
# Python code to demonstrate working of unittest
import unittest

class TestStringMethods(unittest.TestCase):

    def setUp(self):
        pass

    # Returns True if the string contains 4 a.
    def test_strings_a(self):
        self.assertEqual( 'a'*4, 'aaaa')

    # Returns True if the string is in upper case.
    def test_upper(self):        
        self.assertEqual('foo'.upper(), 'FOO')

    # Returns TRUE if the string is in uppercase
    # else returns False.
    def test_isupper(self):        
        self.assertTrue('FOO'.isupper())
        self.assertFalse('Foo'.isupper())

    # Returns true if the string is stripped and 
    # matches the given output.
    def test_strip(self):        
        s = 'geeksforgeeks'
        self.assertEqual(s.strip('geek'), 'sforgeeks')

    # Returns true if the string splits and matches
    # the given output.
    def test_split(self):        
        s = 'hello world'
        self.assertEqual(s.split(), ['hello', 'world'])
        with self.assertRaises(TypeError):
            s.split(2)

if __name__ == '__main__':
    unittest.main()
```

上面的代码是一个测试 5 个字符串方法的短脚本。**单元测试。TestCase** 用于通过子类化来创建测试用例。底部的最后一段代码允许我们通过运行文件来运行所有的测试。

代码中使用的基本术语:

*   **asserteqal()–**此语句用于检查获得的结果是否等于预期结果。
*   **assertTrue()/assertFalse()–**此语句用于验证给定语句是真还是假。
*   **assertrails()–**此语句用于引发特定的异常。

测试描述:

*   **test_strings_a**
    这个测试是用来测试字符串的属性的，其中一个字符说‘a’乘以一个数字说‘x’给出的输出是 x 乘以‘a’。在这种情况下，如果结果与给定的输出匹配，assertEqual()语句将返回 true。
*   **test_upper**
    该测试用于检查给定字符串是否转换为大写。如果返回的字符串是大写的，assertEqual()语句将返回 true。
*   **test_isupper**
    这个测试是用来测试字符串的属性，如果字符串是大写的话返回 TRUE，否则返回 False。assertTrue() / assertFalse()语句用于此验证。
*   **test_strip**
    该测试用于检查函数中通过的所有字符是否已经从字符串中剥离。如果字符串被剥离并与给定的输出匹配，assertEqual()语句将返回 true。
*   **test_split**
    该测试用于检查字符串的 split 函数，该函数通过函数中传递的参数对字符串进行拆分，并将结果作为列表返回。在这种情况下，如果结果与给定的输出匹配，assertEqual()语句将返回 true。

**unittest.main()** 为测试脚本提供命令行界面。从命令行运行上述脚本时，会产生以下输出:

```
.....
----------------------------------------------------------------------
Ran 5 tests in 0.000s

OK

```

本文由**阿迪提·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。