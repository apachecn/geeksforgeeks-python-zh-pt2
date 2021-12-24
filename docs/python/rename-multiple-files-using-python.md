# 使用 Python 重命名多个文件

> 原文:[https://www . geesforgeks . org/rename-multi-file-using-python/](https://www.geeksforgeeks.org/rename-multiple-files-using-python/)

**先决条件:**Python 中的 [OS 模块](https://www.geeksforgeeks.org/os-module-python-examples/)Python 中的
3、*T6】rename()*方法用于重命名文件或目录。这个方法是 [os 模块](https://www.geeksforgeeks.org/os-module-python-examples/)的一部分，非常好用。

【os.rename()的语法:

> **os.rename(src，dst) :** src 是要重命名的文件的源地址，dst 是具有新名称的目的地。

现在假设文件夹中有随机名称的图像。例如，考虑下图:

![](img/3ee17737a3aaa1df342beff9ae7827ad.png)

现在的要求是以有序的方式给它们重新命名，比如 hostel1、hoste 2……等等。手动完成这个任务将是一个乏味的任务，但是这个目标可以使用 os 模块中的 *rename()* 和 *listdir()* 方法来实现。

**listdir** 方法列出给定目录的所有内容。

【listdir()的语法:

> **list = os.listdir('src') :** 其中 src 是要列出的源文件夹。

下面的代码将为我们完成这项工作。它遍历 xyz 文件夹中所有图像的列表，定义目标(dst)和源(src)地址，并使用重命名模块进行重命名。

在 **os.rename(src，dst)** 中作为参数给出的目标(dst)和源(src)地址的公认格式是**“文件夹名/文件名”**。

下面是实现:

## 蟒蛇 3

```
# Pythono3 code to rename multiple
# files in a directory or folder

# importing os module
import os

# Function to rename multiple files
def main():

    folder = "xyz"
    for count, filename in enumerate(os.listdir(folder)):
        dst = f"Hostel {str(count)}.jpg"
        src =f"{folder}/{filename}"  # foldername/filename, if .py file is outside folder
        dst =f"{folder}/{dst}"

        # rename() function will
        # rename all the files
        os.rename(src, dst)

# Driver Code
if __name__ == '__main__':

    # Calling main() function
    main()
```

**输出:**
这个代码的输出看起来是这样的–

![](img/f5a3aa5f4ba1ab8e9a4547dee0cc3ed7.png)

**注意:**此代码可能不会在联机 IDE 中运行，因为它使用了外部图像文件目录。