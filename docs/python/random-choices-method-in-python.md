# 随机。Python 中的 Choices()方法

> 原文:[https://www . geesforgeks . org/random-choices-in-method-python/](https://www.geeksforgeeks.org/random-choices-method-in-python/)

**choices()** 方法通过替换从列表中返回多个随机元素。您可以使用`weights`参数或`cum_weights`参数来衡量每个结果的可能性。元素可以是字符串、范围、列表、元组或任何其他类型的序列。

> **语法:**随机选择(序列，权重=无，cum _ weights =无，k=1)
> 
> **参数:**
> 1。**序列**是一个强制参数，可以是列表、元组或字符串。
> 2。**权重**是一个可选参数，用于衡量每个值的可能性。
> 3。 **cum_weights** 是一个可选参数，用于衡量每个值的可能性，但在此情况下，可能性是累积的
> 4。 **k** 是一个可选参数，用于定义返回列表的长度。

**注:**此方法不同于 random.choice()。

**示例:**

```py
import random

mylist = ["geeks", "for", "python"]

print(random.choices(mylist, weights = [10, 1, 1], k = 5))
```

**注意:**每次输出会因系统返回随机元素而不同。
T3】输出:

```py
['geeks', 'geeks', 'geeks', 'for', 'for']

```

**实际应用:**打印 6 项随机列表。

```py
import random

mylist = ["apple", "banana", "mango"]

print(random.choices(mylist, weights = [10, 1, 1], k = 6))
```

**注意:**每次使用 choices()函数时，输出都会改变。
T3】输出:

```py
['apple', 'banana', 'apple', 'apple', 'apple', 'banana']

```