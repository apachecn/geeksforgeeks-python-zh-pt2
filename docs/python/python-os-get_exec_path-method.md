# Python | os.get_exec_path()方法

> 原文:[https://www . geesforgeks . org/python-OS-get _ exec _ path-method/](https://www.geeksforgeeks.org/python-os-get_exec_path-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

os 模块中的所有函数在文件名和路径无效或不可访问的情况下都会引发 **OSError** ，或者其他具有正确类型但不被操作系统接受的参数。

`***os.get_exec_path()***`Python 中的方法用于获取启动进程时将搜索命名可执行文件的目录列表。

> ***语法:***OS . get _ exec _ path(env = None)
> 
> ***参数:***
> **env** (可选):表示环境变量的字典。此参数的默认值为“无”。如果其值为无[则使用环境](https://www.geeksforgeeks.org/python-os-environ-object/)。
> 
> ***返回类型:*** 该方法返回一个列表，该列表表示启动进程时将用于搜索命名可执行文件的目录路径。

**Code #1:** Use of os.get_exec_path() method

```
# Python program to explain os.get_exec_path() method 

# importing os module 
import os

# Get the list of directories 
# that will be used to search 
# a named executable
# while launching a process
exec_path = os.get_exec_path()

# Print the list
print("Following paths will be searched for a named executable:")
print(exec_path)
```

**Output:**

```
Following paths will be searched for a named executable:
['/usr/local/sbin', '/usr/local/bin', '/usr/sbin', '/usr/bin', '/sbin', '/bin', '/usr/games', '/usr/local/games', '/snap/bin', '/usr/local/java/jdk-10.0.1/bin', '/usr/local/java/jdk-10.0.1/jre/bin', '/opt/jdk-10.0.1/bin', '/opt/jdk-10.0.1/jre/bin']

```

**代码#2:** 指定环境参数

```
# Python program to explain os.get_exec_path() method 

# importing os module 
import os

# Dictionary of environment variable
env = {'HOME': '/home/ihritik'}

# Get the list of directories 
# that will be used to search 
# a named executable
# while launching a process
exec_path = os.get_exec_path(env)

# Print the list
print("Following paths will be searched for a named executable:")
print(exec_path)
```

**Output:**

```
Following paths will be searched for a named executable:
['', '/bin', '/usr/bin']

```