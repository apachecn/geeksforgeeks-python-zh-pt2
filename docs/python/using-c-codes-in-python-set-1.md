# 使用 Python 中的 C 代码|集合 1

> 原文:[https://www . geesforgeks . org/using-c-codes-in-python-set-1/](https://www.geeksforgeeks.org/using-c-codes-in-python-set-1/)

先决条件:[如何在 Python 中调用 C 函数](https://www.geeksforgeeks.org/how-to-call-a-c-function-in-python/)

让我们讨论一下从 Python 访问 C 代码的问题。很明显，Python 的许多内置库都是用 C 编写的。因此，访问 C 是让 Python 与现有库对话的一个非常重要的部分。Python 提供了一个广泛的 C 编程接口，但是有许多不同的方法来处理 C。

**代码# 1:**[`work.c`]C-我们正在处理的代码。

```py
#include <math.h>

int gcd(int x, int y)
{
    int g = y;
    while (x > 0)
    {
        g = x;
        x = y % x;
        y = g;
    }
    return g;
}

int divide(int a, int b, int * remainder)
{
    int quot = a / b;
    *remainder = a % b;
    return quot;
}

double avg(double * a, int n)
{
    int i;
    double total = 0.0;
    for (i = 0; i < n; i++)
    {
        total += a[i];
    }
    return total / n;
}

typedef struct Point
{
    double x, y;
} Point;

double distance(Point * p1, Point * p2)
{
    return hypot(p1->x - p2->x, p1->y - p2->y);
}
```

上面的代码有不同的 C 编程特性。

> gcd()
> divide()–返回多个值，一个通过指针参数
> avg()–跨 C 数组执行数据约简
> 点和距离()–涉及 C 结构。

让我们假设上面的代码是在一个名为 **work.c** 的文件中找到的，并且已经被编译到一个库 *libsample* 中，该库可以链接到其他 C 代码。现在，我们有许多已经编译到共享库中的 C 函数。因此，我们完全从 Python 调用函数，而不必编写额外的 C 代码或使用第三方扩展工具。

**使用 ctypes:**
Python**ctypes**会来玩，但要确保要转换的 C 代码已经编译到与 Python 解释器兼容的共享库中(如相同的架构、字长、编译器等)。).

此外 **libsample.so** 文件已经被放在与`work.py`相同的目录中。现在来了解一下`work.py`。

**代码#2 : Python 模块，环绕结果库进行访问**

```py
# work.py
import ctypes
import os

# locating the 'libsample.so' file in the
# same directory as this file
_file = 'libsample.so'
_path = os.path.join(*(os.path.split(__file__)[:-1] + (_file, )))
_mod = ctypes.cdll.LoadLibrary(_path)
```

**代码#3:访问代码**

```py
# int gcd(int, int)
gcd = _mod.gcd
gcd.argtypes = (ctypes.c_int, ctypes.c_int)
gcd.restype = ctypes.c_int

# int divide(int, int, int *)
_divide = _mod.divide
_divide.argtypes = (ctypes.c_int, ctypes.c_int,
                    ctypes.POINTER(ctypes.c_int))

_divide.restype = ctypes.c_int

def divide(x, y):
    rem = ctypes.c_int()
    quot = _divide(x, y, rem)
    return quot, rem.value

# void avg(double *, int n)
# Define a special type for the 'double *' argument
class DoubleArrayType:
    def from_param(self, param):

        typename = type(param).__name__

        if hasattr(self, 'from_' + typename):
            return getattr(self, 'from_' + typename)(param)

        elif isinstance(param, ctypes.Array):
            return param

        else:
            raise TypeError("Can't convert % s" % typename)

    # Cast from array.array objects
    def from_array(self, param):
        if param.typecode != 'd':
            raise TypeError('must be an array of doubles')

        ptr, _ = param.buffer_info()
        return ctypes.cast(ptr, ctypes.POINTER(ctypes.c_double))

    # Cast from lists / tuples
    def from_list(self, param):
        val = ((ctypes.c_double)*len(param))(*param)
        return val

    from_tuple = from_list

    # Cast from a numpy array
    def from_ndarray(self, param):
        return param.ctypes.data_as(ctypes.POINTER(ctypes.c_double))

DoubleArray = DoubleArrayType()
_avg = _mod.avg
_avg.argtypes = (DoubleArray, ctypes.c_int)
_avg.restype = ctypes.c_double

def avg(values):
    return _avg(values, len(values))

# struct Point { }
class Point(ctypes.Structure):
    _fields_ = [('x', ctypes.c_double), ('y', ctypes.c_double)]

# double distance(Point *, Point *)
distance = _mod.distance
distance.argtypes = (ctypes.POINTER(Point), ctypes.POINTER(Point))
distance.restype = ctypes.c_double
```

现在，人们可以很容易地加载模块并使用生成的 C 函数。参见下一部分–[使用 Python 中的 C 代码|设置 2](https://www.geeksforgeeks.org/using-c-codes-in-python-set-2/) 。