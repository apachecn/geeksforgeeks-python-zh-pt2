# Python | shutil . unpack _ archive()方法

> 原文:[https://www . geesforgeks . org/python-shutil-unpack _ archive-method/](https://www.geeksforgeeks.org/python-shutil-unpack_archive-method/)

**Python 中的 Shutil 模块**提供了很多对文件和文件集合进行高级操作的功能。它属于 Python 的标准实用程序模块。该模块有助于文件和目录复制和删除过程的自动化。
***shutil . unpack _ archive()***Python 中的方法用于解包一个归档文件。

> **语法:**shutil . unpack _ archive(filename[，extract_dir [，format]])
> **参数:**
> **filename:** 表示归档文件完整路径的类路径对象。类似路径的对象是表示路径的字符串或字节对象。
> **extract_dir** (可选):一个类似路径的对象，表示解压归档文件的目标目录的路径。类似路径的对象是表示路径的字符串或字节对象。这是一个可选参数，如果不提供，当前工作目录将用作目标目录。
> **格式**(可选):代表档案格式的字符串。格式的值可以是“zip”、“tar”、“gztar”、“bztar”或“xztar”中的任何一种，也可以是任何其他已注册的解包格式。这也是一个可选参数，如果没有提供，归档文件名的扩展名将用作格式。必须为此扩展注册解包器，否则将引发“ValueError”异常。
> 返回类型:该方法不返回值。

**代码#1:** 使用 shutil.unpack_archive()方法打开归档文件的包装

## 蟒蛇 3

```
# Python program to explain shutil.unpack_archive() method

# importing shutil module
import shutil

# Full path of
# the archive file
filename = "/home/User/Downloads/file.zip"

# Target directory
extract_dir = "/home/ihritik/Documents"

# Format of archive file
archive_format = "zip"

# Unpack the archive file
shutil.unpack_archive(filename, extract_dir, archive_format)
print("Archive file unpacked successfully.")
```

**Output:** 

```
Archive file unpacked successfully.
```

**代码#2:** 使用 shutil.unpack_archive()方法打开归档文件的包装

## 蟒蛇 3

```
# Python program to explain shutil.unpack_archive() method

# importing shutil module
import shutil

# Full path of
# the archive file
filename = "/home/User/Downloads/file.zip"

# Unpack the archived file
shutil.unpack_archive(filename)
print("Archive file unpacked successfully.")

# As extract_dir and format parameters
# are not provided So,
# shutil.unpack_archive() method will
# unpack the archive file in
# current working directory and extension
# of the archive filename i.e zip
# will be taken as format to unpack

```

**Output:** 

```
Archive file unpacked successfully.
```