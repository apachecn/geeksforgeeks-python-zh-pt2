# 为什么 PyPy3 比 Python3 更受青睐？

> 原文:[https://www . geeksforgeeks . org/why-pypy 3-优先于 python3/](https://www.geeksforgeeks.org/why-pypy3-is-preferred-over-python3/)

*“如果你想让你的代码运行得更快，你可能应该只使用 PyPy。”*
*—吉多·范·罗苏姆(Python 的创造者)*

如果你曾经用 Python 编码过，你就知道它和其他一些流行的编程语言相比要慢多少。在大多数在线代码评判中，Python 的时间限制是 C 语言的 5 倍多，是 Java 的两倍多。

Python 之所以在执行时通常要多花 10 到 100 倍的时间，是因为它是一种动态类型化的高级语言。无论你的代码有多优化，它在执行时间上都不能超过 C/C++。然而，Python 是一种有趣且易于使用的语言，这就是为什么用它构建程序要快得多的原因。

### 为了解决这个问题，让我们了解一下 Python 是什么

Python 不是一种单一的语言，而是实现 python 代码的一种方式。默认的、使用最广泛的 Python 实现是 CPython。CPython 中代码的执行流程是:

1.  解释器检查逻辑和语法错误
2.  在没有发现错误之后，格式化的代码被转换成字节码
3.  字节码被发送到 PVM(Python 虚拟机)，它将代码转换成机器可读的语言，由中央处理器执行操作。

但是，CPython 不是实现 Python 的方法。事实上，还有许多其他实现:

*   IronPython(运行在。NET)
*   Jython(运行在 Java 虚拟机上的 Python)
*   PyPy(一种带有 JIT 编译器的快速 python 实现)
*   无堆栈 Python(支持微线程的 CPython 分支)
*   MicroPython(运行在微控制器上的 Python)

**pypypy**是使用与其共同开发的 **RPython** 语言构建的。RPython(限制性 Python)是 Python 语言的一个子集，它对 Python 语言进行了一些限制，以使其运行得更快。用它代替 **CPython** 的主要原因是它的速度。具体来说，它的运行速度通常比 CPython 快 4.4 倍。PyPy 实现了 Python 2.7.13 和 3.6.9。它支持所有核心语言，通过了 Python 2.7 测试套件和大部分 3.6 测试套件(稍加修改)它支持大多数常用的 Python 标准库模块。这意味着在大多数情况下，您的 python 代码无需任何修改即可运行。

PyPy 使用一种称为元跟踪的技术，它将解释器转换为跟踪 JIT(即时)编译器，这是一种在运行时执行涉及编译的代码的方式。它不仅运行速度更快，而且比 Python 有更好的内存利用率。它还与 Python 中使用最多的一些库高度兼容。

其中一些是:

*   ctypes(类型)
*   django
*   sqllcemy(SQL 语法)
*   瓶
*   扭曲的
*   塔架
*   divmod 的 nevow
*   皮格莱特
*   枕头
*   xml 格式
*   NumPy

有这么多优点，也必然会有一些缺点。

### PyPy 的缺点

PyPy 无法执行所有 Python 代码。可能需要对 Python 代码进行一些修改才能执行。外部的 C-API 已经在 PyPy 中重新实现了，但是有时一些 C-抽象会泄露到 CPython 上并被滥用，甚至可能在不知不觉中被滥用。它需要一段“预热”时间，由于加载和编译字节码所花费的时间，这会在应用程序的初始执行中造成轻微到明显的延迟。执行越小，性能越差。