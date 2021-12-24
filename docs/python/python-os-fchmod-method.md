# Python | os.fchmod()方法

> 原文:[https://www.geeksforgeeks.org/python-os-fchmod-method/](https://www.geeksforgeeks.org/python-os-fchmod-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。
在类似 Unix 的系统中，模式是授予用户、组和其他类访问文件的文件系统权限。
***OS . fchmod()***Python 中的方法用于将指定文件描述符给出的文件模式更改为指定的数字模式。这个方法相当于 ***os.chmod(fd，mode)*** 。
**注:**此方法仅在 Unix 平台上可用。

> **语法:** os.fchmod(fd，模式)
> **参数:**
> **fd:** 要设置模式的文件描述符。
> **模式:**代表要设置的模式的数值。
> *模式*也可以取下列值之一或它们的按位“或”组合:
> 
> *   **stat。S_ISUID :** 执行时设置用户标识
> *   **stat。S_ISGID :** 执行时设置组标识
> *   **stat。S_ENFMT :** 强制执行记录锁定
> *   **stat。S_ISVTX :** 执行后保存文字图像
> *   **stat。S_IREAD :** 由所有者读取。
> *   **stat。S_IWRITE :** 由所有者编写。
> *   **stat。S_IEXEC :** 由所有者执行。
> *   **stat。S_IRWXU :** 由所有者读取、写入和执行
> *   **stat。S_IRUSR :** 由所有者读取
> *   **stat。S_IWUSR :** 由所有者编写。
> *   **stat。S_IXUSR :** 由所有者执行。
> *   **stat。S_IRWXG :** 按组读取、写入和执行
> *   **stat。S_IRGRP :** 分组阅读
> *   **stat。S_IWGRP :** 按组写入
> *   **stat。S_IXGRP :** 按组执行
> *   **stat。S_IRWXO :** 由他人读取、写入和执行。
> *   **stat。S_IROTH :** 其他人阅读
> *   **stat。S_IWOTH :** 他人代写
> *   **stat。S_IXOTH :** 由他人执行
> 
> **返回类型:**此方法不返回值。

**代码:**使用 os.fchmod()方法

## 蟒蛇 3

```py
# Python program to explain os.fchmod() method

# importing os module
import os

# importing stat module
import stat

# File name
filename = "file.txt"

# Open the specified file and
# get the file descriptor
# associated with it using
# os.open() method
fd = os.open(filename, os.O_RDWR)

# Print the current numeric mode
# (octal notation ) of the file
mode = oct(os.stat(fd).st_mode)[-3:]
print("Current numeric mode of the file (octal notation):", mode)

# Now change the mode
# of the file

# octal value 777 as mode means
# read write and execute permission
# for owner, group and others
mode = 0o777
os.fchmod(fd, mode)
print("\nFile mode changed successfully")

# Print the changed numeric mode
# (octal notation ) of the file
mode = oct(os.stat(fd).st_mode)[-3:]
print("Current numeric mode of the file (octal notation):", mode)

# mode parameter can be also
# given by flags defined in
# stat module

# Change mode
mode = stat.S_IRWXU
os.fchmod(fd, mode)
print("\nFile mode changed successfully")
print("Now, File can be read, write and executed by owner only")

# Print the changed numeric mode
# (octal notation ) of the file
mode = oct(os.stat(fd).st_mode)[-3:]
print("Current numeric mode of the file (octal notation):", mode)

# change mode
mode = stat.S_IRWXU | stat.S_IRGRP
os.fchmod(fd, mode)
print("\nFile mode changed successfully")
print("Now, File can be read, write and executed \
by owner but can be read by group")

# Print the changed numeric mode
# (octal notation ) of the file
mode = oct(os.stat(fd).st_mode)[-3:]
print("Current numeric mode of the file (octal notation):", mode)

# Close the file descriptor
os.close(fd)
```

**Output:** 

```py
Current numeric mode of the file (octal notation): 666

File mode changed successfully
Current numeric mode of the file (octal notation): 777

File mode changed successfully
Now, File can be read, write and executed by owner only
Current numeric mode of the file (octal notation): 700

File mode changed successfully
Now, File can be read, write and executed by owner but can be read by group
Current numeric mode of the file (octal notation): 740
```