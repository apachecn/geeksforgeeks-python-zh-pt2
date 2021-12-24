# Python | shutil . get _ terminal _ size()方法

> 原文:[https://www . geesforgeks . org/python-shutil-get _ terminal _ size-method/](https://www.geeksforgeeks.org/python-shutil-get_terminal_size-method/)

**Python 中的 Shutil 模块**提供了很多对文件和文件集合进行高级操作的功能。它属于 Python 的标准实用程序模块。该模块有助于文件和目录复制和删除过程的自动化。
`shutil.get_terminal_size()`方法告诉终端窗口的大小。由于终端是二维的，所以分别检查环境变量 COLUMNS 和 LINES。如果定义了变量，并且该值是正整数，则使用该变量。当未定义列或线时，端子连接到**系统。__stdout__** 通过调用 **os.get_terminal_size()** 进行查询。

> **语法:** shutil.get_terminal_size(回退=(列，行))
> 
> **参数:**
> **回退:**代表终端的列和行的元组。许多终端仿真器使用的回退默认值是(80，24)。
> 
> **返回值:**这个方法返回一个类型为**的命名元组。**

**示例#1 :**

```
# Python program to explain
# shutil.get_terminal_size() method 

# importing shutil module 
import shutil 

# Using shutil.get_terminal_size() method 
terminal_size = shutil.get_terminal_size()

# Print result 
print(terminal_size) 
```

**输出:**

```
os.terminal_size(columns=80, lines=24)

```

**例 2 :**

```
# Python program to explain
# shutil.get_terminal_size() method 

# importing shutil module 
import shutil 

# Using shutil.get_terminal_size() method 
terminal_size = shutil.get_terminal_size((40, 20))

# Print result 
print(terminal_size) 
```

**输出:**

```
os.terminal_size(columns=40, lines=20)

```