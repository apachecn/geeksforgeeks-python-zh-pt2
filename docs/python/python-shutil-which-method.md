# Python | shutil . what()方法

> 原文:[https://www.geeksforgeeks.org/python-shutil-which-method/](https://www.geeksforgeeks.org/python-shutil-which-method/)

**Python 中的 Shutil 模块**提供了很多对文件和文件集合进行高级操作的功能。它属于 Python 的标准实用程序模块。该模块有助于文件和目录复制和删除过程的自动化。
`shutil.which()`方法告诉一个可执行应用程序的路径，如果给定的 **cmd** 被调用，该程序将运行。此方法可用于在计算机上查找路径上的文件。

> **语法:**shutil . white(cmd，mode = os。F_OK | os。X_OK，路径=无)
> **参数:**
> **cmd:** 代表文件的字符串。
> **模式:**此参数指定方法应执行的模式。 **os。F_OK** 测试路径和**操作系统的存在。X_OK** 检查路径是否可以执行，或者我们可以说模式决定了文件是否存在和可执行。
> **路径:**此参数指定要使用的路径，如果没有指定路径，则使用`os.environ()`的结果
> **返回值:**此方法返回可执行应用程序的路径

**示例#1 :**
使用`shutil.which()`方法获取**蟒**的位置

```
# Python program to explain shutil.which() method 

# importing os module 
import os 

# importing shutil module 
import shutil 

# cmd 
cmd = 'python'

# Using shutil.which() method
locate = shutil.which(cmd)

# Print result
print(locate)
```

**Output:**

```
/usr/bin/python

```

**示例 2 :**
使用`shutil.which()`方法获取 **C++** 的位置

```
# Python program to explain shutil.which() method 

# importing os module 
import os 

# importing shutil module 
import shutil 

# cmd 
cmd = 'c++'

# Using shutil.which() method
locate = shutil.which(cmd)

# Print result
print(locate)
```

**Output:**

```
/usr/bin/c++

```