# 带装饰器的定时功能–Python

> 原文:[https://www . geesforgeks . org/timing-functions-with-decorator-python/](https://www.geeksforgeeks.org/timing-functions-with-decorators-python/)

Python 中的一切都是一个对象。Python 中的函数也是对象。因此，像任何其他对象一样，它们可以被变量引用，存储在字典或列表等数据结构中，作为参数传递给另一个函数，并作为另一个函数的值返回。在本文中，我们将看到装饰器的定时功能。

**装饰器:**装饰器用于增压或修改功能。装饰器是包装另一个函数并增强或改变它的高阶函数。

**示例:**

解释它是什么的最好方法是编写我们自己的装饰器。假设，你想在某个函数的输出前后打印* 10 次。在每个函数中反复使用 print 语句会非常不方便。在装饰师的帮助下，我们可以有效地做到这一点。

**代码:**

## 蟒蛇 3

```py
def my_decorator(func):
    def wrapper_function(*args, **kwargs):
        print("*"*10)
        func(*args,  **kwargs)
        print("*"*10)
    return wrapper_function

def say_hello():
    print("Hello Geeks!")

@my_decorator
def say_bye():
    print("Bye Geeks!")

say_hello = my_decorator(say_hello)
say_hello()
say_bye()
```

**输出:**

```py
**********
Hello Geeks!
**********
**********
Bye Geeks!
**********
```

**说明:**

在上例中，my_decorator 是一个 decorator 函数，它接受 func，一个函数对象作为参数。它定义了一个包装函数，调用 func 并执行它包含的代码。my_decorator 函数返回这个包装函数。

那么，当我们在定义任何函数之前写@my_decorator 会发生什么呢？考虑上面 say_hello 函数的例子，它在定义时没有被任何装饰者修饰。我们仍然可以通过调用 my_decorator 函数并将 say_hello 函数对象作为参数传递来使用我们的 decorator 来装饰它的输出，这将返回一个带有两个 print 语句的 wrapper_function，中间调用 say_hello()函数。如果我们在 say_hello 对象本身中接收到这个修改后的函数，那么每当我们调用 say_hello()时，我们都会得到修改后的输出。

我们可以在定义函数之前简单地编写@my_decorator，而不是编写这种复杂的语法，剩下的工作留给 python 解释器，如 say_bye 函数所示。

## **使用装饰器的定时器功能**

定时器功能是装饰者的应用之一。在下面的例子中，我们制作了一个接受函数对象 func 的 timer_func 函数。在 timer 函数中，我们定义了 wrap_func，它可以接受任意数量的参数(*args)和任意数量的传递给它的关键字参数(**kwargs)。我们这样做是为了使我们的 timer_func 更加灵活。

在 wrap_func 的主体中，我们使用 time 模块的 time 方法记录了当前时间 t1，然后我们调用了 func 函数，传递了 wrap_func 接收到的相同参数(*args，**kwargs)，并将返回值存储在结果中。现在，我们再次记录了当前时间 t2，并打印了记录时间之间的差值，即{ T2–t1 }，精度可达小数点后第 4 位。这{ T2–t1 }是函数执行期间经过的时间。最后，我们在 wrap_func 函数中返回了结果值，并在 timer_func 函数中返回了这个 wrap_func 函数。

我们还使用@timer_func decorator 定义了 long_time 函数，因此每当我们调用 long_time 函数时，它都会被调用如下:

```py
timer_func(long_time)(5)
```

调用 timer_func 函数时，将 long_time 作为参数传递会返回 wrap_func 函数，并且函数对象 func 开始指向 long_time 函数。

```py
wrap_func(5)
```

现在 wrap_func 将如上所述执行，并返回结果。

## 蟒蛇 3

```py
from time import time

def timer_func(func):
    # This function shows the execution time of 
    # the function object passed
    def wrap_func(*args, **kwargs):
        t1 = time()
        result = func(*args, **kwargs)
        t2 = time()
        print(f'Function {func.__name__!r} executed in {(t2-t1):.4f}s')
        return result
    return wrap_func

@timer_func
def long_time(n):
    for i in range(n):
        for j in range(100000):
            i*j

long_time(5)
```

**输出:**

```py
Function 'long_time' executed in 0.0219s
```