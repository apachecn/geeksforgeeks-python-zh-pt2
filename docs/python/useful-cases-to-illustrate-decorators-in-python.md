# 用 python 说明装饰者的有用案例

> 原文:[https://www . geeksforgeeks . org/有用案例说明-python 中的装饰者/](https://www.geeksforgeeks.org/useful-cases-to-illustrate-decorators-in-python/)

装饰器是一种特殊的函数，它要么接受一个函数并返回一个函数，要么接受一个类并返回一个类。嗯，它可以是任何可调用的(即函数、类、方法，因为它们可以被调用)，它可以返回任何东西，它也可以采用一个方法。这也被称为**元编程**，因为程序的一部分试图在编译时修改程序的另一部分。
让我们深入了解 python 装饰者，看看他们能做什么。这将不会覆盖参数的基础或装饰，但一些有用的例子来说明这种情况。

> 参考下面的文章来获得 Python 装饰器的基础知识
> 
> *   [蟒蛇装饰师](https://www.geeksforgeeks.org/decorators-in-python/)

基本上，装饰器接受一个可调用的，任何实现特殊方法`__call()__`的对象都被称为可调用的，添加一些功能并返回一个可调用的。

**例 1:**

```
# Python program to demonstrate
# decorators

# Creating a decorator
def decorated_func(func):
    def inner():
        print("This is decorated function")
        func()
    return inner()

def ordinary_func ():
    print("This is ordinary function")

decorated = decorated_func(ordinary_func)
decorated
```

**输出:**

```
This is decorated function
This is ordinary function

```

在上面显示的例子中，`decorated_func()`是一个装饰器。简而言之，装饰器充当包装器，包装对象(不改变原始对象)并向原始对象添加新功能。这是一个常见的构造，因此 Python 有一个语法特性(称为`Decorator`)来简化这一点。例如，

**这个:**

```
@decorated_func
def ordinary_func():
     print("This is ordinary function")

```

**相当于:**

```
def ordinary_func():
    print("This is ordinary function")
decorated = decorated_func(ordinary_func)

```

一个简单的例子是:

**例 2:**
**输入:**

```
def mul_decorator(func):
    def wrapper(*args, **kwargs):
        print('function', func.__name__, 'called with args - ', /
              args, 'and kwargs - ', kwargs)
        result = func(*args, **kwargs)
        print('function', func.__name__, 'returns', result)
        return result
    return wrapper

@mul_decorator
def mul(a, b):
    return a * b
mul(3, 3)
mul(3, b = 6)
```

**输出:**

```
function mul called with args -  (3, 3) and kwargs -  {}
function mul returns 9
function mul called with args -  (3,) and kwargs -  {'b': 6}
function mul returns 18

```

您也可以使用内置的装饰器

**例 3:**

```
# func will be func = type(func) -> <class 'function'>
@type
def func(): 
    return 42

print(func)

# print doesn't return anything, so func == None
@print
def func2(): 
    return 42

# Prints None
print(func2)
```

**输出:**

```
<class 'function'>
<function func2 at 0x7f135f067f28>
None

```

您可以用其他东西替换装饰对象

**例 4:**

```
# Creating a decorator
class function_1:
    def __init__(self, func):
        self.func = func
        self.stats = []

    def __call__(self, *args, **kwargs):
        try:
            result = self.func(*args, **kwargs)
        except Exception as e:
            self.stats.append((args, kwargs, e))
            raise e
        else:
            self.stats.append((args, kwargs, result))
            return result

    @classmethod
    def function_2(cls, func):
        return cls(func)

@function_1.function_2
def func(x, y):
    return x / y

print(func(6, 2))

print(func(x = 6, y = 4))

func(5, 0)
print(func.stats)
print(func)
```

**输出:**

```
3.0
1.5

```

```
Traceback (most recent call last):
  File "/home/1ba974e44c61e303979b3ee120b6b066.py", line 29, in 
    func(5, 0)
  File "/home/1ba974e44c61e303979b3ee120b6b066.py", line 11, in __call__
    raise e
  File "/home/1ba974e44c61e303979b3ee120b6b066.py", line 8, in __call__
    result = self.func(*args, **kwargs)
  File "/home/1ba974e44c61e303979b3ee120b6b066.py", line 23, in func
    return x / y
ZeroDivisionError: division by zero

```

注意原来的`"func"`是如何被`"function_1"`的一个实例代替的，这个实例可以和原来的函数一样使用。
可以创建与系统中其他对象的关系

**例 5:**

```
def dict_from_func(func):
    return {func.__name__: func}

activity = {}

@activity.update
@dict_from_func
def mul(a, b):
    return a * b

@activity.update
@dict_from_func
def add(a, b):
    return a + b

print(mul)
print(activity)
print(activity['mul'](2, 5))
```

**输出:**

```
None
{'mul': <function mul at 0x7f0d2209fe18>, 
 'add': <function add at 0x7f0d220a2158>}
10

```

这里，在示例 5 中，我们使用了`dict.update`方法作为装饰器，即使它不是为此而设计的。这是可能的，因为`dict_from_func`返回一个判词，`dict.update`将一个判词作为参数。

**其实这个:**

```
@activity.update
@dict_from_func
def mul(a, b):
    return a * b

```

**等于这个–**

```
def mul(a, b):
    return a * b
mul = activity.update(dict_from_func(mul))

```

## 结论

装饰者是一个有趣和令人惊讶的功能，可以用于各种目的。不仅仅是**“函数或类取函数或类返回函数或类”**。