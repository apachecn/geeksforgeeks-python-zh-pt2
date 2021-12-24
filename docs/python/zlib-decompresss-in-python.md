# 在 Python 中解压缩

> 原文:[https://www.geeksforgeeks.org/zlib-decompresss-in-python/](https://www.geeksforgeeks.org/zlib-decompresss-in-python/)

借助`**zlib.decompress(s)**`方法，我们可以使用`zlib.decompress(s)`方法将字符串的压缩字节解压缩为原始字符串。

> **语法:** `zlib.decompress(string)`
> **返回:**返回解压后的字符串。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`zlib.decompress(s)`方法，我们能够使用该方法将压缩后的字符串解压缩为字符串的字节格式。

```py
# import zlib and decompress
import zlib

s = b'This is GFG author, and final year student.'

# using zlib.compress(s) method
t = zlib.compress(s)
print("Compressed String")
print(t)

print("\nDecompressed String")
print(zlib.decompress(t))
```

**输出:**

> 压缩字符串“
> ”b ' x \ x9c \ x0 b \ xc 9 \ xc8，v \ 0x 00’w7w \ x85 \ xc 4 \ xd 2 \ x92 \ x8c \ xfc " \ x1 d \ x85 \ xc4 \ xbc \ x14 \ x85 \ xbc 4 \ xcc \ xbc \ xc 4 \ x1 c \ x85 \ xca \ xd 4 \ xc 4”\ x85 \ xe 2 \ n
> 
> 这是 GFG 的作者，也是最后一年的学生。'

**例 2 :**

```py
# import zlib and decompress
import zlib

s = b'GeeksForGeeks@12345678'

# using zlib.compress(s) method
t = zlib.compress(s)
print("Compressed String")
print(t)

print("\nDecompressed String")
print(zlib.decompress(t))
```

**输出:**

> 压缩字符串
> b ' x \ x9 CSOM \ xcd . v \ xcb/r \ x07 \ xd 1 \ x0 e \ x86 f \ xc 6&\ xa 6f \ xe 6 \ x16 \ x00 x \ xf 6 \ X6 \ xea’
> 
> 解压缩字符串
> b ' geeksforgeks @ 12345678 '