# 用 Python 写入文件

> 原文:[https://www.geeksforgeeks.org/writing-to-file-in-python/](https://www.geeksforgeeks.org/writing-to-file-in-python/)

Python 提供了创建、写入和读取文件的内置功能。python 中可以处理两种类型的文件，普通文本文件和二进制文件(用二进制语言编写，0 和 1)。

*   **文本文件:**在这种类型的文件中，每一行文本都以一个名为 EOL(行尾)的特殊字符结束，默认情况下，这是 python 中的新行字符(' \n ')。
*   **二进制文件:**在这种类型的文件中，一行没有终止符，数据在转换成机器可理解的二进制语言后存储。

**注意:**想了解更多文件处理[点击这里](https://www.geeksforgeeks.org/reading-writing-text-files-python/)。

> **<font size="4">目录</font>**
> 
> *   [接入模式](#access)
> *   [打开文件](#opening)
> *   [关闭文件](#closing)
> *   [写入文件](#writing)
>     *   [追加到文件中](#appending)
>     *   [同语句](#with)

#### 存取方式

访问模式控制打开的文件中可能的操作类型。它指的是文件打开后将如何使用。这些模式还定义了文件句柄在文件中的位置。文件句柄就像一个光标，它定义了从哪里读取或写入文件中的数据。读取文件的不同访问模式有–

1.  **只写(' w') :** 打开文件写。对于现有文件，数据会被截断和覆盖。句柄位于文件的开头。如果文件不存在，则创建该文件。
2.  **读写(' w+') :** 打开文件进行读写。对于现有文件，数据会被截断和覆盖。句柄位于文件的开头。
3.  **仅追加(' a') :** 打开文件进行写入。如果文件不存在，则创建该文件。句柄位于文件的末尾。正在写入的数据将被插入到现有数据的末尾。

**注意:**想了解更多访问模式[点击这里](https://www.geeksforgeeks.org/reading-writing-text-files-python/)。

## 打开文件

使用 `open()`功能完成。此功能不需要导入任何模块。

**语法:**

```
File_object = open(r"File_Name", "Access_Mode")

```

该文件应该与 python 程序文件存在于同一个目录中，否则文件的完整地址应该写在文件名的位置。

**注意:**将`r`放在文件名之前，以防止文件名字符串中的字符被视为特殊字符。例如，如果文件地址中有\u temp，则\u t 将被视为 tab 字符，并在无效地址中引发错误。r 使字符串原始，也就是说，它告诉字符串没有任何特殊字符。如果文件在同一个目录中并且地址没有被放置，r 可以被忽略。

```
# Open function to open the file "MyFile1.txt"  
# (same directory) in read mode and 
file1 = open("MyFile.txt", "w") 

# store its reference in the variable file1  
# and "MyFile2.txt" in D:\Text in file2 
file2 = open(r"D:\Text\MyFile2.txt", "w+") 
```

这里，文件 1 被创建为我的文件 1 的对象，文件 2 被创建为我的文件 2 的对象。

## 关闭文件

`close()`函数关闭文件并释放该文件获取的内存空间。当不再需要该文件时，或者如果要以不同的文件模式打开该文件时，将使用它。

**语法:**

```
File_object.close()

```

```
# Opening and Closing a file "MyFile.txt" 
# for object name file1. 
file1 = open("MyFile.txt", "w") 
file1.close() 
```

## 写入文件

有两种方法可以写入文件。

1.  **write() :** 将字符串 str1 插入文本文件中的一行。

    ```
    File_object.write(str1)

    ```

2.  **writeline():**对于字符串元素的列表，每个字符串都被插入到文本文件中。用于一次插入多个字符串。

    ```
    File_object.writelines(L) for L = [str1, str2, str3] 

    ```

**注意:** `‘\n’`被视为两个字节的特殊字符。

**示例:**

```
# Python program to demonstrate
# writing to file

# Opening a file
file1 = open('myfile.txt', 'w')
L = ["This is Delhi \n", "This is Paris \n", "This is London \n"]
s = "Hello\n"

# Writing a string to file
file1.write(s)

# Writing multiple strings
# at a time
file1.writelines(L)

# Closing file
file1.close()

# Checking if the data is
# written to file or not
file1 = open('myfile.txt', 'r')
print(file1.read())
file1.close()
```

**输出:**

```
Hello
This is Delhi
This is Paris
This is London

```

#### 追加到文件

当文件以追加模式打开时，句柄位于文件的末尾。正在写入的数据将被插入到现有数据的末尾。让我们看下面的例子来阐明写模式和追加模式之间的区别。

```
# Python program to illustrate
# Append vs write mode
file1 = open("myfile.txt", "w")
L = ["This is Delhi \n", "This is Paris \n", "This is London \n"]
file1.writelines(L)
file1.close()

# Append-adds at last
file1 = open("myfile.txt", "a")  # append mode
file1.write("Today \n")
file1.close()

file1 = open("myfile.txt", "r")
print("Output of Readlines after appending")
print(file1.read())
print()
file1.close()

# Write-Overwrites
file1 = open("myfile.txt", "w")  # write mode
file1.write("Tomorrow \n")
file1.close()

file1 = open("myfile.txt", "r")
print("Output of Readlines after writing")
print(file1.read())
print()
file1.close()
```

**输出:**

```
Output of Readlines after appending
This is Delhi
This is Paris
This is London
Today

Output of Readlines after writing
Tomorrow

```

#### 带语句

`with` Python 中的语句用于异常处理，使代码更加清晰，可读性更强。它简化了文件流等公共资源的管理。与上述实现不同，使用 with 语句时不需要调用`file.close()`。`with`声明本身确保了资源的适当获取和释放。

**语法:**

```
with open filename as file:

```

```
# Program to show various ways to
# write data to a file using with statement

L = ["This is Delhi \n", "This is Paris \n", "This is London \n"]

# Writing to file
with open("myfile.txt", "w") as file1:
    # Writing data to a file
    file1.write("Hello \n")
    file1.writelines(L)

# Reading from file
with open("myfile.txt", "r+") as file1:
    # Reading form a file
    print(file1.read())
```

**输出:**

```
Hello
This is Delhi
This is Paris
This is London

```

**注:**欲了解更多关于[的声明，请点击此处](https://www.geeksforgeeks.org/with-statement-in-python/)。