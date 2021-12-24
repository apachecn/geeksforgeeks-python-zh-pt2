# Python | os.path.expanduser()方法

> 原文:[https://www . geesforgeks . org/python-OS-path-expanduser-method/](https://www.geeksforgeeks.org/python-os-path-expanduser-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。 **os.path** 模块是 Python 中 **OS 模块**的子模块，用于常见的路径名操作。
***OS . path . expanduser()***Python 中的方法用于将给定路径中的初始路径组件 *~* (颚化符)或~user 扩展到 *user* 的主目录。
在 Unix 平台上，初始的 *~* 被 *HOME* 环境变量的值代替，如果设置的话。否则，***OS . path . expanduser()***方法使用内置模块 *pwd* 在密码目录中搜索*用户的主目录。包含初始*~用户*组件的路径直接在密码目录中查找。
在 Windows 平台上，一个初始的 *~* 被 *HOME* 和 *USERPROFILE* 环境变量的值代替，如果设置的话。否则将使用 *HOMEPATH* 和 *HOMEDRIVE* 环境变量。而包含初始*~用户*组件的路径是通过从上面导出的路径用*~用户*替换最后一个目录组件来处理的。* 

> ***语法:*** os.path.expanduser(路径)
> ***参数:***
> **路径**:表示文件系统路径的类路径对象。类似路径的对象是表示路径的*字符串*或*字节*对象。
> ***返回类型:*** 该方法返回一个字符串值，该值代表在给定路径中展开初始路径组件 *~* 或~user 后的路径。

**代码#1:** 使用 os.path.expanduser()方法(在 Unix 上)

## 蟒蛇 3

```py
# Python program to explain os.path.expanduser() method 

# importing os.path module 
import os.path

# Path
path = "~/file.txt"

# Expand an initial ~ component
# in the given path
# using os.path.expanduser() method
full_path = os.path.expanduser(path)

# print the path after
# expanding the initial ~ component
# in the given path
print(full_path)

# Change the value of
# HOME environment variable
os.environ["HOME"] = "/home / GeeksForGeeks"

# Now, Expand the initial ~ component
# in the same path
# using os.path.expanduser() method
full_path = os.path.expanduser(path)

# print the path after
# expanding initial ~ component
# in the given path
print(full_path)

# While expansion, An initial
# ~user component is looked
# up directly in the password directory.

# Path having an initial
# ~user component
path = "~ihritik / file.txt"

# Expand the initial ~user
# component in the given path
# using os.path.expanduser() method
full_path = os.path.expanduser(path)

# print the path after
# expanding the initial ~user
# component in the given path
print(full_path)
```

**Output:** 

```py
/home/ihritik/file.txt
/home/GeeksForGeeks/file.txt
/home/ihritik/file.txt
```

**代码#2:** 使用 os.path.expanduser()方法(在 Windows 上)

## 蟒蛇 3

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

**代码#3:** 3:如果环境变量不存在

## 蟒蛇 3

```py
# Python program to explain os.path.expandvars() method 

# importing os.path module 
import os.path

# If environment variable 
# is malformed or does not exists
# then the given path will be
# left unchanged

# Path
path = R"${MYHOME}/Directory / file.txt"

# Expand the environment variables
# with their corresponding 
# value in the given paths  
exp_var = os.path.expandvars(path)

# Print the given patha with
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

**参考:**T2https://docs.python.org/3/library/os.path.html