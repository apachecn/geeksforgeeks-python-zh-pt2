# Python | os.listdir()方法

> 原文:[https://www.geeksforgeeks.org/python-os-listdir-method/](https://www.geeksforgeeks.org/python-os-listdir-method/)

***os.listdir()*** 方法在 python 中用来获取指定目录下所有文件和目录的列表。如果我们没有指定任何目录，那么将返回当前工作目录中的文件和目录列表。

> ***语法:*** os.listdir(路径)
> 
> ***参数:***
> 路径(可选) :目录的路径
> 
> ***返回类型:*** 该方法返回指定路径下所有文件和目录的列表。此方法的返回类型为*列表*。

**代码#1:** 使用 os.listdir()方法

```py
# Python program to explain os.listdir() method 

# importing os module 
import os

# Get the list of all files and directories
# in the root directory
path = "/"
dir_list = os.listdir(path)

print("Files and directories in '", path, "' :") 

# print the list
print(dir_list)
```

**Output:**

```py
Files and directories in ' / ' :
['sys', 'run', 'tmp', 'boot', 'mnt', 'dev', 'proc', 'var', 'bin', 'lib64', 'usr', 
'lib', 'srv', 'home', 'etc', 'opt', 'sbin', 'media']

```

**代码#2:** 使用 os.listdir()方法

```py
# Python program to explain os.listdir() method 

# importing os module 
import os

# Get the path of current working directory
path = os.getcwd()

# Get the list of all files and directories
# in current working directory
dir_list = os.listdir(path)

print("Files and directories in '", path, "' :") 
# print the list
print(dir_list)
```

**Output:**

```py
Files and directories in ' /home/ihritik ' :
['.rstudio-desktop', '.gnome', '.ipython', '.cache', '.config', '.ssh', 'Public',
'Desktop', '.pki', 'R', '.bash_history', '.Rhistory', '.oracle_jre_usage', 'Music', 
'.ICEauthority', 'Documents', 'examples.desktop', '.swipl-dir-history', '.local', 
'.gnupg', '.profile', 'Pictures', '.keras', '.viminfo', '.thunderbird', 'Templates',
'.bashrc', '.bash_logout', '.sudo_as_admin_successful', 'Videos', 'images', 
'tf_wx_model', 'Downloads', '.mozilla', 'geeksforgeeks']

```

**代码#3:** 省略路径参数

```py
# Python program to explain os.listdir() method 

# importing os module 
import os

# If we do not specify any path
# os.listdir() method will return
# the list of all files and directories
# in current working directory

dir_list = os.listdir()

print("Files and directories in  current working directory :") 

# print the list
print(dir_list)
```

**Output:**

```py
Files and directories in current working directory :
['.rstudio-desktop', '.gnome', '.ipython', '.cache', '.config', '.ssh', 'Public',
'Desktop', '.pki', 'R', '.bash_history', '.Rhistory', '.oracle_jre_usage', 'Music', 
'.ICEauthority', 'Documents', 'examples.desktop', '.swipl-dir-history', '.local', 
'.gnupg', '.profile', 'Pictures', '.keras', '.viminfo', '.thunderbird', 'Templates',
'.bashrc', '.bash_logout', '.sudo_as_admin_successful', 'Videos', 'images', 
'tf_wx_model', 'Downloads', '.mozilla', 'geeksforgeeks']

```

我们可以看到*代码#2* 和*代码#3* 的输出是一样的。所以如果我们省略路径参数 `os.listdir()` 方法将返回当前工作目录中所有文件和目录的列表。