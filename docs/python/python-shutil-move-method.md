# Python | shutil.move()方法

> 原文:[https://www.geeksforgeeks.org/python-shutil-move-method/](https://www.geeksforgeeks.org/python-shutil-move-method/)

**Python 中的 Shutil 模块**提供了很多对文件和文件集合进行高级操作的功能。它属于 Python 的标准实用程序模块。该模块有助于自动化文件和目录的复制和删除过程。
**`shutil.move()`** 方法递归地将一个文件或目录(源)移动到另一个位置(目标)并返回目标。如果目标目录已经存在，那么 src 将被移动到该目录中。如果目标已经存在，但不是目录，那么它可能会被覆盖，这取决于`os.rename()`语义。

> **语法:** shutil.move(源，目标，copy_function = copy2)
> 
> **参数:**
> **来源:**代表源文件路径的字符串。
> **目的地:**表示目的地目录路径的字符串。
> **copy_function** (可选):该参数默认值为 copy2。对于这个参数，我们可以使用其他复制函数，如 copy、copytree 等。
> 
> **返回值:**该方法返回一个字符串，代表新创建文件的路径。

**示例#1 :**

使用`shutil.move()`方法将文件从源移动到目标

```py
# Python program to explain shutil.move() method 

# importing os module 
import os 

# importing shutil module 
import shutil 

# path 
path = 'C:/Users/Rajnish/Desktop/GeeksforGeeks'

# List files and directories 
# in 'C:/Users/Rajnish/Desktop/GeeksforGeeks' 
print("Before moving file:") 
print(os.listdir(path)) 

# Source path 
source = 'C:/Users/Rajnish/Desktop/GeeksforGeeks/source'

# Destination path 
destination = 'C:/Users/Rajnish/Desktop/GeeksforGeeks/destination'

# Move the content of 
# source to destination 
dest = shutil.move(source, destination) 

# List files and directories 
# in "C:/Users / Rajnish / Desktop / GeeksforGeeks" 
print("After moving file:") 
print(os.listdir(path)) 

# Print path of newly 
# created file 
print("Destination path:", dest) 
```

**Output:**

```py
Before moving file:
['source']
After moving file:
['destination']
Destination path: C:/Users/Rajnish/Desktop/GeeksforGeeks/destination

```

**示例 2 :**
使用`shutil.move()`方法通过使用`shutil.copytree()`方法移动文件，并且目标目录已经存在。

```py
# Python program to explain shutil.move() method 

# importing os module 
import os 

# importing shutil module 
import shutil 

# path 
path = 'C:/Users/Rajnish/Desktop/GeeksforGeeks'

# List files and directories 
# in 'C:/Users/Rajnish/Desktop/GeeksforGeeks' 
print("Before moving file:") 
print(os.listdir(path)) 

# Source path 
source = 'C:/Users/Rajnish/Desktop/GeeksforGeeks/source'

# Destination path 
destination = 'C:/Users/Rajnish/Desktop/GeeksforGeeks/destination'

# Move the content of 
# source to destination
# using shutil.copytree() as parameter
dest = shutil.move(source, destination, copy_function = shutil.copytree) 

# List files and directories 
# in "C:/Users / Rajnish / Desktop / GeeksforGeeks" 
print("After moving file:") 
print(os.listdir(path)) 

# Print path of newly 
# created file 
print("Destination path:", dest) 
```

**Output:**

```py
Before moving file:
['destination', 'source']
After moving file:
['destination']
Destination path: C:/Users/Rajnish/Desktop/GeeksforGeeks/destination\source

```