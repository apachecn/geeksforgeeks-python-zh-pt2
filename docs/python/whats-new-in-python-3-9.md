# Python 3.9 有什么新功能？

> 原文:[https://www.geeksforgeeks.org/whats-new-in-python-3-9/](https://www.geeksforgeeks.org/whats-new-in-python-3-9/)

Python 的新版本来了！很快，我们将在 Python 项目中使用它。截至 2020 年 7 月 20 日，Python 3.9 处于测试版(3.9.0b4)，并将很快发布 Python 3.9 的完整版本。

介绍够了。让我们开始了解新功能。

**1。字典合并和更新操作符** : Python 3.9 在**字典**类中引入了**合并(|)** 和**更新(|=)** 操作符。如果你有两个字典 a 和 b，你现在可以使用这些操作符来合并和更新它们。

```py
a = {1: "Sam", 2: "Alex"}
b = {3: "Daniel", 4: "Tom", 5: "Jimmy"}
```

您可以使用 **|** 来合并这两本词典。

```py
c = a|b
print(c)
```

**输出:**

```py
{1: "Sam", 2: "Alex", 3: "Daniel", 4: "Tom", 5: "Jimmy"}
```

如果两个字典都有一个公共键，那么输出将显示第二个键值对。

```py
a = {1: "Sam", 2: "Alex", 3: "James"}
b = {3: "Daniel", 4: "Tom", 5: "Jimmy"}

c = a|b
print(c)
```

**输出:**

```py
{1: "Sam", 2: "Alex", 3: "Daniel", 4: "Tom", 5: "Jimmy"}
```

要更新字典，可以使用以下运算符:

```py
a = {1: "Sam", 2: "Alex"}
b = {2: "Daniel"}
a |= b
print(a)
```

**输出:**

```py
{1: "Sam", 2: "Daniel"}
```

**2。 `removeprefix()`和`removesuffix()` 字符串方法:**在 Python 的 str 类中，新的更新引入了新的 **`removeprefix()`** 和 **`removesuffix()`** 方法。

您可以使用`removeprefix()`方法删除任何字符串的前缀:

```py
print('HelloWorld'.removeprefix('Hello'))
```

**输出:**

```py
'World'
```

如果字符串不以输入前缀开头，将返回原始字符串的副本。

```py
print('BaseTestCase'.removeprefix('Test'))
```

**输出:**

```py
'BaseTestCase'
```

如果字符串以输入后缀结尾，输出将看起来像字符串`[:-len(suffix)]`。

```py
print('MiscTests'.removesuffix('Tests'))
```

**输出:**

```py
'Misc'
```

如果输入后缀为空或者字符串不以它结尾，输出将是原始字符串的副本。

```py
print('BadTestCase'.removesuffix('Tmp'))
```

**输出:**

```py
'BadTestCase'
```

**3。新解析器:** Python 3.9 使用了一个新的解析器，它是一个基于 PEG 的解析器。之前，Python 使用了 **LL(1)** 。在构建语言的新特性时，PEG 比 LL(1)更灵活。官方文档表示，这种灵活性将在 Python 3.10 和更高版本中看到。

**4。类型提示:** Python 动态指定变量的数据类型。对于数据类型的静态分配，使用类型提示。这是在 Python 3.5 中引入的。您现在可以使用内置的集合类型(**列表**和**字典**)作为泛型类型。之前需要从打字中导入大写类型( **List** 或 **Dict** )。

```py
def greet_all(names: list[str]) -> None:
    for name in names:
        print("Hello", name)
```

现在不需要从`typing.List`调用 List。