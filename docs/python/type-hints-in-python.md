# Python 中的类型提示

> 原文:[https://www.geeksforgeeks.org/type-hints-in-python/](https://www.geeksforgeeks.org/type-hints-in-python/)

Python 是一种动态类型的语言，这意味着您永远不必明确指出变量有哪种类型。但是在某些情况下，动态类型会导致一些非常难以调试的错误，在这些情况下，类型提示或静态类型可能会很方便。类型提示是 Python 3.5 中引入的一项新功能。

让我们看看这个阶乘函数来清楚地理解这一点:

```
# factorial function
def factorial(i):
  if i<0:
    return None
  if i == 0:
    return 1
  return i * factorial(i-1)

# passing an integer to the function
print(factorial(4))

# passing a string to the function
print(factorial("4"))

# passing a floating point number to the function
print(factorial(5.01))
```

如果我们试图将一个整数传递给函数，它就能正常工作。现在，如果我们试图将一个字符串传递给阶乘函数，我们会得到一个错误，因为我们不能用字符串进行数学比较。
同样，如果我们试图传递一个浮点数，比如说 5.01，我们也会在这里得到一个错误，因为我们在每次迭代中根据我们的逻辑将这个数减 1，在最后一次迭代中它变成-0.99，返回“无”，这导致了一个错误，因为我们试图将“无”与其他浮点数相乘。

类型提示代码如下所示:
我们必须指定参数的类型&以及阶乘函数的类型。

```
# factorial function
def factorial(i: int) -> int:
  if i<0:
    return None
  if i == 0:
    return 1
  return i * factorial(i-1)

# passing a fraction to the function
print(factorial(5.01))
```

Python 解释器完全忽略了类型提示。所以，如果我们再次运行这段代码，我们仍然会得到相同的错误。

因此，我们必须使用静态类型检查器来分析我们的代码，并尝试检测我们是否违反了类型提示。
最著名的字体检查器是“ **mypy** ”。我们只需使用 **pip** 即可安装。

```
pip install mypy
```

为了现在运行代码，我们必须简单地调用 Python 解释器，并且我们必须指定“-m”来指示我们想要加载一个模块，然后指定我们想要检查的脚本。例如:

`mypy program.py`

现在，如果我们运行它，它不会实际执行我们的“`program.py`”脚本，但它会分析它，并给我们一个错误，就像“参数 1 到*阶乘*有不兼容的类型*浮动*；预期的 *int* 这是一个非常明确的消息，这使得我们比以前更容易调试我们的代码，没有 *mypy* 类型检查器，错误消息没有那么具体。如果我们用一个整数再次运行代码，它也能正常工作。