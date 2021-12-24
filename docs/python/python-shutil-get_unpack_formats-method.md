# Python | shutil . get _ unpack _ formats()方法

> 原文:[https://www . geesforgeks . org/python-shutil-get _ unpack _ formats-method/](https://www.geeksforgeeks.org/python-shutil-get_unpack_formats-method/)

**Python 中的 Shutil 模块**提供了很多对文件和文件集合进行高级操作的功能。它属于 Python 的标准实用程序模块。该模块有助于文件和目录复制和删除过程的自动化。

`***shutil.get_unpack_formats()***`Python 中的方法用于获取所有支持的可用于解包归档文件的格式列表。
默认情况下，以下格式可用于打开归档文件:

*   **zip:** ZIP 文件。如果 *zlib* 模块可用
*   **tar:** 未压缩的 tar 文件。
*   **gztar:** gzip'ed tar-file。如果 *zlib* 模块可用
*   **bztar:** bzip2'ed tar-file。如果 *bz2* 模块可用
*   **xztar:** xz'ed tar-file。如果 *lzma* 模块可用

我们也可以注册新的格式，或者使用`***shutil.register_unpack_format()***`方法指定自己的拆包现有格式的功能，或者使用`***shutil.unregister_unpack_format()***`方法注销现有格式。

> ***语法:***shutil . get _ unpack _ formats()
> 
> ***参数:*** 不需要参数
> 
> ***返回类型:*** 该方法返回一个列表，该列表代表打开归档文件时支持的可用格式。列表的每个元素都是一个元组(名称、扩展描述)。

**Code:** Use of shutil.get_unpack_formats() method

```
# Python program to explain shutil.get_unpack_formats() method 

# importing shutil module 
import shutil

# Get the list of 
# supported unpacking formats
formats = shutil.get_unpack_formats()

# Print the list
print("Supported unpacking formats:\n", formats)
```

**Output:**

```
Supported unpacking formats:
Supported unpacking formats:
 [('bztar', ['.tar.bz2', '.tbz2'], "bzip2'ed tar-file"), ('gztar', ['.tar.gz', '.tgz'], "gzip'ed tar-file"), ('tar', ['.tar'], 'uncompressed tar file'), ('xztar', ['.tar.xz', '.txz'], "xz'ed tar-file"), ('zip', ['.zip'], 'ZIP file')]

```

**参考:**T2】https://docs.python.org/3/library/shutil.html