# Python | shutil . unregister _ archive _ format()方法

> 原文:[https://www . geesforgeks . org/python-shutil-unregister _ archive _ format-method/](https://www.geeksforgeeks.org/python-shutil-unregister_archive_format-method/)

**Python 中的 Shutil 模块**提供了很多对文件和文件集合进行高级操作的功能。它属于 Python 的标准实用程序模块。该模块有助于自动化文件和目录的复制和删除过程。

`***shutil.unregister_archive_format()***`Python 中的方法用于从可用的支持的归档格式列表中注销或删除归档格式。

我们也可以注册一个新的格式，或者使用`***shutil.register_archive_format()***`方法指定自己的现有格式归档功能，或者使用`***shutil.get_archive_formats()***`方法获取所有支持的可用归档格式列表。

> ***语法:***shutil . unregister _ archive _ format(名称)
> 
> ***参数:***
> **名称**:表示要从列表中删除的档案格式名称的字符串。
> 
> ***返回类型:*** 此方法不返回值。

**Code:** Use of shutil.unregister_archive_format() method

```py
# Python program to explain shutil.unregister_archive_format() method  

# importing shutil module 
import shutil

# Get the list of 
# supported archive formats
formats = shutil.get_archive_formats()

# Print the list
print("Supported archive formats:")
print(formats, "\n")

# Remove an archive format
name = "bztar"
shutil.unregister_archive_format(name)
print("'% s' archive format unregistered successfully." % name, "\n")

# Get the list of 
# supported archive formats
formats = shutil.get_archive_formats()

# Print the list
print("Supported archive formats:")
print(formats, "\n")
```

**Output:**

> 支持的存档格式:
> [('bztar '，[. tar . BZ 2 '，. tbz2']，" bzip2'ed tar-file ")，(' gztar '，tar.gz '，'。tgz']，" gzip'ed tar-file ")，(' tar '，['。tar']，'未压缩的 tar 文件')，(' xztar '，[. . tar . xz '，'。txz']，" xz'ed tar-file ")，(' zip '，['。zip']，' zip 文件')]
> 
> “bztar”存档格式已成功注销。
> 
> 支持的归档格式:
> [('gztar '，' gzip'ed tar-file ')，(' tar '，'未压缩 tar 文件')，(' xztar '，' xz'ed tar-file ')，(' zip '，' zip 文件')]

**参考:**T2】https://docs.python.org/3/library/shutil.html