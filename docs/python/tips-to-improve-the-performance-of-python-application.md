# 提高 Python 应用程序性能的技巧

> 原文:[https://www . geeksforgeeks . org/tips-提高 python 应用程序性能/](https://www.geeksforgeeks.org/tips-to-improve-the-performance-of-python-application/)

**Python**……我们都知道这种语言的流行。Python 是一种强大的高阶编程语言。在今天的科技世界里，它几乎无处不在。无论您是在构建 web 应用程序还是在使用机器学习，这种语言都已经成为开发人员的首选。说到优化开发人员的工作效率，Python 是第一位的。您可以立即创建一个程序，并解决客户的业务问题。

![Tips-to-Improve-the-Performance-of-Python-Application](img/b9f21e241b0445c927c97291ba4064a2.png)

用[**【Python】**](https://www.geeksforgeeks.org/python-language-introduction/)写一个解决方案，并不能给你一个优化的保证，反而提高了 Python 的性能。然而，在用 Python 编写代码时，您可以遵循一些策略来帮助您提高应用程序的性能。这些策略可以使您的应用程序更快。

一些技巧或策略会对执行产生很大的影响，而另一些则会产生更小、更微妙的影响。让我们详细讨论这些技巧…

### 1.使用内置函数

任何语言的内置函数总是有用的，因为您不需要从头开始编写代码。Python 也是如此。Python 附带了许多有用的库和内置函数。这些库有助于在开发项目的几个地方编写特性。您可以编写高质量、高效的代码，但是很难击败底层的库。

Python 库经过了严格的优化和测试(就像您的代码一样)。这些内置函数在您的项目中很容易使用。您的项目中不会有多余的代码，并且代码会得到很好的优化。

### 2.编写自己的生成器

在 Python 中，尽可能使用生成器。它允许您一次返回一个项目，而不是一次返回所有项目。Xrange()函数是 Python 2 中的一个生成器，类似于 Python 3 中的 range()函数。

如果你使用列表，你应该编写自己的生成器。生成器给你懒惰的评价，内存将被有效利用。如果你正在阅读大量的大文件，生成器非常有用。您可以处理单个块，而不用担心文件的大小。

下面是一个例子供你帮助…

```py
import requests
import re

def get_pages(link):
  pages_to_visit = []
  pages_to_visit.append(link)
  pattern = re.compile('https?')
  while pages_to_visit:
    current_page = pages_to_visit.pop(0)
    page = requests.get(current_page)
    for url in re.findall('<a href="([^"]+)">', str(page.content)):
      if url[0] == '/':
        url = current_page + url[1:]
      if pattern.match(url):
        pages_to_visit.append(url)
    yield current_page
webpage = get_pages('http://www.example.com')
for result in webpage:
  print(result)
```

上面的示例在执行某种操作时返回一个页面。在上面的例子中，我们正在打印链接。如果没有生成器，您需要同时获取和处理数据，或者在开始处理之前收集所有链接。在这种情况下，您的代码将更干净、更快、更容易测试。

### 3.使用列表理解

就像在任何其他语言中一样，使用循环在 Python 中很常见。您可能在 Python 中使用了列表理解。列表理解是更快执行代码的好方法。列表理解是简洁的，创建一个新的列表更容易，因为它加快了这个过程。假设，你想找出特定范围内所有奇数的平方。您可以使用下面给出的循环来解决这个问题…

```py
square_numbers = []
  for n in range(0,10):
    if n % 2 == 1:
      square_numbers.append(n**2)
```

你可以用一行的列表理解来解决同样的问题…

```py
square_numbers = [n**2 for n in range(1,10) if n%2 == 1]
```

您可以看到第二种方法更加优化，可读性更强。运行此代码后，您将获得更快的结果。所有这些小代码库中的提示都有很小的范围。这种方法不会有太大的不同，但在其他情况下，当你试图节省一些时间时，它会有很大的不同。您的程序将运行得更快。

### 4.使用 xrange()代替 range()

在 Python 2 中，为了迭代循环，我们可以使用 range()和 xrange()函数。第一个函数将该范围内的所有数字存储在内存中，它和 range 一样线性变大。其他函数 xrange()返回生成器对象。如果你循环使用这些对象号，它们将只在需要的时候在内存中可用。

```py
import sys
counter = range(1, 70000)
print(sys.getsizeof(counter))
```

上面的代码返回 560064。如果在相同的范围内使用 xrange，它将返回 40。如果你用 Python 2 编写应用程序，那么交换函数会对内存使用产生很大影响。在 Python 3 中，默认情况下实现 xrange()功能。如果没有 xrange()函数，那么 range()函数的行为将是这样的。

### 5.使用集合和联合

如果您在代码中使用了太多的循环，那么您将会给服务器带来不必要的压力。这将是最有效的方法。您可以在两个列表中获得重叠值。您可以使用嵌套 for 循环来实现这一点，如下所示…

```py
a = [7,8,1,0,2]
b = [2,8,9,1,3]

overlaps = []
for x in a:
  for y in b:
    if x==y:
      overlaps.append(x)

print(overlaps)
```

上面的代码将打印列表[8，1，2]。在这里，比较的数量会变得非常大，非常快。让我们看看另一种方法…

```py
a = [7,8,1,0,2]
b = [2,8,9,1,3]

overlaps = set(a) & set(b)

print(overlaps)
```

上面的代码将打印字典{8，1，2}。在这里你会得到一个很好的速度和内存颠簸的结果。

### 6.懒于模块导入

Python 专家建议在程序开始时导入所有模块。你可以按字母顺序排列这些。这种方法将帮助您跟踪程序的依赖关系，但缺点是您的导入会在启动时加载。

你可以尝试不同的方法？您可以在需要时加载模块。这项技术将帮助您平均分配模块的加载时间，这将减少内存使用的峰值。

### 7.如果可能，请使用“in”

建议使用“in”关键字检查列表的成员资格。

```py
for username in member_list:
  print('{} is a member'.format(username))
```

### 结论

所有上述代码将帮助您更快地运行代码，这将允许您从应用程序中获得更好的 Python 性能。随着您使用 Python 的进步，您会发现许多提示，并且您将独自学习使用 Python 优化代码。您将在 Python 中使用列表、字典、元组和许多其他东西，并且在构建您的逻辑或添加一些功能时，慢慢地您将了解如何优化这些东西。