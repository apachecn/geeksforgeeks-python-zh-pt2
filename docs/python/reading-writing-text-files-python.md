# Python 中文本文件的读写

> 原文:[https://www . geesforgeks . org/read-writing-text-files-python/](https://www.geeksforgeeks.org/reading-writing-text-files-python/)

Python 提供了创建、写入和读取文件的内置功能。python 中可以处理两种类型的文件，普通文本文件和二进制文件(用二进制语言编写，0 和 1)。

*   **文本文件:**在这种类型的文件中，每一行文本都以一个名为 EOL(行尾)的特殊字符结束，默认情况下，这是 python 中的新行字符(' \n ')。
*   **二进制文件:**在这种类型的文件中，一行没有终止符，数据在转换成机器可理解的二进制语言后存储。

在本文中，我们将重点讨论在文本文件中打开、关闭、读取和写入数据。

**文件访问模式**

访问模式控制打开的文件中可能的操作类型。它指的是文件打开后将如何使用。这些模式还定义了文件中**文件句柄**的位置。文件句柄就像一个光标，它定义了从哪里读取或写入文件中的数据。python 中有 6 种访问模式。

1.  **只读(' r') :** 打开文本文件阅读。句柄位于文件的开头。如果文件不存在，将引发输入/输出错误。这也是打开文件的默认模式。
2.  **读写(' r+') :** 打开文件进行读写。句柄位于文件的开头。如果文件不存在，将引发输入/输出错误。
3.  **只写(' w') :** 打开文件写。对于现有文件，数据被截断和覆盖。句柄位于文件的开头。如果文件不存在，则创建该文件。
4.  **读写(' w+')** :打开文件进行读写。对于现有文件，数据被截断和覆盖。句柄位于文件的开头。
5.  **仅追加(' a')** :打开文件进行写入。如果文件不存在，则创建该文件。句柄位于文件的末尾。正在写入的数据将被插入到现有数据的末尾。
6.  **追加并读取(' a+') :** 打开文件进行读写。如果文件不存在，则创建该文件。句柄位于文件的末尾。正在写入的数据将被插入到现有数据的末尾。

**打开文件**

这是使用 open()函数完成的。此功能不需要导入任何模块。

```
File_object = open(r"File_Name","Access_Mode")
```

该文件应该与 python 程序文件存在于同一个目录中，否则文件的完整地址应该写在文件名的位置。
注意: **r** 放在文件名之前，防止文件名字符串中的字符被视为特殊字符。例如，如果文件地址中有\u temp，则\u t 将被视为 tab 字符，并在无效地址中引发错误。r 使字符串原始，也就是说，它告诉字符串没有任何特殊字符。如果文件在同一个目录中并且地址没有被放置，r 可以被忽略。

```
# Open function to open the file "MyFile1.txt" 
# (same directory) in append mode and
file1 = open("MyFile.txt","a")

# store its reference in the variable file1 
# and "MyFile2.txt" in D:\Text in file2
file2 = open(r"D:\Text\MyFile2.txt","w+")
```

这里，文件 1 被创建为文件 1 的对象，文件 2 被创建为文件 2 的对象

**关闭文件**

close()函数关闭文件并释放该文件获取的内存空间。当不再需要该文件时，或者如果要以不同的文件模式打开该文件时，将使用它。

File_object.close()

```
# Opening and Closing a file "MyFile.txt"
# for object name file1.
file1 = open("MyFile.txt","a")
file1.close()
```

**写入文件**

有两种方法可以写入文件。

1.  **write() :** 将字符串 str1 插入文本文件中的一行。

    ```
    File_object.write(str1)
    ```

2.  **writeline():**对于字符串元素的列表，每个字符串都被插入到文本文件中。用于一次插入多个字符串。

    ```
    File_object.writelines(L) for L = [str1, str2, str3] 
    ```

**从文件中读取**

从文本文件中读取数据有三种方法。

1.  **read() :** 以字符串的形式返回读取的字节。读取 n 个字节，如果没有指定 n，读取整个文件。

    ```
    File_object.read([n])
    ```

2.  **readline() :** 读取文件的一行并以字符串形式返回。对于指定的 n，读取最多 n 个字节。但是，不会读取多行，即使 n 超过了该行的长度。

    ```
    File_object.readline([n])
    ```

3.  **readline():**读取所有行，并将它们作为列表中的字符串元素返回。

    ```
      File_object.readlines()
    ```

**注意:**“\ n”被视为两个字节的特殊字符

```
# Program to show various ways to read and
# write data in a file.
file1 = open("myfile.txt","w")
L = ["This is Delhi \n","This is Paris \n","This is London \n"] 

# \n is placed to indicate EOL (End of Line)
file1.write("Hello \n")
file1.writelines(L)
file1.close() #to change file access modes

file1 = open("myfile.txt","r+") 

print("Output of Read function is ")
print(file1.read())
print()

# seek(n) takes the file handle to the nth
# bite from the beginning.
file1.seek(0) 

print( "Output of Readline function is ")
print(file1.readline()) 
print()

file1.seek(0)

# To show difference between read and readline
print("Output of Read(9) function is ") 
print(file1.read(9))
print()

file1.seek(0)

print("Output of Readline(9) function is ") 
print(file1.readline(9))

file1.seek(0)
# readlines function
print("Output of Readlines function is ") 
print(file1.readlines()) 
print()
file1.close()
```

输出:

```
Output of Read function is 
Hello 
This is Delhi 
This is Paris 
This is London 

Output of Readline function is 
Hello 

Output of Read(9) function is 
Hello 
Th

Output of Readline(9) function is 
Hello 

Output of Readlines function is 
['Hello \n', 'This is Delhi \n', 'This is Paris \n', 'This is London \n']

```

**追加到文件中**

```
# Python program to illustrate
# Append vs write mode
file1 = open("myfile.txt","w")
L = ["This is Delhi \n","This is Paris \n","This is London \n"] 
file1.writelines(L)
file1.close()

# Append-adds at last
file1 = open("myfile.txt","a")#append mode
file1.write("Today \n")
file1.close()

file1 = open("myfile.txt","r")
print("Output of Readlines after appending") 
print(file1.readlines())
print()
file1.close()

# Write-Overwrites
file1 = open("myfile.txt","w")#write mode
file1.write("Tomorrow \n")
file1.close()

file1 = open("myfile.txt","r")
print("Output of Readlines after writing") 
print(file1.readlines())
print()
file1.close()
```

输出:

```
Output of Readlines after appending
['This is Delhi \n', 'This is Paris \n', 'This is London \n', 'Today \n']

Output of Readlines after writing
['Tomorrow \n']

```

**相关文章:**
[Python 中的文件对象](https://www.geeksforgeeks.org/file-objects-python/)

本文由 **Harshit Agrawal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。