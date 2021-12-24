# Python | os。DirEntry.stat()方法

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-OS-direntry-stat 方法/

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

**操作系统模块**的`***os.scandir()***`方法产生对应于由指定路径给出的目录中的条目的`***os.DirEntry***`对象。`***os.DirEntry***`对象具有各种属性和方法，用于公开目录条目的文件路径和其他文件属性。

`***os.DirEntry***`对象上的`***stat()***`方法用于获取一个条目的 *os.stat_result* 对象。

**注意:** `***os.DirEntry***`对象打算在迭代后被使用和丢弃，因为对象的属性和方法会缓存它们的值，并且永远不会再次重新提取这些值。如果文件的元数据已经更改，或者如果调用 ***os.scandir()*** 方法已经很长时间。我们不会得到最新的信息。

> **语法:** os。DirEntry.stat(*，follow _ symlinks = True)
> 
> **参数:**
> **follow_symlinks:** 该参数需要一个布尔值。如果条目是符号链接，并且 follow_symlinks 为 True，则该方法将在符号链接指向的路径上运行。如果条目是符号链接，并且 follow_symlinks 为 False，则该方法将对符号链接本身进行操作。如果条目不是符号链接，则 follow _ symlinks 参数被忽略。此参数的默认值为“真”。
> 
> **返回值:**这个方法为条目返回一个 os.stat_result 对象。以下是 os.stat_result 对象的属性:
> 
> *   **st_mode** :表示文件类型和文件模式位(权限)。
> *   **st_ino** :表示 Unix 上的索引节点号，Windows 平台上的文件索引。
> *   **st_dev** :表示该文件所在设备的标识。
> *   **st_nlink** :表示硬链接数。
> *   **st_uid** :表示文件所有者的用户标识。
> *   **st_gid** :表示文件所有者的组标识。
> *   **st_size** :表示文件的大小，以字节为单位。
> *   **st_atime** :表示最近一次访问的时间。用秒来表示。
> *   **st_mtime** :表示最近一次内容修改的时间。用秒来表示。
> *   **st_ctime** :表示 Unix 上最近一次元数据更改的时间和 Windows 上的创建时间。用秒来表示。
> *   **st_atime_ns** :与 **st_atime** 相同，但时间以纳秒为单位表示为整数。
> *   **st_mtime_ns** :与 **st_mtime** 相同，但时间以纳秒为单位表示为整数。
> *   **st_ctime_ns** :与 **st_ctime** 相同，但时间以纳秒为单位表示为整数。
> *   **st_blocks** :表示分配给文件的 512 字节块数。
> *   **st_rdev** :表示设备类型，如果是 inode 设备。
> *   **st_flags** :表示文件的用户自定义标志。

**代码:**使用`***os.DirEntry.stat()***`方法

```py
# Python program to explain os.DirEntry.stat() method 

# importing os module  
import os

# Directory to be scanned
# Path
path = "/home / ihritik"

# Print status of all
# files in the above
# specified path

# Using os.scandir() method
# scan the specified directory
# and yield os.DirEntry object
# for each file and sub-directory

print("Status of all files in path '% s':" % path) 
with os.scandir(path) as itr:
    for entry in itr :
        # Check if the entry
        # is a file 
        if entry.is_file() :
            # Print file status    
            print("Status of % s:" % entry.name)
            print(entry.stat(), "\n")
```

**Output:**

```py
Status of all files in path '/home/ihritik':
Status of file.txt:
os.stat_result(st_mode=33248, st_ino=801366, st_dev=2056, st_nlink=2, st_uid=1000,
st_gid=1000, st_size=409, st_atime=1566360293, st_mtime=1566287810, 
st_ctime=1566291428)

Status of tree.cpp:
os.stat_result(st_mode=33188, st_ino=801364, st_dev=2056, st_nlink=1, st_uid=1000,
st_gid=1000, st_size=820, st_atime=1565604415, st_mtime=1565604415,
st_ctime=1565604415)

Status of graph.cpp:
os.stat_result(st_mode=33188, st_ino=801237, st_dev=2056, st_nlink=1, st_uid=1000,
st_gid=1000, st_size=1729, st_atime=1561515200, st_mtime=1561515069, 
st_ctime=1561515069)

Status of abc.txt
os.stat_result(st_mode=33434, st_ino=801196, st_dev=2056, st_nlink=1, st_uid=1000,
st_gid=1000, st_size=0, st_atime=1560204341, st_mtime=1560204341, 
st_ctime=1560204349)

```

**参考资料:**[https://docs . python . org/3/library/OS . html # OS。direntry . stat〔T3〕](https://docs.python.org/3/library/os.html#os.DirEntry.stat)