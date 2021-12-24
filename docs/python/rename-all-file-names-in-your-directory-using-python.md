# 使用 Python 重命名目录中的所有文件名

> 原文:[https://www . geesforgeks . org/rename-all-文件名-在您的目录中-使用-python/](https://www.geeksforgeeks.org/rename-all-file-names-in-your-directory-using-python/)

给定一个目录中具有不同名称的多个文件，任务是按排序顺序重命名所有这些文件。
我们可以使用[操作系统模块](https://www.geeksforgeeks.org/os-module-python-examples/)来做这个操作。Python 中的[操作系统模块](https://www.geeksforgeeks.org/os-module-python-examples/)提供了与操作系统交互的功能，并提供了使用操作系统相关功能的可移植方式。我们可以使用 os.getcwd()方法转到当前工作目录，并使用 os.rame()方法重命名文件。

下面是 Python 实现:

## 蟒蛇 3

```
# Python program to rename all file
# names in your directory
import os

os.chdir('D:\\Geeksforgeeks')
print(os.getcwd())

for count, f in enumerate(os.listdir()):
    f_name, f_ext = os.path.splitext(f)
    f_name = "geek" + str(count)

    new_name = f'{f_name}{f_ext}'
    os.rename(f, new_name)
```