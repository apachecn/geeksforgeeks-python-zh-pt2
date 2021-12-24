# Python 中的 zlib.adler32()

> 原文:[https://www.geeksforgeeks.org/zlib-adler32-in-python/](https://www.geeksforgeeks.org/zlib-adler32-in-python/)

借助`**zlib.adler32()**`方法，我们可以计算 adler32 对特定数据的校验和。它会使用`zlib.adler32()`方法给出 32 位整数值作为结果。

> **语法:** `zlib.adler32(s)`
> **返回:**返回无符号的 32 位校验和整数。

**示例#1 :**
在此示例中，我们可以看到，通过使用`zlib.adler32()`方法，我们能够使用此方法计算给定数据的无符号 32 位校验和。

```
# import zlib and adler32
import zlib

s = b'I love python, Hello world'

# using zlib.adler32() method
t = zlib.adler32(s)

print(t)
```

**输出:**

> Two billion seventy-three million one hundred and two thousand six hundred and ninety-eight

**例 2 :**

```
# import zlib and adler32
import zlib

s = b'Hello GeeksForGeeks'

# using zlib.adler32() method
t = zlib.adler32(s)

print(t)
```

**输出:**

> One billion one hundred and fifty-six million three hundred and eighty-four thousand five hundred and thirty-eight