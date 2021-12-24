# 从 C | Python 中读取类似 Python 文件的对象

> 原文:[https://www . geesforgeks . org/reading-python-file-like-objects-from-c-python/](https://www.geeksforgeeks.org/reading-python-file-like-objects-from-c-python/)

编写 C 扩展代码，使用任何类似 Python 文件的对象(例如，普通文件、StringIO 对象等)中的数据。).`**read()**`方法必须被重复调用以消耗类似文件对象上的数据，并采取步骤来正确解码结果数据。
下面给出的是一个 C 扩展函数，它只消耗一个类似文件的对象上的所有数据，并将其转储到标准输出。

**Code #1 :**

```py
#define CHUNK_SIZE 8192

/* Consume a "file-like" object and write bytes to stdout */
static PyObject* py_consume_file(PyObject* self, PyObject* args)
{
    PyObject* obj;
    PyObject* read_meth;
    PyObject* result = NULL;
    PyObject* read_args;

    if (!PyArg_ParseTuple(args, "O", &obj)) {
        return NULL;
    }

    /* Get the read method of the passed object */
    if ((read_meth = PyObject_GetAttrString(obj, "read")) == NULL) {
        return NULL;
    }

    /* Build the argument list to read() */
    read_args = Py_BuildValue("(i)", CHUNK_SIZE);
    while (1) {
        PyObject* data;
        PyObject* enc_data;
        char* buf;
        Py_ssize_t len;

        /* Call read() */
        if ((data = PyObject_Call(read_meth, read_args, NULL)) == NULL) {
            goto final;
        }

        /* Check for EOF */
        if (PySequence_Length(data) == 0) {
            Py_DECREF(data);
            break;
        }

        /* Encode Unicode as Bytes for C */
        if ((enc_data = PyUnicode_AsEncodedString(data,
             "utf-8", "strict")) == NULL) {
            Py_DECREF(data);
            goto final;
        }

        /* Extract underlying buffer data */
        PyBytes_AsStringAndSize(enc_data, &buf, &len);

        /* Write to stdout (replace with something more useful) */
        write(1, buf, len);

        /* Cleanup */
        Py_DECREF(enc_data);
        Py_DECREF(data);
    }
    result = Py_BuildValue("");

final:
    /* Cleanup */
    Py_DECREF(read_meth);
    Py_DECREF(read_args);
    return result;
}
```

一个类似文件的对象，如 *StringIO* 实例，准备测试代码，然后传入:

**代码#2 :**

```py
import io
f = io.StringIO('Hello\nWorld\n')
import sample
sample.consume_file(f)
```

**输出:**

```py
Hello
World
```

与普通系统文件不同，类似文件的对象不一定是围绕低级文件描述符构建的。因此，一个普通的 C 库函数不能用来访问它。相反，Python 的 C 语言应用编程接口被用来操作类似文件的对象，就像在 Python 中一样。
所以从传递的对象中提取`read()`方法。构建一个参数列表，然后重复传递给`PyObject_Call()`来调用该方法。为了检测文件结束(EOF)，使用`PySequence_Length()`来查看返回的结果是否为零长度。
对于所有的输入/输出操作，关注的是基本编码以及字节和 Unicode 之间的区别。这个方法展示了如何在文本模式下读取文件，并将结果文本解码为 c 可以使用的字节编码。如果文件是在二进制模式下读取的，将只进行微小的更改，如下代码所示。

**代码#3 :**

```py
/* Call read() */
if ((data = PyObject_Call(read_meth, read_args, NULL)) == NULL) {
    goto final;
}

/* Check for EOF */
if (PySequence_Length(data) == 0) {
    Py_DECREF(data);
    break;
}

if (!PyBytes_Check(data)) {
    Py_DECREF(data);
    PyErr_SetString(PyExc_IOError, "File must be in binary mode");
    goto final;
}

/* Extract underlying buffer data */
PyBytes_AsStringAndSize(data, &buf, &len);
```