# 用于竞争编码的 Python 技巧

> 原文:[https://www . geesforgeks . org/python-tricks-competitive-coding/](https://www.geeksforgeeks.org/python-tricks-competitive-coding/)

Python 就是这样一种编程语言，它让一切都变得简单直接。任何涉猎过 python for Competitive Coding 的人都会对它的许多特性有些上瘾。下面是它的一些很酷的特性的列表，我发现这些特性在竞争激烈的编码环境中非常有用。

1.  **计数器包最常见的 _ 功能。**
    这可能是我用过的最有用的函数，在编写任何 python 代码时，它总是在我的脑海中。这个函数分析一个列表/字符串，并帮助返回列表/字符串中顶部的 **n** 实体，根据它们出现的次数以降序排列，其中 **n** 是程序员指定的数字。各个实体连同它们在**元组**中的出现次数一起被返回，该元组可以在需要时容易地被引用/打印。

## 计算机编程语言

```
# Code to find top 3 elements and their counts
# using most_common
from collections import Counter

arr = [1, 3, 4, 1, 2, 1, 1, 3, 4, 3, 5, 1, 2, 5, 3, 4, 5]
counter = Counter(arr)
top_three = counter.most_common(3)
print(top_three)
```

1.  输出:

```
[(1, 5), (3, 4), (4, 3)]
```

1.  输出元组清楚地表明 1 发生了 5 次，3 发生了 4 次，4 发生了 3 次。
2.  **堆包的 n 最大/n 最小函数。**
    这个函数帮助返回任何列表中最上面的 **n** 最小/最大的元素，这里 **n** 是程序员指定的一个数字。

## 计算机编程语言

```
# Python code to find 3 largest and 4 smallest
# elements of a list.
import heapq

grades = [110, 25, 38, 49, 20, 95, 33, 87, 80, 90]
print(heapq.nlargest(3, grades))
print(heapq.nsmallest(4, grades))
```

1.  输出:

```
[110, 95, 90]
[20, 25, 33, 38]
```

1.  输出的第一行给出了列表等级中最大的 3 个数字。同样，输出的第二行打印出列表等级中的 4 个最小元素。该功能的另一个**特点**是不忽略重复。所以代替 **n** 如果我们放置数组的长度，我们会得到整个排序数组本身！！
2.  [**字典**](https://www.geeksforgeeks.org/python-set-4-dictionary-keywords-python/) **和概念** [**zipping**](https://www.geeksforgeeks.org/using-iterations-in-python-effectively/) **字典**
    python 中的字典就其提供的独特功能而言确实令人着迷。它们以类似数组的结构形式作为**键和值对**存储。每个值都可以通过其对应的键来访问。
    zip 函数用于将两个列表连接在一起，或者我们甚至可以将字典中的键和值对作为单个列表连接在一起。这个概念的应用将在下面的代码片段中阐明。

## 计算机编程语言

```
# Python code to demonstrate use of zip.
import heapq

stocks = {
    'Goog' : 520.54,
    'FB' : 76.45,
    'yhoo' : 39.28,
    'AMZN' : 306.21,
    'APPL' : 99.76
    }

zipped_1 = zip(stocks.values(), stocks.keys())

# sorting according to values
print(sorted(zipped_1))

zipped_2 = zip(stocks.keys(), stocks.values())
print(sorted(zipped_2))
#sorting according to keys
```

1.  输出:

```
[(39.28, 'yhoo'), (76.45, 'FB'), (99.76, 'APPL'), (306.21, 'AMZN'), (520.54, 'Goog')]
[('AMZN', 306.21), ('APPL', 99.76), ('FB', 76.45), ('Goog', 520.54), ('yhoo', 39.28)]
```

1.  **地图功能。**
    这个函数是一个偷偷摸摸的小快捷方式，允许我们以非常**非常规的方式**在值列表上实现一个简单的函数。下面的例子将给出这个功能的一个简单应用。该函数将函数名和需要应用该函数的列表名作为参数。

## 计算机编程语言

```
# Python code to apply a function on a list
income = [10, 30, 75]

def double_money(dollars):
    return dollars * 2

new_income = list(map(double_money, income))
print(new_income)
```

1.  输出:

```
[20, 60, 150]
```

1.  这里，我们只是实现了一个简单的函数，它将每个列表值乘以 2，并将其作为新列表返回。
2.  **字符串列表的串联**
    假设我们已经得到了一个字符串列表，我们必须通过串联列表给出输出
    让我们看看前面的代码我们在做什么:

## 计算机编程语言

```
string = ""
lst = ["Geeks", "for", "Geeks"]
for i in lst:
    string += i
print(string)
```

1.  这种连接字符串列表的方法肯定不是最好的方法，因为每次都会创建一个新的字符串

## 计算机编程语言

```
lst = ["Geeks", "for", "Geeks"]
string = ''.join(lst)
print(string)
```

1.  使用 **join()** 函数不仅内存效率高，而且编写起来也很方便，这无疑证明了它优于之前的代码。

**单个来说，这些函数可能看起来很简单，但在限时编码环境中肯定会派上用场，因为它们在很短的代码量内提供了大量的功能。所讨论的功能有非常具体的应用，在竞争性编码中就像一个快捷键或备忘单。把这些有用的技巧藏在你的袖子里可能会给某人带来他们正在寻找的竞争优势！！**
本文由**悉达多·巴贾杰**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。