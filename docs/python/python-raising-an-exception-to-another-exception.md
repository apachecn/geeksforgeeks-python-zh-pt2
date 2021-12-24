# Python |引发一个异常到另一个异常

> 原文:[https://www . geesforgeks . org/python-引发一个异常到另一个异常/](https://www.geeksforgeeks.org/python-raising-an-exception-to-another-exception/)

让我们考虑这样一种情况，我们想要引发一个异常来响应捕获一个不同的异常，但是想要在回溯中包含关于这两个异常的信息。

若要链接异常，请使用 raise from 语句而不是简单的 raise 语句。这将为您提供关于这两个错误的信息。

**代码#1 :**

```
def example():
    try:
        int('N/A')
    except ValueError as e:
        raise RuntimeError('A parsing error occurred') from e...

example()
```

**输出:**

```
Traceback (most recent call last):
  File "", line 3, in example
ValueError: invalid literal for int() with base 10: 'N/A'

```

该异常是以下异常的直接原因–

```
Traceback (most recent call last):
  File "", line 1, in <module>File "<stdin>", line 5, in example
RuntimeError: A parsing error occurred</stdin></module> 
```

这两个异常都在回溯中捕获。一个普通的 except 语句用来捕捉这样的异常。然而，异常对象的`__cause__`属性可以被视为遵循异常链，如下面给出的代码中所解释的。

**代码#2 :**

```
try:
    example()
except RuntimeError as e:
    print("It didn't work:", e)
    if e.__cause__:
        print('Cause:', e.__cause__)
```

当另一个异常在 except 块中引发时，就会出现隐式形式的链式异常。

**代码#3 :**

```
def example2():
    try:
        int('N/A')
    except ValueError as e:
        print("Couldn't parse:", err)

example2()
```

```
Traceback (most recent call last):
    File "", line 3, in example2
ValueError: invalid literal for int() with base 10: 'N / A' 
```

在处理上述异常的过程中，又出现了一个异常:

```
Traceback (most recent call last):
    File "", line 1, in <module>File "<stdin>", line 5, in example2
NameError: global name 'err' is not defined</stdin></module> 
```

在下面的代码中，NameError 异常是作为编程错误的结果而引发的，而不是对解析错误的直接响应。对于这种情况，不设置异常的`__cause__`属性。相反，`__context__`属性被设置为先前的异常。

**代码#4:要抑制链接，使用从无开始提升**

```
def example3():
    try:
        int('N / A')
    except ValueError:
        raise RuntimeError('A parsing error occurred') from None...

example3()
```

**输出:**

```
Traceback (most recent call last):
    File "", line 1, in 
    File "", line 5, in example3
RuntimeError: A parsing error occurred

```