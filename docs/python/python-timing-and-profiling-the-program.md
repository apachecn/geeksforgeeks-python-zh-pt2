# Python |程序计时和分析

> 原文:[https://www . geeksforgeeks . org/python-计时和分析程序/](https://www.geeksforgeeks.org/python-timing-and-profiling-the-program/)

**问题–**找出程序花费时间的地方，并进行计时测量。

为了简单地给整个程序计时，通常使用如下所示的 Unix time 命令就足够简单了。

**代码#1:命令对整个程序计时**

```
bash % time python3 someprogram.py
real 0m13.937s
user 0m12.162s
sys 0m0.098s
bash %
```

在另一个极端，为了有一个显示程序正在做什么的详细报告，使用了 **cProfile** 模块。

```
bash % python3 -m cProfile someprogram.py
```

**输出:**

```
Ordered by: standard name
    ncalls tottime percall cumtime percall filename:lineno(function)
    263169 0.080 0.000 0.080 0.000 someprogram.py:16(frange)
    513 0.001 0.000 0.002 0.000 someprogram.py:30(generate_mandel)
    262656 0.194 0.000 15.295 0.000 someprogram.py:32()
    1 0.036 0.036 16.077 16.077 someprogram.py:4()
    262144 15.021 0.000 15.021 0.000 someprogram.py:4(in_mandelbrot)
    1 0.000 0.000 0.000 0.000 os.py:746(urandom)
    1 0.000 0.000 0.000 0.000 png.py:1056(_readable)
    1 0.000 0.000 0.000 0.000 png.py:1073(Reader)
    1 0.227 0.227 0.438 0.438 png.py:163()
    512 0.010 0.000 0.010 0.000 png.py:200(group)

```

通常情况下，分析代码介于这两个极端之间。例如，如果已经知道代码大部分时间花在几个选定的函数上。对于选定的函数分析，一个简短的装饰器可能是有用的。

**代码#3:使用短修饰器对功能进行选择分析**

```
# abc.py

import time
from functools import wraps

def timethis(func):
    @wraps(func)
    def wrapper(*args, **kwargs):
        start = time.perf_counter()
        r = func(*args, **kwargs)
        end = time.perf_counter()
        print('{}.{} : {}'.format(func.__module__, func.__name__, end - start))
        return r
    return wrapper
```

要使用装饰器，只需将它放在函数定义的前面，就可以从中获取计时，如下面的代码所示。
**代码#4 :**

```
@abc
def countdown(n):
    while n > 0:
    n -= 1

countdown(10000000)
```

**输出:**

```
__main__.countdown : 0.803001880645752
```

**代码#5:定义一个上下文管理器来为一个语句块计时。**

```
from contextlib import contextmanager

def timeblock(label):
    start = time.perf_counter()
    try:
        yield
    finally:
        end = time.perf_counter()
        print('{} : {}'.format(label, end - start))
```

**代码#6:上下文管理器如何工作**

```
with timeblock('counting'):
    n = 10000000
    while n > 0:
        n -= 1
```

**输出:**

```
counting : 1.5551159381866455
```

**代码#7:使用 timeit 模块研究小代码片段的性能**

```
from timeit import timeit
print (timeit('math.sqrt(2)', 'import math'), "\n")

print (timeit('sqrt(2)', 'from math import sqrt'))
```

**输出:**

```
0.1432319980012835
0.10836604500218527

```

**timeit** 通过执行第一个参数中指定的语句一百万次并测量时间来工作。