# 从 C 和 Python 中释放 GIL 并混合线程

> 原文:[https://www . geeksforgeeks . org/releasing-Gil-and-mixing-threads-from-c-and-python/](https://www.geeksforgeeks.org/releasing-gil-and-mixing-threads-from-c-and-python/)

**在 C 扩展中释放 GIL:**
给出一个 C 扩展代码，需要和 Python 解释器中的其他线程并发执行。为此**必须释放并重新获取全球翻译锁(GIL)** 。

**代码#1:通过插入以下宏来释放和重新获取 GIL**

```py
#include "Python.h"
...
PyObject *pyfunc(PyObject *self, PyObject *args)
{
    ...
    Py_BEGIN_ALLOW_THREADS

    // Threaded C code. 
    // Must not use Python API functions
    ...
    Py_END_ALLOW_THREADS
    ...
    return result;
}
```

**混合来自 C 和 Python 的线程:**
考虑一种情况，给定的程序涉及 C、Python 和线程的混合。但是一些给定的线程是在 Python 解释器控制之外从 C 语言创建的，并且某些线程还利用了 Python C API 中的函数。

**那有什么解决办法？**
如果有 Python、C 和线程的混合，正确初始化和管理 Python 的**全局解释器锁(GIL)** 很重要。下面给出的代码解释了这种情况，它们的代码可以在 C 程序中的任何地方使用(在创建线程之前)。

**代码#2 :**

```py
#include <Python.h>
...
if (!PyEval_ThreadsInitialized())
{
    PyEval_InitThreads();
}
...
```

对于任何涉及 Python 对象或 Python C API 的 C，都需要先获取并发布 GIL。这可以使用`**PyGILState_Ensure()**`和`**PyGILState_Release()**`进行，如下面给出的代码所示。每个到`**PyGILState_Ensure()**`的呼叫必须有一个到`**PyGILState_Release()**`的匹配呼叫。

**代码#3 :**

```py
...
// Make sure we own the GIL
// Use functions in the interpreter
PyGILState_STATE state = PyGILState_Ensure();

...
// Restore previous GIL state and return 
PyGILState_Release(state);
...
```

**注意:**
同时进行这么多事情并不那么容易，涉及到一个 Python 代码、C 代码和它们的线程的混合。要做到这一点，需要注意解释器被正确初始化，并且涉及解释器的 C 代码有正确的 GIL 管理调用，这一切都应该工作。
同样，`**PyGILState_Ensure()**` 调用不会立即抢占或中断解释器。如果其他代码当前正在执行，该功能将被阻止，直到该代码决定释放 ***全局解释器锁(GIL)*** 。