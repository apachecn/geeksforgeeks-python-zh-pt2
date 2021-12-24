# Python |让程序运行更快

> 原文:[https://www . geesforgeks . org/python-making-program-run-fast/](https://www.geeksforgeeks.org/python-making-program-run-faster/)

我们知道，Python 编程语言有点慢，目标是在没有更极端的解决方案(如 C 扩展或即时(JIT)编译器)的帮助下加快速度。
虽然优化的第一条规则可能是“不做”，但第二条规则几乎肯定是“不要优化不重要的。”为此，如果程序运行缓慢，可以从分析代码开始。通常情况下，人们会发现程序将时间花在一些热点上，比如内部数据处理循环。一旦确定了这些位置，就可以使用无意义技术来使程序运行得更快。
很多程序员开始使用 Python 作为编写简单脚本的语言。编写脚本时，很容易陷入简单编写结构非常少的代码的做法。
**代码#1:考虑该代码。**

## 蟒蛇 3

```py
# abc.py
import sys
import csv

with open(sys.argv[1]) as f:
    for row in csv.reader(f):
        # Some kind of processing
```

一个鲜为人知的事实是，像这样在全局范围内定义的代码比在函数中定义的代码运行得慢。速度差异与局部变量和全局变量的实现有关(涉及局部变量的操作更快)。所以，简单地把脚本语句放在一个函数中，让程序运行得更快。

**代码#2 :**

## 蟒蛇 3

```py
# abc.py
import sys
import csv

def main(filename):
    with open(filename) as f:
        for row in csv.reader(f):
        # Some kind of processing

main(sys.argv[1])
```

速度差异很大程度上取决于正在执行的处理，但 15-30%的加速并不少见。

### 选择性地消除属性访问–

点(。)运算符访问属性是有代价的。在封面下，这会触发特殊的方法，例如 __getattribute__()和 __getattr__()，这通常会导致字典查找。
通过使用模块导入名称形式的*导入，以及选择使用绑定方法，通常可以避免属性查找，如下面给出的代码片段所示–
**代码#3 :*** 

## 蟒蛇 3

```py
import math

def compute_roots(nums):
    result = []
    for n in nums:
        result.append(math.sqrt(n))
    return result

# Test
nums = range(1000000)
for n in range(100):
    r = compute_roots(nums)
```

**输出:**

```py
This program runs in about 40 seconds when running on the machine.

```

**代码#4:更改 compute _ roots()函数**

## 蟒蛇 3

```py
from math import sqrt

def compute_roots(nums):
    result = []
    result_append = result.append
    for n in nums:
        result_append(sqrt(n))
    return result
```

**输出:**

```py
This program runs in about 29 seconds when running on the machine.

```

这两个版本的代码之间唯一的区别是消除了属性访问。代码没有使用 math.sqrt()，而是使用 sqrt()。result.append()方法被附加到局部变量 re
sult_append 中，并在内部循环中重用。
但是，必须强调的是，这些变化只在频繁执行的代码中有意义，例如循环。所以，这种优化真的只有在精心挑选的地方才有意义。

### 了解变量的位置–

如前所述，局部变量比全局变量快。对于经常访问的名称，可以通过使这些名称尽可能本地化来获得加速。
**代码# 5:compute _ root()函数的修改版**

## 蟒蛇 3

```py
import math

def compute_roots(nums):
    sqrt = math.sqrt
    result = []
    result_append = result.append
    for n in nums:
        result_append(sqrt(n))
    return result
```

在这个版本中，sqrt 已经从数学模块中取出，并放入局部变量中。这段代码将运行大约 25 秒(比前一个版本(耗时 29 秒)有所改进)。额外的加速是由于 sqrt 的本地查找比 sqrt 的全局查找快一点。
局部性参数在类中工作时也适用。一般来说，查找像 self.name 这样的值比访问局部变量要慢得多。在内部循环中，将经常访问的属性提升到一个局部变量中可能会有好处，如下面给出的代码所示。
**代码#6 :**

## 蟒蛇 3

```py
# Slower
class SomeClass:
    ...
    def method(self):
        for x in s:
            op(self.value)
# Faster
class SomeClass:
    ...
    def method(self):
        value = self.value
        for x in s:
            op(value)
```

### **动态分型:**

Python 速度慢的原因是因为它是动态类型的，现在我们将更详细地讨论这一点，但我想与 Java 这样的语言进行比较。现在在 Java 中，一切都是静态类型的，这种语言实际上是在运行之前编译的，不像 Python 那样在运行时通过解释器编译。现在在 Java 中发生的是，当你写代码时，你需要定义你的每一个变量将是什么类型，你的方法和函数将返回什么类型，并且你必须精确地定义在你的代码中所有的东西将是什么类型。虽然这会导致更长的开发时间，并且需要更长的时间来编写代码，但是它确实在编译时提高了效率，这实际上是可行的，而且比 Python 代码快得多，因为如果您知道特定变量或对象的类型， 您可以执行大量不同的优化，并避免在实际运行代码时执行大量不同的检查，因为这些检查是在编译时执行的。在 Java 中，本质上，您不能编译任何没有实际错误的 Java 代码，甚至就像编写代码时键入的错误一样。您将尝试编译它，它会说，这种类型不准确，您不能这样做， 您不能编译它，因为它知道，当运行时，这是行不通的，所以基本上所有这些实际上需要在 Python 中执行的检查都是预先执行的，并且由于这种静态类型的长度，只做了大量的优化。 现在人们可能会问这样一个问题，为什么 Python 不这样做？答案是 Python 是动态类型的，这意味着任何变量都可以改变它的类型，并且可以在程序运行的任何时候改变它的值，这意味着我们不能事先编译整个程序，因为我们不能一次完成所有这些检查，因为我们不知道这些变量会是什么类型，它们会在运行时改变， 不同的事情将会发生，正因为如此，我们不能得到所有这些优化，我们可能会在一个较低层次的语言，如 Java，C 或 C++，这是一种基本的原因，语言是缓慢的，这种动态类型和任何快速语言将有一个编译器，它将运行通过，它将确保一切都是好的， 它将在运行时实际运行代码之前进行所有这些检查，在 Python 中发生的是，您的所有代码实际上都是在运行时编译和检查的，因此，与其在运行代码之前编译它并预先花费所有这些时间，还不如进行许多不同的检查，以确保说这个对象是正确的，这些类型是正确的，一切都是一样的。

### 并发性:

现在接下来要讲的显然是 Python 中缺乏并发性。这将是速度的主要因素，如果你用 Java，C 写一个应用程序，你可以把所有的东西分散到多个线程中，这允许你利用你的中央处理器的所有核心，所以在现代计算中，为了打破这一点，我们大多数人有四个核心中央处理器或更高，这允许我们实际上同时运行四个任务，现在用 Python 这是不可能的。Python 说， 对于每个解释器，我们一次最多只能有一个线程运行，一个线程只是发生在 CPU 内核上的某种操作，这意味着即使我们在 Python 程序中创建了许多线程，我们也只能使用一个 CPU 内核，而在 Java 程序或 C 程序中，我们可以使用全部八个或全部四个，这显然会导致速度提高 4 倍或 8 倍，现在我们可以通过使用多处理在 Python 中解决这个问题，但是这有一些问题。