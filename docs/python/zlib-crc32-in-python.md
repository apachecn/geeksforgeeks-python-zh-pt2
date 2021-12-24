# python 中的 zlib.crc32()

> 原文:[https://www.geeksforgeeks.org/zlib-crc32-in-python/](https://www.geeksforgeeks.org/zlib-crc32-in-python/)

借助`**zlib.crc32()**`方法，我们可以计算特定数据的 crc32(循环冗余校验)校验和。它会使用`zlib.crc32()`方法给出 32 位整数值作为结果。

> **语法:** `zlib.crc32(s)`
> **返回:**返回无符号的 32 位校验和整数。

**示例#1 :**
在此示例中，我们可以看到，通过使用`zlib.crc32()`方法，我们能够使用此方法计算给定数据的无符号 32 位校验和。

```py
# import zlib and crc32
import zlib

s = b'I love python, Hello world'
# using zlib.crc32() method
t = zlib.crc32(s)

print(t)
```

**输出:**

> Two billion one hundred and eighty-five million twenty-nine thousand two hundred and two

**例 2 :**

```py
# import zlib and crc32
import zlib

s = b'Hello GeeksForGeeks'
# using zlib.crc32() method
t = zlib.crc32(s)

print(t)
```

**输出:**

> Three billion one hundred and sixty-five million five hundred and eighteen thousand six hundred and twenty-four