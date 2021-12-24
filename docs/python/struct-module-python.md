# Python 中的结构模块

> 原文:[https://www.geeksforgeeks.org/struct-module-python/](https://www.geeksforgeeks.org/struct-module-python/)

该模块执行 Python 值和表示为 Python 字节对象的 C 结构之间的转换。格式字符串是用于在打包和解包数据时指定预期布局的机制。模块结构在 Python 3.x 中可用，而在 2.x 中不可用，因此这些代码将在 Python 3 解释器上运行。

**结构功能**

*   **struct.pack()**

    ```
    Syntax: 
    struct.pack(format, v1, v2, ...)
    ```

    返回一个包含值 v1，v2，…的字符串，这些值根据给定的格式打包(格式化字符串是在打包和解包数据时用于指定预期布局的机制)。格式后面的值必须仅与格式一致，否则会引发 struct.error。

    ```
    import struct

    # Format: h is short in C type
    # Format: l is long in C type
    # Format 'hhl' stands for 'short short long'
    var = struct.pack('hhl',1,2,3)
    print(var)

    # Format: i is int in C type
    # Format 'iii' stands for 'int int int'
    var = struct.pack('iii',1,2,3)
    print(var)
    ```

    输出:

    ```
    b'\x01\x00\x02\x00\x00\x00\x00\x00\x03\x00\x00\x00\x00\x00\x00\x00'
    b'\x01\x00\x00\x00\x02\x00\x00\x00\x03\x00\x00\x00'

    ```

*   **struct.unpack()**

    ```
    Syntax:
    struct.unpack(fmt, string)
    ```

    返回根据给定格式(第一个参数)解包的值 v1、v2、…。此函数返回的值作为元组返回，元组的大小等于打包期间通过 struct.pack()传递的值的数量。

    ```
    import struct

    # '?' -> _BOOL , 'h' -> short, 'i' -> int and 'l' -> long
    var = struct.pack('?hil', True, 2, 5, 445)
    print(var)

    # struct.unpack() return a tuples
    # Variables V1, V2, V3,.. are returned as elements of tuple
    tup = struct.unpack('?hil', var)
    print(tup)

    # q -> long long int and f -> float
    var = struct.pack('qf', 5, 2.3)
    print(var)
    tup = struct.unpack('qf', var)
    print(tup)
    ```

    输出:

    ```
    b'\x01\x00\x02\x00\x05\x00\x00\x00\xbd\x01\x00\x00\x00\x00\x00\x00'
    (True, 2, 5, 445)
    b'\x05\x00\x00\x00\x00\x00\x00\x0033\x13@'
    (5, 2.299999952316284)

    ```

    注意:“输出”中的“b”代表二进制。

*   **struct.calcsize()**

    ```
    Syntax:
    struct.calcsize(fmt)
    fmt: format 
    ```

    返回对应于给定格式的结构(以及字符串)的大小。calcsize()是一个重要的函数，对于 struct.pack_into()和 struct.unpack_from()之类的函数是必需的，这些函数也需要偏移量和缓冲区。

    ```
    import struct
    var = struct.pack('?hil', True, 2, 5, 445)
    print(var)
    # Returns the size of the structure
    print(struct.calcsize('?hil'))
    print(struct.calcsize('qf'))
    ```

    输出:

    ```
    b'\x01\x00\x02\x00\x05\x00\x00\x00\xbd\x01\x00\x00\x00\x00\x00\x00'
    16
    12

    ```

    ```
    import struct
    var = struct.pack('bi', 56, 0x12131415)
    print(var)
    print(struct.calcsize('bi'))
    var = struct.pack('ib', 0x12131415, 56)
    print(var)
    print(struct.calcsize('ib'))
    ```

    输出:

    ```
    b'8\x00\x00\x00\x15\x14\x13\x12'
    8
    b'\x15\x14\x13\x128'
    5

    ```

    注意:格式字符的顺序可能会影响大小。

*   **Exception struct.error**
    Exception struct.error describes what is wrong at passing arguments, when a wrong argument is passed struct.error is raised.

    ```
    from struct import error
    print(error)
    ```

    注意:这段代码除了异常处理之外，在任何地方都没有用，它用来显示解释后的“错误”显示了这个类。

*   **struct . pack _ into()**T0】
*   **struct.unpack_from()**

    ```
    Syntax:
    struct.unpack_from(fmt, buffer[,offset = 0])fmt: data type format
    buffer: writable buffer which starts at offset (optional)
    ```

    返回一个元组，类似于 struct.unpack()

    ```
    import struct

    # ctypes in imported to create string buffer
    import ctypes

    # SIZE of the format is calculated using calcsize()
    siz = struct.calcsize('hhl')
    print(siz)

    # Buffer 'buff' is created
    buff = ctypes.create_string_buffer(siz)

    # struct.pack() returns packed data
    # struct.unpack() returns unpacked data
    x = struct.pack('hhl', 2, 2, 3)
    print(x)
    print(struct.unpack('hhl', x))

    # struct.pack_into() packs data into buff, doesn't return any value
    # struct.unpack_from() unpacks data from buff, returns a tuple of values
    struct.pack_into('hhl', buff, 0, 2, 2, 3)
    print(struct.unpack_from('hhl', buff, 0))
    ```

    输出:

    ```
    16
    b'\x02\x00\x02\x00\x00\x00\x00\x00\x03\x00\x00\x00\x00\x00\x00\x00'
    (2, 2, 3)
    (2, 2, 3)

    ```

参考[https://docs.python.org/2/library/struct.html](https://docs.python.org/2/library/struct.html)
本文由**皮尤什门战**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。