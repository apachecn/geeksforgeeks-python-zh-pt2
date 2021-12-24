# 是什么让蟒蛇变酷？

> 原文:[https://www.geeksforgeeks.org/what-makes-python-cool/](https://www.geeksforgeeks.org/what-makes-python-cool/)

正如主题所说，我们将研究 Python 提供的一些很酷的特性。

Python 有很多功能(或者说技巧)，这使得这种语言不同于其他语言，例如

**1。Python 的禅**

```
import this
```

如果您在终端上键入这个命令，您将获得“Python 的禅，由蒂姆·彼得斯编写”，这将帮助您提高 Python 代码的可读性、可用性和可维护性。

查看此视频了解更多详情

**3。一行中两个变量的交换**

Python 提供了一个很酷的功能，使用所谓的元组解包在一行中交换两个变量，这将使您的代码更短、更容易阅读

```
a = 10

b = 20

print(f"Before swapping value of a = {a} and b = {b}")

a, b = b, a

print(f"After swapping value of a = {a} and b = {b}")
```

如果你想更深入地了解这个元组解包，我建议你看看特雷·亨纳的博客

[元组解包](http://treyhunner.com/2018/03/tuple-unpacking-improves-python-code-readability/)

**4。使用一行**创建一个网络服务器

```
python -m http.server 8000
```

要创建一个简单的文件共享应用程序，请转到您想要共享的文件夹，键入上面的命令，然后转到您的浏览器并键入

```
127.0.0.1:8000
```

要在浏览器中打开该文件夹，如果您在同一个网络中，也可以从其他设备使用它。

这里有一个链接来了解更多信息

**5。所有数据结构在一个地方:集合**

```
from collections import Counter

myList = [1, 1, 2, 3, 4, 5, 3, 2, 3, 4, 2, 1, 2, 3]

print(Counter(myList))
```

这个模块有数据结构，可以帮助你在不写太多代码的情况下解决各种实际问题。
[收藏品](https://docs.python.org/3/library/collections.html)

**6。蟒蛇宝石:Itertools**

Itertools 是 Python 3 中最重要的标准库之一，它内置了许多特性。Itertools 提供了创建快速、内存高效且美观的代码的功能。

你会在 Itertools 模块中发现很多有用的函数，让我们来看看一个流行的函数

```
import itertools

itertools.permutations('ab')
```

要了解更多关于 Itertools 的信息，请查看此链接

[刀具](https://realpython.com/python-itertools/)

**7。带索引循环:枚举**

这是一个很酷的特性，它提供了索引，而不必为索引定义任何计数器

```
mylist = [1, 13, 16, 15, 80]

for i, value in enumerate(mylist):
      print( i, ': ', value)
```

**8。反转列表**

在任何编程语言中，反转总是一项乏味的任务，但是 Python 内置的 reversed()函数允许您在一行中创建列表的反转

```
lst = [1, 2, 3, 4, 5]

list(reversed(lst))
```

有关更多详细信息，请查看此链接

[反转列表](https://dbader.org/blog/python-reverse-list)

**9。使用 Zip 添加两个列表**

假设您有两个列表，并且您想要添加该列表的元素，那么 python 有一个 Zip 函数，它会派上用场，并在不使用嵌套循环的情况下为您提供结果

```
a = [1, 2, 3]

b = [4, 5, 6]

for i, j in zip(a, b):
    print("Sum of a and b is", i + j)
```

Zip 运算在数据科学中很受欢迎，因为在矩阵乘法中，Zip 可以用来进行行和列乘法。

**10。列表/集合/字典理解**

理解提供了在一行中定义任何复杂代码的最简单方法

***假设你想将 1–20 的偶数平方***

如果您使用正常的 if-else，那么代码将如下所示

```
square_list = []

for number in range(1, 20):
    if number % 2 == 0:
        square_list.append(number * number)

print(square_list)
```

如果使用列表理解，你只需要输入更少的代码

```
square_list = [number * number for number in range(1, 20) if number % 2 == 0]

print(square_list)
```

同样，字典理解和集合理解也可以使用

```
my_dict = {i: i * i for i in range(10)}

my_set =  {i * 10 for i in range(10)}

print(my_dict)

print(my_set)
```

**11 时。现代词典**

Python 字典是如此强大，如果你深入 python，那么一切都围绕着对象和字典。

如果你想了解更多关于字典的知识，那么看看这个视频，你会学到字典的很多重要特性

**12 时。漂亮的印花**

这是最简单的方法来打印一个美丽的清单和字典

```
import pprint

pp = pprint.PrettyPrinter(indent = 4)

pp.pprint(my_dict)
```

这在使用大型字典时非常方便，或者如果您正在使用 JSON 文件，那么您可以使用 pprint 来打印 JSON 文件。

**13。使用交互式“_”运算符。**

```
2 + 2

print(_)
```

“_”引用最后执行的表达式的输出。

> **在这个 Python 之上还提供了很多外部库，它比任何编程语言都有更好的特性，下面我就列举几个顶级库**

Numpy
熊猫
Scikit-学习
刺儿头
美人汤
OpenCV
请求
Matplotlib
Pygame
SQLAlchemy
SciPy
巨蟒扭曲

看完所有酷炫的功能，你的感觉就像

![](img/8c437934328756f2627baf358ae4bfc8.png)

以上就是我这边关于 Python 的全部内容，如果你有任何疑问或者想补充什么，请在下面评论。

如果你喜欢我的文章，你可以继续关注我

quora:[https://www.quora.com/profile/Shankar-Jha-20](https://www.quora.com/profile/Shankar-Jha-20)T2【中:[https://medium.com/@shankarj67](https://medium.com/@shankarj67)T5】推特:[https://twitter.com/Skhk634](https://twitter.com/Skhk634)