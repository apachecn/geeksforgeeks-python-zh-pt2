# Python 中的 Shutil 模块

> 原文:[https://www.geeksforgeeks.org/shutil-module-in-python/](https://www.geeksforgeeks.org/shutil-module-in-python/)

Shutil 模块提供对文件的高级操作，如文件的复制、创建和远程操作。它属于 Python 的标准实用程序模块。该模块有助于自动化文件和目录的复制和删除过程。在本文中，我们将学习这个模块。

## 将文件复制到另一个目录

[**shutil . copy()**](https://www.geeksforgeeks.org/python-shutil-copy-method/)Python 中的方法是用来将源文件的内容复制到目标文件或目录中。它还保留了文件的权限模式，但文件的其他元数据(如文件的创建和修改时间)不会被保留。
源必须代表文件，但目标可以是文件或目录。如果目标是一个目录，那么文件将使用来自源的基本文件名复制到目标中。此外，目标必须是可写的。如果目标是一个文件，并且已经存在，那么它将被替换为源文件，否则将创建一个新文件。

> **语法:** shutil.copy(源，目标，* follow _ symlinks = True)
> 
> **参数:**
> 
> *   source:表示源文件路径的字符串。
> *   目标:表示目标文件或目录路径的字符串。
> *   follow _ symlinks(可选) :此参数的默认值为 True。如果为假，并且源表示符号链接，则目标将被创建为符号链接。
> 
> **返回类型:**该方法返回一个字符串，代表新创建文件的路径。

**例 1:**

## 蟒蛇 3

```py
# Python program to explain shutil.copy() method 

# importing shutil module 
import shutil 

source = "path/main.py"
destination ="path/main2.py"

# Copy the content of 
# source to destination 
dest = shutil.copy(source, destination) 

# Print path of newly 
# created file 
print("Destination path:", dest) 
```

**输出:**

```py
Destination path: path/main2.py
```

**例 2:** 如果目的地是目录。

## 蟒蛇 3

```py
# importing shutil module  
import shutil 

# Source path 
source = "path/main.py"

# Destination path 
destination = "path/gfg/"

# Copy the content of 
# source to destination 
dest = shutil.copy(source, destination) 

# Print path of newly  
# created file 
print("Destination path:", dest) 
```

**输出:**

```py
path/gfg/main.py
```

## 将元数据与文件一起复制

[**shutil . copy 2()**](https://www.geeksforgeeks.org/python-shutil-copy2-method/)Python 中的方法是将源文件的内容复制到目标文件或目录中。此方法与 **shutil.copy()** 方法相同，但它也尝试保留文件的元数据。

> **语法:** shutil.copy2(源，目标，* follow _ symlink = True)
> 
> **参数:**
> 
> *   **来源**:代表源文件路径的字符串。
> *   **目标:**表示目标文件或目录路径的字符串。
> *   **follow _ symlink(可选):**此参数的默认值为 True。如果为 False，并且源表示符号链接，则它会尝试将所有元数据从源符号链接复制到新创建的目标符号链接。该功能依赖于平台。
> 
> **返回类型:**该方法返回一个字符串，代表新创建文件的路径。

## 蟒蛇 3

```py
# Python program to explain shutil.copy2() method 

# importing os module 
import os 

# importing shutil module 
import shutil 

# path 
path = 'csv/'

# List files and directories 
# in '/home/User/Documents' 
print("Before copying file:") 
print(os.listdir(path)) 

# Source path 
source = "csv/main.py"

# Print the metadeta 
# of source file 
metadata = os.stat(source) 
print("Metadata:", metadata, "\n") 

# Destination path 
destination = "csv/gfg/check.txt"

# Copy the content of 
# source to destination 
dest = shutil.copy2(source, destination) 

# List files and directories 
# in "/home / User / Documents" 
print("After copying file:") 
print(os.listdir(path)) 

# Print the metadata 
# of the destination file 
matadata = os.stat(destination) 
print("Metadata:", metadata) 

# Print path of newly 
# created file 
print("Destination path:", dest) 
```

**输出:**

> 复制文件前:
> 
> ['archive (2)'，' c.jpg '，' c.PNG '，' Capture。PNG '，' cc.jpg '，' check.zip '，' cv.csv '，' d.png '，' Done！条款和条件生成器–最快的免费条款和条件生成器！。pdf '，' file1.csv '，' gfg '，' haarcscade _ frontal face _ alt2 . XML '，' log_transformed.jpg '，' main.py '，' nba.csv '，' new_gfg.png '，' r.gif '，' Result -_ 条款和条件已准备就绪！。pdf '，' rockyou.txt '，' sample.txt']
> 
> 元数据:os.stat_result(st_mode=33206，st_ino=2251799814202896，st_dev=1689971230，st_nlink=1，st_uid=0，st_gid=0，st_size=1916，st_atime=1612953710，st_mtime=1612613202，st _ ctime = 1612522940
> 
> 复制文件后:
> 
> ['archive (2)'，' c.jpg '，' c.PNG '，' Capture。PNG '，' cc.jpg '，' check.zip '，' cv.csv '，' d.png '，' Done！条款和条件生成器–最快的免费条款和条件生成器！。pdf '，' file1.csv '，' gfg '，' haarcscade _ frontal face _ alt2 . XML '，' log_transformed.jpg '，' main.py '，' nba.csv '，' new_gfg.png '，' r.gif '，' Result -_ 条款和条件已准备就绪！。pdf '，' rockyou.txt '，' sample.txt']
> 
> 元数据:os.stat_result(st_mode=33206，st_ino=2251799814202896，st_dev=1689971230，st_nlink=1，st_uid=0，st_gid=0，st_size=1916，st_atime=1612953710，st_mtime=1612613202，st _ ctime = 1612522940
> 
> 目标路径:csv/gfg/check.txt

**示例 2:** 如果目的地是目录

## 蟒蛇 3

```py
# Python program to explain shutil.copy2() method 
# importing os module 
import os 

# importing shutil module 
import shutil 

# Source path 
source = "csv/main.py"

# Destination path 
destination = "csv/gfg/"

# Copy the content of 
# source to destination 
dest = shutil.copy2(source, destination) 

# List files and directories 
# in "/home / User / Desktop" 
print("After copying file:") 
print(os.listdir(destination)) 

# Print path of newly 
# created file 
print("Destination path:", dest) 
```

**输出:**

> 复制文件后:
> 
> ['cc.jpg '，' check.txt '，' log_transformed.jpg '，' main.py '，' main2.py '
> 
> 目标路径:csv/gfg/main.py

## **将一个文件的内容复制到另一个文件中**

[**shutil . copy file()**](https://www.geeksforgeeks.org/python-shutil-copyfile-method/)Python 中的方法是用来将源文件的内容复制到目标文件中。不会复制文件的元数据。源和目标必须代表一个文件，目标必须是可写的。如果目标已经存在，则它将被源文件替换，否则将创建一个新文件。

如果源和目标表示同一个文件，那么将引发 SameFileError 异常。

> **语法:** shutil.copyfile(源，目标，* follow _ symlinks = True)
> 
> **参数:**
> 
> *   **来源:**代表源文件路径的字符串。
> *   **目标:**表示目标文件路径的字符串。
> *   **follow _ symlink(可选):**此参数的默认值为 True。如果“假”和“源”表示符号链接，则将创建一个新的符号链接，而不是复制文件。
> 
> **返回类型:**该方法返回一个字符串，代表新创建文件的路径。

## 蟒蛇 3

```py
# Python program to explain shutil.copyfile() method 
# importing shutil module 
import shutil 

# Source path 
source = "csv/main.py"

# Destination path 
destination = "csv/gfg/main_2.py"

dest = shutil.copyfile(source, destination) 

print("Destination path:", dest) 
```

**输出:**

```py
Destination path: csv/gfg/main_2.py
```

## 复制完整的目录

[**shutil . copy tree()**](https://www.geeksforgeeks.org/python-shutil-copytree-method/)方法递归地将一整棵以源(src)为根的目录树复制到目标目录。由(dst)命名的目标目录必须不存在。它将在复制过程中创建。

> **语法:** shutil.copytree(src，dst，symlink = False，ignore = None，copy_function = copy2，igonre _ 悬空 _ symlinks = False)
> 
> **参数:**
> **src:** 代表源目录路径的字符串。
> **dest:** 代表目的地路径的字符串。
> **符号链接(可选):**此参数接受 True 或 False，具体取决于原始链接或链接链接的元数据将被复制到新的树中。
> **忽略(可选):**如果给定了忽略，它必须是一个可调用的，它将接收 copytree()访问的目录作为参数，以及 os.listdir()返回的目录列表。
> **copy_function(可选):**此参数默认值为 copy2。对于这个参数，我们可以使用像 copy()这样的其他复制函数。
> **igon re _ 悬空 _ symlinks(可选):**此参数值设置为 True 时，用于在 symlink 指向的文件不存在时，对引发的异常进行静默。
> 
> **返回值:**这个方法返回一个字符串，代表新创建目录的路径。

## 蟒蛇 3

```py
# Python program to explain shutil.copytree() method 
# importing os module 
import os 

# importing shutil module 
import shutil 

# path 
path = 'C:/Users/ksaty/csv/gfg'

print("Before copying file:") 
print(os.listdir(path)) 

# Source path 
src = 'C:/Users/ksaty/csv/gfg'

# Destination path 
dest = 'C:/Users/ksaty/csv/gfg/dest'

# Copy the content of 
# source to destination 
destination = shutil.copytree(src, dest) 

print("After copying file:") 
print(os.listdir(path)) 

# Print path of newly 
# created file 
print("Destination path:", destination) 
```

**输出:**

> 复制文件前:
> 
> [“cc . jpg”、“check.txt”、“log_transformed.jpg”、“main.py”、“main2.py”、“main _ 2 . py”]
> 
> 复制文件后:
> 
> [“cc . jpg”、“check.txt”、“dest”、“log_transformed.jpg”、“main.py”、“main2.py”、“main _ 2 . py”]
> 
> 目标路径:C:/Users/ksaty/csv/gfg/dest

## 删除目录

[**shutil.rmtree()**](https://www.geeksforgeeks.org/delete-an-entire-directory-tree-using-python-shutil-rmtree-method/) 用于删除一个完整的目录树，路径必须指向一个目录(但不能是指向一个目录的符号链接)。

> ***语法:** shutil.rmtree(路径，ignore_errors=False，onerror=None)*
> 
> ***参数:***
> ***路径:**表示文件路径的类路径对象。类似路径的对象是表示路径的字符串或字节对象。*
> ***ignore_errors:**如果 ignore _ errors 为真，则删除失败导致的错误将被忽略。*
> ***oneerror:**如果 ignore_errors 为 false 或省略，则通过调用 one error 指定的处理程序来处理此类错误。*

## 蟒蛇 3

```py
# Python program to demonstrate 
# shutil.rmtree() 

import shutil 
import os 

# location 
location = "csv/gfg/"

# directory 
dir = "dest"

# path 
path = os.path.join(location, dir) 

# removing directory 
shutil.rmtree(path) 
```

## 查找文件

[**shutil . what()**](https://www.geeksforgeeks.org/python-shutil-which-method/)方法告诉一个可执行应用程序的路径，如果给定的 **cmd** 被调用，该程序将运行。此方法可用于在计算机上查找路径上的文件。

> ***语法:**shutil . white(cmd，mode = os。F_OK | os。X_OK，路径= None)*
> ***参数:***
> ***cmd:** 代表文件的字符串。*
> ***模式:**该参数指定方法执行的模式。 **os。F_OK** 测试路径和 **os 的存在。X_OK** 检查路径是否可以执行，或者我们可以说模式决定文件是否存在和可执行。*
> ***路径:**此参数指定要使用的路径，如果没有指定路径，则使用 os.environ()的结果*
> ***返回值:**此方法返回可执行应用程序的路径*

## 蟒蛇 3

```py
# importing shutil module  
import shutil  

# file search  
cmd = 'anaconda'

# Using shutil.which() method 
locate = shutil.which(cmd) 

# Print result 
print(locate)
```

**输出:**

```py
D:\Installation_bulk\Scripts\anaconda.EXE
```