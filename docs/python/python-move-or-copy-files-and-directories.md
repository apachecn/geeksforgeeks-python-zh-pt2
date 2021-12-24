# Python |移动或复制文件和目录

> 原文:[https://www . geesforgeks . org/python-移动或复制文件和目录/](https://www.geeksforgeeks.org/python-move-or-copy-files-and-directories/)

假设我们想复制或移动文件和目录，但不想通过调用 shell 命令来实现。 **shutil 模块**具有复制文件和目录功能的可移植实现。

**Code #1 : Using shutil module**

```
import shutil

# Copy src to dst. (cp src dst)
shutil.copy(src, dst)

# Copy files, but preserve metadata (cp -p src dst)
shutil.copy2(src, dst)

# Copy directory tree (cp -R src dst)
shutil.copytree(src, dst)

# Move src to dst (mv src dst)
shutil.move(src, dst)
```

这些函数的参数都是提供文件名或目录名的字符串。底层语义试图模拟类似的 Unix 命令，如注释所示。默认情况下，符号链接后面跟有这些命令。例如，如果源文件是符号链接，那么目标文件将是链接指向的文件的副本。

要复制符号链接，请提供如下代码所示的 *follow_symlinks* 关键字参数:

**代码#2 :**

```
shutil.copy2(src, dst, follow_symlinks = False)

# To preserve symbolic links in copied directories
shutil.copytree(src, dst, symlinks = True)
```

`copytree()`可选地允许在复制过程中忽略某些文件和目录。为此，请提供一个忽略函数，该函数将目录名和文件名列表作为输入，并返回要忽略的名称列表。该示例显示在下面的代码中–

**代码#3 :**

```
def ignore_pyc_files(dirname, filenames):
    return [name in filenames if name.endswith('.pyc')]

shutil.copytree(src, dst, ignore = ignore_pyc_files)
```

由于忽略文件名模式是常见的，已经提供了一个实用函数`ignore_patterns()`来实现它，如下面给出的代码所示。

**代码#4 :**

```
shutil.copytree(src, dst, ignore = shutil.ignore_patterns('*~', '*.pyc'))
```

**它是如何工作的？**

*   使用 **shutil** 复制文件和目录是非常简单的。
*   但是，关于文件元数据的一个注意事项是，像 **copy2()** 这样的函数只会尽最大努力保存这些数据。
*   基本信息(如访问时间、创建时间和权限)将始终保留，但所有者、ACL、资源分叉和其他扩展文件元数据的保留可能会也可能不会起作用，这取决于底层操作系统和用户自己的访问权限。
*   用户可能不想使用类似 **shutil.copytree()** 这样的函数来执行系统备份。

使用文件名时，确保使用 **`os.path`** 中的函数以获得最大的可移植性(尤其是在使用 Unix 和 Windows 的情况下)。

**代码#5:示例**

```
filename = '/Users/gfg/programs/abc.py'

import os.path
os.path.basename(filename)
```

```
'abc.py'
```

```
os.path.dirname(filename)
```

```
'/Users/gfg/programs'
```

```
os.path.split(filename)
```

```
('/Users/gfg/programs', 'abc.py')
```

```
os.path.join('/new/dir', os.path.basename(filename))
```

```
'/new/dir/spam.py'
```

```
os.path.expanduser('~/gfg/programs/spam.py')
```

```
'/Users/gfg/programs/abc.py'
```

用`copytree()`复制目录的一个棘手之处是错误的处理。例如，在复制过程中，函数可能会遇到符号链接断开、文件因权限问题而无法访问等情况。