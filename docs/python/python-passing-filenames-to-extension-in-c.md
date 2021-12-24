# Python |在 C #中将文件名传递给扩展名

> 原文:[https://www . geesforgeks . org/python-传递-filename-to-extension-in-c/](https://www.geeksforgeeks.org/python-passing-filenames-to-extension-in-c/)

在将文件名传递给 C 库函数之前，文件名必须根据系统预期的文件名编码进行编码。

**代码#1:要编写接收文件名**

```
static PyObject* py_get_filename(PyObject* self, PyObject* args)
{
    PyObject* bytes;
    char* filename;
    Py_ssize_t len;

    if (!PyArg_ParseTuple(args, "O&", PyUnicode_FSConverter, &bytes)) {
        return NULL;
    }

    PyBytes_AsStringAndSize(bytes, &filename, &len);
    /* Use filename */
    /* Cleanup and return */
    Py_DECREF(bytes)
        Py_RETURN_NONE;
}
```

的扩展函数，如果已经存在需要转换为文件名的`PyObject *`，则使用下面给出的代码:

**代码#2 :**

```
/* Object with the filename */
PyObject* obj;
PyObject* bytes;

char* filename;
Py_ssize_t len;

bytes = PyUnicode_EncodeFSDefault(obj);
PyBytes_AsStringAndSize(bytes, &filename, &len);

/* Use filename */
...
    /* Cleanup */
    Py_DECREF(bytes);
```

如果文件名要返回 Python，则使用下面给出的代码–

**代码#3 :**

```
/* Turn a filename into a Python object */
char* filename;
int filename_len;
PyObject* obj = PyUnicode_DecodeFSDefaultAndSize(
    filename, filename_len);
```

处理文件名文件名的处理方式是，如果在扩展 C 代码中使用以上内容。

**将打开的文件传递给 C 扩展–**

**代码#4:要将文件转换为整数文件描述符，请使用`PyFile_FromFd()`**

```
PyObject* fobj;
int fd = PyObject_AsFileDescriptor(fobj);
if (fd < 0) {
    return NULL;
}
```

通过调用 *fobj* 上的`fileno()`方法获得结果文件描述符。因此，以这种方式公开描述符的任何对象都应该可以工作(例如，文件、套接字等)。).描述符可以传递给各种期望处理文件的低级 C 函数。`PyFile_FromFd()`用于将整数文件描述符转换回 Python 对象。

**代码#5 :**

```
/* Existing file descriptor (already open) */
int fd;

PyObject* fobj = PyFile_FromFd(fd, "filename",
                   "r", -1, NULL, NULL, NULL, 1);
```

`PyFile_FromFd()`的参数反映了内置 open()函数的参数。空值只是表示正在使用编码、错误和换行符的默认设置。