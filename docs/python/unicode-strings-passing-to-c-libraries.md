# 传递给 C 库的 Unicode 字符串

> 原文:[https://www . geesforgeks . org/unicode-strings-passing-to-c-libraries/](https://www.geeksforgeeks.org/unicode-strings-passing-to-c-libraries/)

假设您想编写一个扩展模块，需要将 Python 字符串传递给 C 库函数。因此，出现了正确处理 Unicode 的问题。因此，出现的一个主要问题是现有的 C 库无法理解 Python 对 Unicode 的本机表示。因此，主要的挑战是将 Python 字符串转换成 C 库更容易理解的形式。

为了说明解决方案，下面给出了两个对字符串数据进行操作的 C 函数，并将其输出用于调试和实验。

**代码#1:使用表格`char *, int`** 中提供的字节

```py
void print_chars(char *s, int len)
{
    int n = 0;
    while (n < len)
    {
        printf("%2x ", (unsigned char) s[n]);
        n++;
    }
    printf("\n");
}
```

**代码#2:使用宽字符形式`wchar_t *, int`**

```py
void print_wchars(wchar_t *s, int len)
{
    int n = 0;
    while (n < len)
    {
        printf("%x ", s[n]);
        n++;
    }
    printf("\n");
}
```

对于面向字节的函数`print_chars()`，Python 字符串需要转换为合适的字节编码，例如 UTF-8。下面的代码给出了一个简单的扩展函数来解决这个问题。

**代码#3 :**

```py
static PyObject *py_print_chars(PyObject *self, PyObject *args)
{
    char *s;
    Py_ssize_t len;
    if (!PyArg_ParseTuple(args, "s#", &s, &len))
    {
        return NULL;
    }
    print_chars(s, len);
    Py_RETURN_NONE;
}
```

对于使用机器原生`**wchar_t**` 类型的库函数，C 扩展代码可以写成–

**代码#4 :**

```py
static PyObject * py_print_wchars(PyObject * self, PyObject * args)
{
    wchar_t * s;
    Py_ssize_t len;
    if (! PyArg_ParseTuple(args, "u#", &s, &len))
    {
        return NULL;
    }
    print_wchars(s, len);
    Py_RETURN_NONE;
}
```

下面的代码检查扩展函数是如何工作的。

需要观察面向字节的函数`**print_chars()**`接收 UTF 8 编码数据的方式，而`**print_wchars()**`接收 Unicode 码点值的方式。

**代码#5 :**

```py
s = 'Spicy Jalape\u00f1o'
print (print_chars(s))

print ("\n", print_wchars(s))
```

**输出:**

```py
53 70 69 63 79 20 4a 61 6c 61 70 65 c3 b1 6f

53 70 69 63 79 20 4a 61 6c 61 70 65 f1 6f

```

让我们检查一下被访问的 C 库的性质。对于许多 C 库来说，传递字节而不是字符串可能更有意义。让我们使用下面给出的转换代码来实现。

**代码#6 :**

```py
static PyObject *py_print_chars(PyObject *self, PyObject *args)
{
    char *s;
    Py_ssize_t len;

    // accepts bytes, bytearray, or other byte-like object 

    if (!PyArg_ParseTuple(args, "y#", &s, &len))
    {
        return NULL;
    }
    print_chars(s, len);
    Py_RETURN_NONE;
}
```

如果仍然希望传递字符串，需要注意的是，Python3 使用了一种适应性强的字符串表示法，这种表示法并不完全直接使用标准类型`char *` 或`wchar_t *`直接映射到 C 库。因此，为了将字符串数据呈现给 C，某种转换几乎总是必要的。 *s#* 和 *u#* 格式代码到`PyArg_ParseTuple()`安全地执行这样的转换。
每当进行转换时，转换后的数据的副本会附加到原始字符串对象上，以便以后可以重用，如下代码所示。

**代码#7 :**

```py
import sys

s = 'Spicy Jalape\u00f1o'
print ("Size : ", sys.getsizeof(s))

print("\n", print_chars(s))

print ("\nSize : ", sys.getsizeof(s))

print ("\n", print_wchars(s))

print ("\nSize : ", sys.getsizeof(s))
```

**输出:**

```py
Size : 87

53 70 69 63 79 20 4a 61 6c 61 70 65 c3 b1 6f

Size : 103    

53 70 69 63 79 20 4a 61 6c 61 70 65 f1 6f

Size : 163    

```