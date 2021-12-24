# Python | os.renames()方法

> 原文:[https://www.geeksforgeeks.org/python-os-renames-method/](https://www.geeksforgeeks.org/python-os-renames-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

`os.renames()`方法是递归的目录或文件重命名功能。它的工作方式类似于`os.rename()`方法，除了创建任何需要的中间目录，然后首先尝试。重命名完成后，对应于旧名称最右边路径段的目录将使用`os.removedirs()`删除。

> **语法:** os .重命名(旧，新)
> 
> **参数:**
> **旧:**这是要重命名的文件或目录的旧名称。
> **new:** 这是文件或目录的新名称。它可以包括一个到
> 目录的文件，或者一整棵树不存在的目录。
> **注意:**对于**旧的****新的**也可以接受一个**类路径的对象**。
> 
> **返回值:**此方法不返回值。

**示例#1 :** 使用`os.renames()`方法重命名文件

```py
# Python program to explain os.renames() method 

# importing os module 
import os 

# path 
path = 'C:/Users/Rajnish/Desktop/GeeksforGeeks'

# Changing directory 
os.chdir(path)

# Printing current directory
print ("Current directory is: ", os.getcwd())

# List files and directories 
# in 'C:/Users/Rajnish/Desktop/GeeksforGeeks'
print("Before renaming file:") 
print(os.listdir(os.getcwd())) 

# Rename the file
# Using os.renames() method
os.renames('testfile.txt', 'new_name.txt') 

# List files and directories 
# in 'C:/Users/Rajnish/Desktop/GeeksforGeeks'
print("After renaming file:") 
print(os.listdir(os.getcwd())) 
```

**Output:**

```py
Current directory is: C:\Users\Rajnish\Desktop\GeeksforGeeks
Before renaming file:
['testfile.txt']
After renaming file:
['new_name.txt']

```

**示例 2 :**
使用`os.renames()`方法重命名文件，并将其添加到不存在的新目录中

```py
# Python program to explain os.renames() method 

# importing os module 
import os 

# path 
path = 'C:/Users/Rajnish/Desktop/GeeksforGeeks'
# Changing directory 
os.chdir(path)

# Printing current directory
print ("Current directory is: " os.getcwd())

# List files and directories 
# in 'C:/Users/Rajnish/Desktop/GeeksforGeeks'
print("Before renaming file:") 
print(os.listdir(os.getcwd())) 

# Rename the file and
# adding the file in new
# directory name 'newdir'
# Using os.renames() method
os.renames('testfile.txt', 'newdir / new_name.txt') 

# List files and directories 
# in 'C:/Users/Rajnish/Desktop/GeeksforGeeks'
print("After renaming file:") 
print(os.listdir(os.getcwd())) 
```

**Output:**

```py
Current directory is: C:\Users\Rajnish\Desktop\GeeksforGeeks
Before renaming file:
['newdir', 'testfile.txt']
After renaming file:
['newdir']

```