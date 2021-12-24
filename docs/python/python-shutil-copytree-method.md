# Python | shutil.copytree()方法

> 原文:[https://www . geesforgeks . org/python-shutil-copy tree-method/](https://www.geeksforgeeks.org/python-shutil-copytree-method/)

**Python 中的 Shutil 模块**提供了很多对文件和文件集合进行高级操作的功能。它属于 Python 的标准实用程序模块。该模块有助于文件和目录复制和删除过程的自动化。
`shutil.copytree()`方法递归地将以源(src)为根的整个目录树复制到目标目录。由(dst)命名的目标目录必须不存在。它将在复制过程中创建。使用 [copystat()](https://www.geeksforgeeks.org/python-shutil-copystat-method/) 复制目录的权限和时间，使用 [shutil.copy2()](https://www.google.com/url?client=internal-uds-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/python-shutil-copy2-method/&sa=U&ved=2ahUKEwiduprUl_XiAhUHiHAKHZJXBv8QFjAAegQIBhAB&usg=AOvVaw1-BV1dB94WGX0nnhQDx0Xt) 复制单个文件。

> **语法:** shutil.copytree(src，dst，symlink = False，ignore = None，copy_function = copy2，igonre _ 悬空 _ symlink = False)
> **参数:**
> **src:** 表示源目录路径的字符串。
> **dest:** 表示目的地路径的字符串。
> **符号链接**(可选) :此参数接受 True 或 False，具体取决于原始链接或链接链接的哪些元数据将被复制到新树中。
> **忽略**(可选) :如果给出了忽略，它必须是一个可调用的，它将接收`copytree()`正在访问的目录作为参数，以及其内容的列表，如`os.listdir()`所返回的。
> **copy_function** (可选):该参数默认值为 copy2。对于这个参数，我们可以使用其他复制功能，如`copy()`。
> **igon re _ 悬空 _ symlink**(可选) :该参数值设置为 **True** 时，用于在 symlink 指向的文件不存在的情况下，对引发的异常进行静默。
> **返回值:**这个方法返回一个代表新创建目录路径的字符串。

**示例#1 :**
使用`shutil.copytree()`方法将文件从源复制到目标

```py
# Python program to explain shutil.copytree() method 

# importing os module 
import os 

# importing shutil module 
import shutil 

# path 
path = 'C:/Users / Rajnish / Desktop / GeeksforGeeks'

# List files and directories 
# in 'C:/Users / Rajnish / Desktop / GeeksforGeeks' 
print("Before copying file:") 
print(os.listdir(path)) 

# Source path 
src = 'C:/Users / Rajnish / Desktop / GeeksforGeeks / source'

# Destination path 
dest = 'C:/Users / Rajnish / Desktop / GeeksforGeeks / destination'

# Copy the content of 
# source to destination 
destination = shutil.copytree(src, dest) 

# List files and directories 
# in "C:/Users / Rajnish / Desktop / GeeksforGeeks" 
print("After copying file:") 
print(os.listdir(path)) 

# Print path of newly 
# created file 
print("Destination path:", destination)
```

**Output:**

```py
Before copying file:
['source']
After copying file:
['destination', 'source']
Destination path: C:/Users/Rajnish/Desktop/GeeksforGeeks/destination

```

**例 2 :**
使用`shutil.copytree()`方法通过使用`shutil.copy()`方法复制文件。

```py
# Python program to explain shutil.copytree() method 

# importing os module 
import os 

# importing shutil module 
import shutil 

# path 
path = 'C:/Users / Rajnish / Desktop / GeeksforGeeks'

# List files and directories 
# in 'C:/Users / Rajnish / Desktop / GeeksforGeeks' 
print("Before copying file:") 
print(os.listdir(path)) 

# Source path 
src = 'C:/Users / Rajnish / Desktop / GeeksforGeeks / source'

# Destination path 
dest = 'C:/Users / Rajnish / Desktop / GeeksforGeeks / destination'

# Copy the content of 
# source to destination 
# using shutil.copy() as parameter
destination = shutil.copytree(src, dest, copy_function = shutil.copy) 

# List files and directories 
# in "C:/Users / Rajnish / Desktop / GeeksforGeeks" 
print("After copying file:") 
print(os.listdir(path)) 

# Print path of newly 
# created file 
print("Destination path:", destination)
```

**Output:**

```py
Before copying file:
['source']
After copying file:
['destination', 'source']
Destination path: C:/Users/Rajnish/Desktop/GeeksforGeeks/destination

```