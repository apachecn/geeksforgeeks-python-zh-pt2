# Python | shutil . get _ archive _ formats()方法

> 原文:[https://www . geesforgeks . org/python-shutil-get _ archive _ formats-method/](https://www.geeksforgeeks.org/python-shutil-get_archive_formats-method/)

**Python 中的 Shutil 模块**提供了很多对文件和文件集合进行高级操作的功能。它属于 Python 的标准实用程序模块。该模块有助于文件和目录复制和删除过程的自动化。

`***shutil.get_archive_formats()***`使用 Python 中的方法获取支持归档的格式列表。
默认情况下，以下格式可用于归档:

*   **zip:** ZIP 文件
*   **tar:** 未压缩的 tar 文件。
*   **gztar:** gzip 和 tar 文件
*   **bztar:**bzip 2’和 tar 文件
*   **xztar:**xz’和 tar 文件

> ***语法:***shutil . get _ archive _ formats()
> 
> ***参数:*** 不需要参数
> 
> ***返回类型:*** 该方法返回一个列表，该列表代表归档支持的格式。列表的每个元素都是一个元组(名称、描述)。

**Code:** Use of shutil.get_archive_formats() method

```
# Python program to explain shutil.get_archive_formats() method 

# importing shutil module 
import shutil

# Get the list of
# supported archiving formats
formats = shutil.get_archive_formats()

# Print the list of
# supported archiving formats 
print("Supported archiving formats:\n", formats)
```

**Output:**

```
Supported archiving formats:
[('bztar', "bzip2'ed tar-file"), ('gztar', "gzip'ed tar-file"),
('tar', 'uncompressed tar file'), ('xztar', "xz'ed tar-file"), ('zip', 'ZIP file')]

```

**参考:**T2】https://docs.python.org/3/library/shutil.html