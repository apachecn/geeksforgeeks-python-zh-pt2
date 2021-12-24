# 尝试-除了在 Python 中 vs If

> 原文:[https://www.geeksforgeeks.org/try-except-vs-if-in-python/](https://www.geeksforgeeks.org/try-except-vs-if-in-python/)

Python 是一种广泛使用的通用高级编程语言。它主要是为了强调代码的可读性而开发的，它的语法允许程序员用更少的代码行来表达概念。Python 是一种编程语言，可以让您快速工作并更高效地集成系统。
大多数人不知道 Try-Except 块可以代替 if-else(条件语句)。是的，你读对了！这是可以做到的。我们可以使用 Try(异常处理)来代替普通的条件语句。

这里有一个非常著名的例子:
**使用 If:**

```py
if key in mydict:
    mydict[key] += 1
else:
    mydict[key] = 1
```

**使用尝试/除外:**

```py
try:
    mydict[key] += 1
except KeyError:
    mydict[key] = 1
```

看起来很棒，对吧！但是问题来了，哪个代码块工作得更快？
可以使用 python 中的 timeit 模块进行测量。可见是否应该用 Try 块代替 If。
**示例:**使用 try-except 和 if-else 进行 2 个数字除法的时间比较。
以下是执行情况。

## 蟒蛇 3

```py
import timeit

code_snippets =["""\
try:
    result = 1000 / value
except ZeroDivisionError:
    pass""",
"""\
if value:
    result = 1000 / value""",
]

for value in (1, 0):
    for code in code_snippets:
        t = timeit.Timer(stmt = code, setup ='value ={}'.format(value))
        print("----------------------")
        print("value = {}\n{}".format(value, code))
        print("%.2f usec / pass\n" % (1000000 * t.timeit(number = 100000)/100000))
```

**输出:**

```py
----------------------
value = 1
try:
    result = 1000 / value
except ZeroDivisionError:
    pass
0.04 usec / pass

----------------------
value = 1
if value:
    result = 1000 / value
0.06 usec / pass

----------------------
value = 0
try:
    result = 1000 / value
except ZeroDivisionError:
    pass
0.37 usec / pass

----------------------
value = 0
if value:
    result = 1000 / value
0.01 usec / pass
```

现在可以清楚地看到，异常处理程序(try/except)比显式 if 条件相对更快，直到遇到异常。这意味着如果任何异常抛出，异常处理程序花费的时间比代码版本多。这意味着决定代码牢固性的因素是正在处理的问题的类型。
我们经常听到 python 总是鼓励[**【EAFP】**](https://docs.python.org/3.5/glossary.html#term-eafp)(【请求原谅比请求允许更容易】)的风格，而不是像 C. Python 文档这样的大多数语言中使用的 **LBYL** (【三思而后行】)的风格——T7

> 请求原谅比请求允许容易。这种常见的 Python 编码风格假设存在有效的键或属性，如果假设被证明为假，则捕捉异常。这种简洁快速的风格的特点是有许多尝试和例外语句。这种技术与许多其他语言(如 c 语言)常见的 LBYL 风格形成对比

从我们的评价中，我们得出以下结论。让我们考虑一下上面的例子，如果我们预期 99%的情况下“value”的值不等于 0，我们可以使用 try/except 方法。如果例外真的是例外会更快。如果值变为 0 的可能性大于 50 %，那么使用“If”可能更好。