# Python | shutil . unregister _ unpack _ format()方法

> 原文:[https://www . geesforgeks . org/python-shutil-unregister _ unpack _ format-method/](https://www.geeksforgeeks.org/python-shutil-unregister_unpack_format-method/)

**Python 中的 Shutil 模块**提供了很多对文件和文件集合进行高级操作的功能。它属于 Python 的标准实用程序模块。该模块有助于文件和目录复制和删除过程的自动化。

`***shutil.unregister_unpack_format()***`Python 中的方法用于从可用的支持的解包格式列表中取消注册或移除解包格式。

我们也可以注册一个新的格式，或者使用`***shutil.register_unpack_format()***`方法指定自己的解包现有格式的功能，或者使用`***shutil.get_unpack_formats()***`方法获取所有支持的可用解包格式的列表。

> ***语法:***shutil . unregister _ unpack _ format(名称)
> 
> ***参数:***
> **名称**:表示要从列表中删除的解包格式名称的字符串。
> 
> ***返回类型:*** 此方法不返回值。

**Code:** Use of shutil.unregister_unpack_format() method

```
# Python program to explain shutil.unregister_unpack_format() method  

# importing shutil module 
import shutil

# Get the list of 
# supported unpack formats
formats = shutil.get_unpack_formats()

# Print the list
print("Supported unpack formats:")
print(formats, "\n")

# Remove an unpack format
name = "gztar"
shutil.unregister_unpack_format(name)
print("%s unpack format unregistered successfully." %name, "\n")

# Get the list of 
# supported unpack formats
formats = shutil.get_unpack_formats()

# Print the list
print("Supported unpack formats:")
print(formats, "\n")
```

**Output:**

> 支持的解包格式:
> [('bztar '，[. tar . BZ 2 '，. tbz2']，" bzip2'ed tar-file ")，(' gztar '，tar.gz '，'。tgz']，" gzip'ed tar-file ")，(' tar '，['。tar']，'未压缩的 tar 文件')，(' xztar '，[. . tar . xz '，'。txz']，" xz'ed tar-file ")，(' zip '，['。zip']，' zip 文件')]
> 
> “gztar”解压缩格式已成功注销。
> 
> 支持的解包格式:
> [('bztar '，tar.bz2 '，. tbz2']，" bzip2'ed tar-file ")，(' tar '，[)。tar']，'未压缩的 tar 文件')，(' xztar '，[. . tar . xz '，'。txz']，" xz'ed tar-file ")，(' zip '，['。zip']，' zip 文件')]

**参考:**T2】https://docs.python.org/3/library/shutil.html