# Python | C 扩展模块中的不透明指针

> 原文:[https://www . geesforgeks . org/python-不透明-指针-in-c-extension-modules/](https://www.geeksforgeeks.org/python-opaque-pointers-in-c-extension-modules/)

让我们讨论一个扩展模块，它需要处理指向 C 数据结构的指针，而不需要向 Python 公开该结构的任何内部细节。[不透明的](https://www.geeksforgeeks.org/opaque-pointer/)数据结构可以通过将它们包装在胶囊对象中来轻松处理，如下面的代码片段所示。

**代码#1 :**

```
typedef struct Point
{
    double x, y;
} Point;

extern double distance(Point *p1, Point *p2);
```

参考上一篇文章，使用 Python 中的 C 代码找到距离()函数–。

**代码#2 :** 给出的代码是一个扩展代码，使用胶囊包装*点*结构和`distance()`功能。

```
/* Destructor function for points */
static void del_Point(PyObject * obj)
{
    free(PyCapsule_GetPointer(obj, "Point"));
}

/* Utility functions */
static Point * PyPoint_AsPoint(PyObject * obj)
{
    return (Point *) PyCapsule_GetPointer(obj, "Point");
}
static PyObject * PyPoint_FromPoint(Point * p, int must_free)
{
    return PyCapsule_New(p, "Point", must_free ? del_Point : NULL);
}

/* Create a new Point object */
static PyObject * py_Point(PyObject * self, PyObject * args)
{
    Point * p;
    double x, y;
    if (! PyArg_ParseTuple(args, "dd", &x, &y))
    {
        return NULL;
    }
    p = (Point *) malloc(sizeof(Point));
    p->x = x;
    p->y = y;
    return PyPoint_FromPoint(p, 1);
}

static PyObject * py_distance(PyObject * self, PyObject * args)
{
    Point * p1, *p2;
    PyObject * py_p1, *py_p2;
    double result;
    if (! PyArg_ParseTuple(args, "OO", &py_p1, &py_p2))
    {
        return NULL;
    }
    if (!(p1 = PyPoint_AsPoint(py_p1)))
    {
        return NULL;
    }
    if (!(p2 = PyPoint_AsPoint(py_p2)))
    {
        return NULL;
    }
    result = distance(p1, p2);
    return Py_BuildValue("d", result);
}
```

**代码#3:使用 Python 中的上述函数**

```
import sample

pt1 = sample.Point(2, 3)
pt2 = sample.Point(4, 5)

print ("pt1 : ", pt1)
print ("\npt2 : ", pt2)

print ("Distance : ", sample.distance(p1, p2))
```

**输出:**

```
pt1 : <capsule object "Point" at 0x1004ea330>

pt2 : <capsule object "Point" at 0x1005d1db0>

Distance : 2.8284271247461903

```

*   胶囊类似于一个 C 型指针。
*   它们有一个通用指针和一个识别名称，可以使用`**PyCapsule_New()**`函数轻松创建。
*   `**PyCapsule_GetPointer()**`功能用于提取胶囊内的指针。
*   垃圾收集和内存管理是一个棘手的问题。
*   `**PyPoint_FromPoint()**`函数接受一个必选 _ 自由参数，该参数指示当胶囊被破坏时是否要收集底层的点*结构。