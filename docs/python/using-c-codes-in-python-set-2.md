# 使用 Python 中的 C 代码|第 2 集

> 原文:[https://www . geesforgeks . org/using-c-codes-in-python-set-2/](https://www.geeksforgeeks.org/using-c-codes-in-python-set-2/)

先决条件:[使用 Python 中的 C 代码|集合 1](https://www.geeksforgeeks.org/using-c-codes-in-python-set-1/)

在[上一篇文章](https://www.geeksforgeeks.org/using-c-codes-in-python-set-1/)中，我们已经讨论了如何在 Python 中访问 C 代码。现在，让我们看看如何访问 C 函数。

**代码#1:用 Python 访问 C 函数**

```py
import work

print ("GCD : ", work.gcd(35, 42))

print ("\ndivide : ", work.divide(42, 8))

print ("\navg : ", work.avg([1, 2, 3]))

p1 = work.Point(1, 2)
p2 = work.Point(4, 5)
print ("\ndistance : ", work.distance(p1, p2))
```

**输出:**

```py
GCD : 7

divide : (5, 2)

avg : 2.0

distance : 4.242640687119285

```

T3】发行？
现在上面做的工作有一个问题，对于 C 和 Python 代码的整体打包，使用 **ctypes** 来访问已经编译好的 C 代码，必须确保共享库放在`work.py`模块可以找到的位置。一种可能是将生成的`libsample.so`文件放在与支持 Python 代码相同的目录中。

因此，如果 C 库安装在其他地方，那么路径必须相应地调整。如果作为标准库安装在机器上，则可以使用`ctypes.util.find_library()`功能。

**代码#2:路径示例**

```py
from ctypes.util import find_library

find_library('m')

find_library('pthread')

find_library('sample')
```

**输出:**

```py
/usr/lib/libm.dylib

/usr/lib/libpthread.dylib

/usr/local/lib/libsample.so

```

同样， **ctypes** 如果用 C 代码找不到库的话，根本不会工作。`ctypes.cdll.LoadLibrary()`用于加载 C 库，一旦知道了它的位置。

```py
_mod = ctypes.cdll.LoadLibrary(_path)
```