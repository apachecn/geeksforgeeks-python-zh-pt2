# 竞争程序员的技巧和诀窍|第 2 集(用于竞争编程的语言)

> 原文:[https://www . geeksforgeeks . org/给有竞争力的程序员的提示和技巧-设置-2-哪种语言应该用于有竞争力的编程/](https://www.geeksforgeeks.org/tips-and-tricks-for-competitive-programmers-set-2-which-language-should-be-used-for-competitive-programming/)

这是一个经常被问到的问题，即在竞争性编程中，哪种语言更有效。这是人们不应该担心的事情，因为重要的是逻辑，而不是语言。大多数语言或多或少都是相同的，但到目前为止，最受欢迎的语言是 C++，原因如下。

[T1】巨蟒 T3】](https://www.geeksforgeeks.org/python/)

**简单容易:** Python 简单，容易写(我们需要少打字)，拥有庞大的模块集合，几乎拥有你能想象到的所有功能。

**数据类型:**一般首选 Python 作为[它对整数的内存没有任何上限](https://www.geeksforgeeks.org/what-is-maximum-possible-value-of-an-integer-in-python/)。此外，人们不需要指定它是哪种数据类型，这样的事情使编码变得更容易，但同时也使编译变得困难(参考编译所花费的时间)。

**执行慢:** Python 程序相对于 Java 来说一般都比较慢(参见[这一篇](https://www.python.org/doc/essays/comparisons/))。由于 Python 的执行时间很长，所以它在启动阶段就被排除了。

现在我们主要剩下 Java、C、C++，这里很难比较，主要取决于用户，但是让我们讨论一下它们的优缺点。

[T1】爪哇 T3】](https://www.geeksforgeeks.org/java/)

*   **STL vs Containers:**c++中的 STL 真的设计得很好，而有些人更喜欢 Java Containers。几乎没有 STL 没有直接解决方案的情况。例如，STL 中的 priority_queue 不支持 Dijkstra 最短路径算法和 Prim 算法实现所需的减少键操作

**Java 中的异常处理是无与伦比的:**与 C++相比，Java 代码提供了更强的异常处理。例如，在 Java 中跟踪 ArrayIndexOutOfBound 异常或分段错误更容易。C++/C 可能会给你错误的答案，但在这种情况下，Java 肯定是可靠的。

**时间限制超过**:你可能会得到 TLE，因为 Java 在时间限制方面稍微慢一点(特别是在 SPOJ 中)，Codeforces。

**大整数和正则表达式:**相对于编程竞赛来说，Java 没有什么优势。大整数、正则表达式和几何库就是其中的一部分。

*   现在让我们进行 C++。

[**c++**T3**和**T6**C**T9】](https://www.geeksforgeeks.org/c-plus-plus/)

*   **C++的速度堪比 C:** 许多 C 程序也是有效的 C++程序——并且这类 C 程序在编译时以相同的速度运行
*   **C++不强制面向对象编程:**C++语言包含一些便于面向对象编程的语言扩展，c++不强制任何地方的面向对象设计——它只是允许这样做。
*   **参数化类型**模板关键字允许程序员编写算法的泛型(类型不可知)实现。其中，在 C 语言中，可以编写一个通用的列表实现，其元素如下:

```py
    struct element_t 
    {
       struct element_t *next, *prev;
       void *element;
    };
```

*   C++允许人们写一些类似的东西:

```py
template <typename T>
struct element_t 
{
    element_t<T> *next, *prev;
    T element;
};
```

*   **更大的标准库:** C++允许完全使用 C 标准库，C++包括自己的库，包括[标准模板库](http://geeksquiz.com/the-c-standard-template-library-stl/)。STL 包含许多有用的模板，像上面的排序例程。它包括有用的通用数据结构，如列表、地图、集合等。像排序例程一样，其他的 STL 例程和数据结构是根据程序员的特定需求“定制”的——程序员所要做的就是填写类型。
    例如，如果我们需要为一个问题实现二分搜索法，我们将不得不编写我们自己的函数，而在 C++中[二分搜索法 STL 例程](http://geeksquiz.com/binary-search-algorithms-the-c-standard-template-library-stl/)被定义为

```py
 binary_search(startaddress, endaddress, valuetofind)
```

**C++ vs Java**
**Java 代码更长**一个程序员在用 Java 编程的时候需要写更多的东西

*   **Java 比较啰嗦**:在 C++中，只写 scanf/printf，Input Output 比较简单。在 Java 中，您需要 BufferedReader 类，这同样是乏味的。

**C++ STL vs Java Containers:** 大部分程序员发现使用 STL 更容易。

**C++更受欢迎:**无论是起源年份还是使用舒适度，但 C++在使用该语言的用户数量上胜过 Java。

**C++节省时间:**众所周知，Java 比 C++慢。我们通常需要多次编译和运行程序来测试它们。在 C++中花费的时间相对要少得多。因此，在有限的时间竞赛中，我们的时间可以节省。

总结一下，C++是迄今为止最受欢迎的语言，其次是 Java，当涉及到编程竞赛时，但你应该总是选择一种你觉得舒服的语言。对任何语言都充满信心是最重要的。永远不要选择一种你“刚刚学会”的语言，因为用那种语言表达自己是很困难的。

对于主题，从简单的问题开始，然后转向特别的问题，然后涵盖标准[算法](https://www.geeksforgeeks.org/fundamentals-of-algorithms/)和[数据结构](https://www.geeksforgeeks.org/data-structures/)。最后学会优化你的代码。所有这些时间都强调学习数学，因为[数学算法](https://www.geeksforgeeks.org/fundamentals-of-algorithms/#MathematicalAlgorithms)是超越竞争性编程的重要部分。

**快乐编码！！**

参考:[http://unthought.net/c++/c_vs_c++.html](http://unthought.net/c++/c_vs_c++.html)

本文由我们的校园极客们独家撰写- **拉胡尔·阿加瓦尔、阿迪蒂亚·查特吉、舒巴姆·辛格·拉杰普特、维内特·塞西亚、赛伊加·雷迪、沙伊·赛斯、穆迪特·马赫什瓦里、阿贾伊·贾恩和鲁奇尔·加尔格。**

如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

[竞技程序员的技巧和诀窍|第 1 集(针对初学者)](https://www.geeksforgeeks.org/tips-and-tricks-for-competitive-programmers-set-1-for-beginners/)

如果你是竞争性编程的新手，[这篇文章](https://www.geeksforgeeks.org/how-to-begin-with-competitive-programming/)可能会帮助你写第一段代码。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论