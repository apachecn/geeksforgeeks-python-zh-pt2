# Python |测试输出到标准输出

> 原文:[https://www . geesforgeks . org/python-testing-output-to-stdout/](https://www.geeksforgeeks.org/python-testing-output-to-stdout/)

测试是开发的关键部分，因为在 Python 执行代码之前，没有编译器来分析代码。
给定一个程序，该程序有一个输出到**标准输出(sys.stdout)** 的方法。这几乎总是意味着它向屏幕发出文本。人们喜欢为代码编写一个测试来证明，给定正确的输入，就会显示正确的输出。

使用 **unittest.mock 模块的`patch()`** 功能，模拟出 *sys.stdout* 只是一个测试，然后再放回去就很简单了，没有杂乱的临时变量或者测试用例之间泄露的被模拟状态。

**Code #1 : Example**

```py
def urlprint(protocol, host, domain):
    url = '{}://{}.{}'.format(protocol, host, domain)
    print(url)
```

默认情况下，内置的`print` 功能向`sys.stdout`发送输出。为了测试输出是否真的到达了那里，需要使用一个替身对象来模拟输出，然后断言发生了什么。

使用`unittest.mock`模块的`patch()`方法可以方便地仅在运行测试的上下文中替换对象，在测试完成后立即将事物恢复到原始状态。

**代码#2:上述代码的测试代码**

```py
from io import StringIO
from unittest import TestCase
from unittest.mock import patch
import mymodule

class TestURLPrint(TestCase):

    def test_url_gets_to_stdout(self):
        protocol = 'http'
        host = 'www'
        domain = 'example.com'
        expected_url = '{}://{}.{}\n'.format(protocol, host, domain)

        with patch('sys.stdout', new = StringIO()) as fake_out:
            mymodule.urlprint(protocol, host, domain)
            self.assertEqual(fake_out.getvalue(), expected_url)
```