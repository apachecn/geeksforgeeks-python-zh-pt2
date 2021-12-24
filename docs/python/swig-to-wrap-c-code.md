# 刷卡包装 C 码

> 原文:[https://www.geeksforgeeks.org/swig-to-wrap-c-code/](https://www.geeksforgeeks.org/swig-to-wrap-c-code/)

先决条件:[使用 Python 中的 C 代码](https://www.geeksforgeeks.org/using-c-codes-in-python-set-1/)、[使用 SWIG](https://www.geeksforgeeks.org/wrapping-cc-python-using-swig-set-1/) 包装 Python 的 C/C++代码

假设我们给出了一个 C 代码，它需要作为 C 扩展模块来访问。因此，对于给定的任务–*使用 Swig Wrapper* 生成器。

Swig 通过解析 C 头文件和自动创建扩展代码来操作。首先需要 c 头文件，才能使用 Swig。在下面的代码中给出一个 C 头文件的例子。

**代码#1 : `work.h`**

```
// work.h

# include <math.h>

extern int gcd(int, int);
extern int divide(int a, int b, int * remainder);
extern double avg(double * a, int n);

typedef struct Point
{
    double x, y;
} Point;

extern double distance(Point * p1, Point * p2);
```

有了头文件之后，下一步就是写一个 Swig“接口”文件。按照惯例，这些文件有一个 ***。i* 后缀**可能看起来和下面类似。

**代码#2 : `work.i`**

```
// work.i - Swig interface % module work %
{
# include "work.h"
    %
}
// Customizations % extend Point
{
    // Constructor for Point objects 
    Point(double x, double y)
    {
        Point * p = (Point *) malloc(sizeof(Point));
        p->x = x;
        p->y = y;
        return p;
    };
};
```

**代码#3:映射**

```
// Map int * remainder as an output argument
%include typemaps.i 
%apply int * OUTPUT { int * remainder };

// Map the argument pattern (double * a, int n) to arrays 
%typemap(in) (double * a, int n)(Py_buffer view)
{
    view.obj = NULL;
    if (PyObject_GetBuffer($input, &view, 
                           PyBUF_ANY_CONTIGUOUS | PyBUF_FORMAT) == -1)
    {
        SWIG_fail;
    }
    if (strcmp(view.format, "d") != 0)
    {
        PyErr_SetString(PyExc_TypeError, 
                        "Expected an array of doubles");
        SWIG_fail;
    }
    $1 = (double *) view.buf;
    $2 = view.len / sizeof(double);
}

% typemap(freearg) (double * a, int n)
{
    if (view$argnum.obj)
    {
        PyBuffer_Release(&view$argnum);
    }
}
```

一旦接口文件准备好，Swig 作为命令行工具被调用

**代码#4 :**

```
bash % swig -python -py3 work.i
bash %
```

swig 的输出是两个文件–**`work_wrap.c`**和 **`work.py`** 。 *work.py* 文件是用户导入的内容， *work_wrap.c* 文件是需要编译成支持模块 **`_work`** 的 C 代码。使用与普通扩展模块相同的技术来执行。例如，创建如下代码所示的`setup.py`文件–

**代码#5 :**

```
# setup.py
from distutils.core import setup, Extension
setup(name='sample', 
      py_modules=['sample.py'],
      ext_modules=[ Extension(
              '_sample', ['sample_wrap.c'], 
              include_dirs = [], 
              define_macros = [],
              undef_macros = [],
              library_dirs = [],
              libraries = ['sample']
              ) ] )
```

**代码#6:编译并测试，在 *setup.py*** 上运行 python3

```
bash % python3 setup.py build_ext --inplace
running build_ext
building '_sample' extension

gcc -fno-strict-aliasing -DNDEBUG -g -fwrapv -O3 -Wall -Wstrict-prototypes
-I/usr/local/include/python3.3m -c work_wrap.c
-o build/temp.macosx-10.6-x86_64-3.3/work_wrap.o

work_wrap.c: In function ‘SWIG_InitializeModule’:

work_wrap.c:3589: warning: statement with no effect

gcc -bundle -undefined dynamic_lookup build/temp.macosx-10.6-x86_64-3.3/work.o

build/temp.macosx-10.6-x86_64-3.3/work_wrap.o -o _work.so -lwork
bash %
```

执行完所有任务后，我们可以非常轻松地使用 C 扩展模块。

**代码#7 :**

```
import work
print ("GCD : ", work.gcd(12,8))

print ("\nDivision : ", work.divide(42,8))

pt1 = work.Point(2,3)
pt2 = work.Point(4,5)

print ("\nDistance between pt1 and pt2 : ", 
       work.distance(pt1,pt2))

print ("\nx co-ordinate of pt1 : ", pt1.x)
print ("\ny co-ordinate of pt1 : ", pt1.x)

import array
ar = array.array('d',[2, 4, 6])
print ("\nAverage : ", work.avg(arr))
```

**输出:**

```
GCD : 4

Divide : [5, 2]

Distance between pt1 and pt2 : 2.8284271247461903

Distance between pt1 and pt2 : 2.0

Distance between pt1 and pt2 : 3.0

Average : 4.0

```