# Python | os.path.expandvars()方法

> 原文:[https://www . geesforgeks . org/python-OS-path-expandvars-method/](https://www.geeksforgeeks.org/python-os-path-expandvars-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。 **os.path** 模块是 Python 中 **OS 模块**的子模块，用于常见的路径名操作。

Python 中的`***os.path.expandvars()***`方法用于扩展给定路径中的环境变量。它用环境变量*名称*的值替换给定路径中形式 *$name* 或 *${name}* 的子字符串。

如果给定路径包含格式错误的环境变量名称或不存在的环境变量，则`***os.path.expandvars()***`方法将保持不变。

在 *Windows* 上，除了 *$name* 和 *${name}* 扩展外，还支持 *%name%* 扩展。

> ***语法:*** os.path.expandvars(路径)
> 
> ***参数:***
> **路径**:表示文件系统路径的类路径对象。类似路径的对象是代表路径的*字符串*或*字节*对象。
> 
> ***返回类型:*** 该方法返回一个字符串，该字符串表示扩展了环境变量的参数。

**代码#1:** 使用 os.path.expandvars()方法

```py
# Python program to explain os.path.expandvars() method 

# importing os.path module 
import os.path

# Path
path = "$HOME/file.txt"

# Expand the environment variables
# with their corresponding 
# value in the given path  
exp_var = os.path.expandvars(path)

# Print the given path with
# environment variables expanded
print(exp_var)

# Change the value of 
# Environment variable 'HOME'

os.environ["HOME"] = "/home/GeeksForGeeks" 

# Path
path = "$HOME/Documents/file.txt"

# Expand the environment variables
# with their corresponding 
# value in the given path  
exp_var = os.path.expandvars(path)

# Print the given path with
# environment variables expanded
print(exp_var)

# Create an environment variable
os.environ["USER"] = "ihritik"

# Path
path = "/home/${USER}/file.txt"

# Expand the environment variables
# with their corresponding 
# value in the given path  
exp_var = os.path.expandvars(path)

# Print the given path with
# environment variables expanded
print(exp_var)

# In the above example,
# os.path.expandvars() method replaced 
# the environment variable 'HOME' and 'USER'
# with their corresponding values
```

**Output:**

```py
/home/ihritik/file.txt
/home/GeeksForGeeks/Documents/file.txt
/home/ihritik/file.txt

```

**代码#2:** 使用 os.path.expandvars()方法(在 Windows 上)

```py
# Python program to explain os.path.expandvars() method 

# importing os.path module 
import os.path

# On Windows % name % expansions
# are supported in addition to
# $name and ${name}

# Path 1
path1 = R"% HOMEPATH %\Directory\file.txt"

# Path 2
path2 = R"C:\Users\$USERNAME\Directory\file.txt"

# Path 3
path3 = R"${TEMP}\file.txt"

# Expand the environment variables
# with their corresponding 
# value in the given paths  
exp_var1 = os.path.expandvars(path1)
exp_var2 = os.path.expandvars(path2)
exp_var3 = os.path.expandvars(path3)

# Print the given paths with
# environment variables expanded
print(exp_var1)
print(exp_var2)
print(exp_var3)

# In the above example 
# os.path.expandvars() method
# replaced the environment variables
# 'HOMEPATH', 'USERNAME' and 'TEMP'
# with their corresponding values
```

**Output:**

```py
\\Users\\Hritik\\\Directory\\file.txt
C:\\Users\\Hritik\\\Directory\\file.txt
C:\\Users\\Hritik\\AppData\\Local\\Temp\\file.txt

```

**代码#3:** 如果环境变量不存在

```py
# Python program to explain os.path.expandvars() method 

# importing os.path module 
import os.path

# If the environment variable 
# is malformed or does not exist
# then the given path will be
# left unchanged

# Path
path = R"${MYHOME}/Directory/file.txt"

# Expand the environment variables
# with their corresponding 
# value in the given paths  
exp_var = os.path.expandvars(path)

# Print the given path with
# environment variables expanded
print(exp_var)

# As 'MYHOME' environment variable
# does not exists so
# os.path.expandvars() method
# will return the given path
# unchanged
```

**Output:**

```py
${MYHOME}/Directory/file.txt

```

**参考:**[https://docs.python.org/3/library/os.path.html](https://docs.python.org/3/library/os.path.html)