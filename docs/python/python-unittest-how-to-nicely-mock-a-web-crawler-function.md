# Python unittest——如何很好地模拟网络爬虫功能？

> 原文:[https://www . geeksforgeeks . org/python-unittest-how-good-mock-a-web-crawler-function/](https://www.geeksforgeeks.org/python-unittest-how-to-nicely-mock-a-web-crawler-function/)

**先决条件:** [Python |单元测试对象修补](https://www.geeksforgeeks.org/python-unit-test-objects-patching-set-1/)

单元测试是软件测试的第一级，测试软件中最小的可测试部分。这用于验证软件的每个单元是否按设计运行。 [Unittest](https://www.geeksforgeeks.org/unit-testing-python-unittest/) 框架是 python 的 xUnit 风格框架。在深入探讨“如何很好地模拟网络爬虫”之前，让我们先了解一些基本原理。

### 什么是模拟？

**Mock** 是 **unittest** 模块的子模块(类)。模拟模块允许我们用模拟对象替换整个系统中我们正在测试的特定部分。

### 要执行的步骤:

*   从 *unittest.mock* 模块导入模拟类。
*   创建*模拟*类的实例。
*   设置模拟对象的方法。
*   打印结果

### **示例:**

让我们通过模仿另一个 python 类来理解 mock。在这个例子中，我们将看到在我们模拟的类上调用的方法，以及传递给它们的参数。

T2T4

```
# importing mock from unittest.mock module
from unittest.mock import Mock

# defining instance of our mock
our_mock = Mock()

# defining mock object’s __str__ method
our_mock.__str__ = Mock(return_value='GeeksforGeeks Mocking Example')

# executing str function for output
print(str(our_mock))
```

T5

**输出:**

```
GeeksforGeeks Mocking Example
```