# Python |将测试输出记录到文件中

> 原文:[https://www . geesforgeks . org/python-日志记录-测试-输出到文件/](https://www.geeksforgeeks.org/python-logging-test-output-to-a-file/)

**问题–**将运行单元测试的结果写入文件，而不是打印到标准输出。

运行*单元测试*的一个非常常见的技术是在测试文件的底部包含一个小的代码片段(如下面给出的代码所示)。

**代码#1 :**

```
import unittest
class MyTest(unittest.TestCase):
    ...
if __name__ == '__main__':
    unittest.main()
```

这使得测试文件可执行，并将运行测试的结果打印到标准输出。要重定向此输出，请展开 main()调用一点，并编写自己的 main()函数，如下面给出的代码所示:

**代码#2 :**

```
import sys

def main(out = sys.stderr, verbosity = 2):
    loader = unittest.TestLoader()

    suite = loader.loadTestsFromModule(sys.modules[__name__])
    unittest.TextTestRunner(out, verbosity = verbosity).run(suite)

if __name__ == '__main__':
    with open('testing.out', 'w') as f:
        main(f)
```

**工作原理:**

*   代码有趣的地方不在于将测试结果重定向到一个文件，而是这样做暴露了 unittest 模块的一些值得注意的内部工作。
*   基本上，**单元测试模块**通过首先组装测试套件来工作。
*   这个测试套件由您定义的不同测试方法组成。一旦组装好套件，它包含的测试就会被执行。
*   单元测试的这两个部分是相互分离的。解决方案中创建的`unittest.TestLoader`实例用于组装测试套件。
*   `loadTestsFromModule()`是它定义的收集测试的几种方法之一。在这种情况下，它扫描模块中的测试用例类，并从中提取测试方法。
*   `loadTestsFromTestCase()`方法(未显示)可用于从继承自测试用例的单个类中提取测试方法。
*   `TextTestRunner`类是一个测试跑者类的例子。这个类的主要目的是执行测试套件中包含的测试。这个类就是位于`unittest.main()`函数后面的同一个测试运行程序。