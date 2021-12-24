# Python 中的 StringIO 模块

> 原文:[https://www.geeksforgeeks.org/stringio-module-in-python/](https://www.geeksforgeeks.org/stringio-module-in-python/)

**StringIO** 模块是一个内存中类似文件的对象。这个对象可以作为标准文件对象的输入或输出。当创建 StringIO 对象时，通过向构造函数传递一个字符串来初始化它。如果没有传递字符串，字符串将开始为空。在这两种情况下，文件上的初始光标从零开始。

**注意:**这个模块在最新版本的 Python 中不存在，所以要使用这个模块，我们必须将其从 Python 中的 **io 模块**导入为 io.StringIO。

**示例:**

## 蟒蛇 3

```py
# Importing the StringIO module.
from io import StringIO 

# The arbitrary string.
string ='This is initial string.'

# Using the StringIO method to set
# as file object. Now we have an
# object file that we will able to
# treat just like a file.
file = StringIO(string)

# this will read the file
print(file.read())

# We can also write this file.
file.write(" Welcome to geeksforgeeks.")

# This will make the cursor at
# index 0.
file.seek(0)

# This will print the file after
# writing in the initial string.
print('The string after writing is:', file.read())
```

**输出:**

> 这是初始字符串。
> 写后的字符串是:这是初始字符串。欢迎来到极客乐园。

**StringIO 的一些重要方法如下:**

**1。StringIO.getvalue():** 这个函数返回文件的全部内容。

**语法:**

```py
File_name.getvalue()
```

**示例:**

## 蟒蛇 3

```py
# Importing the StringIO module.
from io import StringIO 

# The arbitrary string.
string ='Hello and welcome to GeeksForGeeks.'

# Using the StringIO method to
# set as file object.
file = StringIO(string)

# Retrieve the entire content of the file.
print(file.getvalue())
```

**输出:**

```py
'Hello and welcome to GeeksForGeeks.'
```

**2。**在本文中，我们讨论了返回布尔值(即真或假)的字符串的一些函数:

*   **StringIO.isatty():** 如果流是交互的，则该函数返回 True 如果流不是交互的，则返回 False
*   **StringIO.readable():** 如果文件可读，则该函数返回 True 如果文件不可读，则返回 False。
*   **stringio . written():**如果文件支持写入，则该函数返回 True，如果文件不支持写入，则返回 False。
*   **StringIO.seekable():** 如果文件支持随机访问，则该函数返回 True，如果文件不支持随机访问，则返回 False。
*   **StringIO.closed:** 如果文件关闭，该函数返回 True 如果文件打开，该函数返回 False。

**语法:**

```py
File_name.isatty()
File_name.readable()
File_name.writable()
File_name.seekable()
File_name.closed
```

**示例:**

## 蟒蛇 3

```py
# Importing the StringIO module.
from io import StringIO 

# The arbitrary string.
string ='Hello and welcome to GeeksForGeeks.'

# Using the StringIO method to
# set as file object.
file = StringIO(string)

# This will returns whether the file
# is interactive or not.
print("Is the file stream interactive?", file.isatty())

# This will returns whether the file is
# readable or not.
print("Is the file stream readable?", file.readable())

# This will returns whether the file supports
# writing or not.
print("Is the file stream writable?", file.writable())

# This will returns whether the file is
# seekable or not.
print("Is the file stream seekable?", file.seekable())

# This will returns whether the file is
# closed or not.
print("Is the file closed?", file.closed)
```

**输出:**

```py
Is the file stream interactive? False
Is the file stream readable? True
Is the file stream writable? True
Is the file stream seekable? True
Is the file closed? False
```

**3。stringio . seek():**seek()函数用于设置文件上的光标位置。如果我们对一个文件执行任何读和写操作，光标将被设置在最后一个索引上，因此在文件开始索引处移动光标将使用 seek()。

**语法:**

```py
File_name.seek(argument) 
# Here the argument is passed to tell the 
# function  where to set the cursor position. 
```

**示例:**

## 蟒蛇 3

```py
# Importing the StringIO module.
from io import StringIO 

# The arbitrary string.
string ='Hello and welcome to GeeksForGeeks.'

# Using the StringIO method
# to set as file object.
file = StringIO(string)

# Reading the file:
print(file.read())

# Now if we again want to read
# the file it shows empty file
# because the cursor is set to
# the last index.

# This does not print anything
# because the function returns an
# empty string.
print(file.read())

# Hence to set the cursor position
# to read or write the file again
# we use seek().We can pass any index
# here form(0 to len(file))
file.seek(0)

# Now we can able to read the file again()
print(file.read())
```

**输出:**

```py
Hello and welcome to GeeksForGeeks.
Hello and welcome to GeeksForGeeks.
```

**4。StringIO.truncate():** 此函数用于调整文件流的大小。此方法在提供的索引后删除文件并保存它。

**语法:**

```py
File_name.truncate(size = None)
# We can provide the size from where 
# to truncate the file.
```

**示例:**

## 蟒蛇 3

```py
# Importing the StringIO module.
from io import StringIO 

# The arbitrary string.
string ='Hello and welcome to GeeksForGeeks.'

# Using the StringIO method
# to set as file object.
file = StringIO(string)

# Reading the initial file:
print(file.read())

# To set the cursor at 0.
file.seek(0)

# This will drop the file after
# index 18.
file.truncate(18)

# File after truncate.
print(file.read())
```

**输出:**

```py
Hello and welcome to GeeksForGeeks.
Hello and welcome 
```

**5。StringIO.tell():** 这个方法用来告诉当前流或者文件的光标位置。

**语法:**

```py
File_name.tell()
```

**示例:**

## 蟒蛇 3

```py
# Importing the StringIO module.
from io import StringIO 

# The arbitrary string.
string ='Hello and welcome to GeeksForGeeks.'

# Using the StringIO method to
# set aas file object.
file = StringIO(string)

# Here the cursor is at index 0.
print(file.tell())

# Cursor is set to index 20.
file.seek(20)

# Print the index of cursor
print(file.tell())
```

**输出:**

```py
0
20
```

**6。StringIO.close():** 此方法用于关闭文件。在对文件调用这个函数后，我们不能对文件执行任何操作。如果执行任何操作，它将引发值错误。

**语法:**

```py
File_name.close()
```

**示例:**

## 蟒蛇 3

```py
# Importing the StringIO module.
from io import StringIO 

# The arbitrary string.
string ='Hello and welcome to GeeksForGeeks.'

# Using the StringIO method to
# set as file object.
file = StringIO(string)

# Reading the file.
print(file.read())

# Closing the file.
file.close()

# If we now perform any operation on the file
# it will raise an ValueError.

# This is to know whether the
# file is closed or not.
print("Is the file closed?", file.closed)
```

**输出:**

```py
Hello and welcome to GeeksForGeeks.
Is the file closed? True
```