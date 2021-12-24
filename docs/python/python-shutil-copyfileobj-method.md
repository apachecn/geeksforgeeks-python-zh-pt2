# Python | shutil . copyfilobj()方法

> 原文:[https://www . geeksforgeeks . org/python-shutil-copilobj-method/](https://www.geeksforgeeks.org/python-shutil-copyfileobj-method/)

**Python 中的 Shutil 模块**提供了很多对文件和文件集合进行高级操作的功能。它属于 Python 的标准实用程序模块。该模块有助于自动处理和删除文件和目录。
***Python 中的 shutil.copyfileobj()*** 方法用于将一个类文件对象的内容复制到另一个类文件对象。默认情况下，该方法以块的形式复制数据，如果需要，我们还可以通过长度参数指定缓冲区大小。
此方法将文件内容从当前文件位置复制到文件末尾。

> ***语法:*** shutil.copyfileobj(fsrc，fdst[，length])
> ***参数:***
> **fsrc:** 表示要复制的源文件的类似文件的对象
> **fdst:** 表示将复制 fsrc 的目标文件的类似文件的对象。
> **长度(可选):**表示缓冲区大小的整数值。
> 类文件对象主要是 StringIO 对象、连接套接字和实际文件对象。
> ***返回类型:*** 此方法不返回任何值。

**代码:**使用***shutil . copyfile obj()***方法将源文件样对象的内容复制到目标文件样对象

## 蟒蛇 3

```py
# Python program to explain shutil.copyfileobj() method

# importing shutil module
import shutil

# Source file
source = 'file.txt'

# Open the source file
# in read mode and
# get the file object
fsrc = open(source, 'r')

# destination file
dest = 'file_copy.txt'

# Open the destination file
# in write mode and
# get the file object
fdst = open(dest, 'w')

# Now, copy the contents of
# file object f1 to f2
# using shutil.copyfileobj() method
shutil.copyfileobj(fsrc, fdst)

# We can also specify
# the buffer size by passing
# optional length parameter
# like shutil.copyfileobj(fsrc, fdst, 1024)

print("Contents of file object copied successfully")

# Close file objects
f1.close()
f2.close()
```

**Output:** 

```py
Contents of file object copied successfully
```

**参考:**T2https://docs.python.org/3/library/shutil.html