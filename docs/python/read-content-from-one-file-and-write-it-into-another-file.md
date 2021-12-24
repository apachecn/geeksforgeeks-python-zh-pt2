# 从一个文件中读取内容并写入另一个文件

> 原文:[https://www . geesforgeks . org/从一个文件读取内容并将其写入另一个文件/](https://www.geeksforgeeks.org/read-content-from-one-file-and-write-it-into-another-file/)

**先决条件:**[Python 文本文件读写](https://www.geeksforgeeks.org/reading-writing-text-files-python/)

Python 提供了创建、写入和读取文件的内置功能。python 中可以处理两种类型的文件，普通文本文件和二进制文件(用二进制语言编写，0 和 1)。

*   **文本文件:**在这种类型的文件中，每一行文本都以一个名为 EOL(行尾)的特殊字符结束，默认情况下，这是 python 中的新行字符(' \n ')。
*   **二进制文件:**在这种类型的文件中，一行没有终止符，数据转换成机器可理解的二进制语言后存储。

在本文中，我们将学习如何从一个文件中读取内容并将其写入另一个文件。我们在**上操作。Python 中的 txt 文件**。

**进场:**

有两种方法可以做到这一点:

*   使用循环从一个文件读取内容并将内容复制到另一个文件。
*   使用文件方法从一个文件读取内容并将内容复制到另一个文件。

**输入文件:**

![](img/9983ca302cc09d43c66e367c4e899c3b.png)

### **方法 1:使用循环**

**进场:**

*   以读取模式打开输入文件。
*   以写入模式打开输出文件。
*   从输入文件中读取行，并将其写入输出文件。

**以下是上述方法的实现:**

## 蟒蛇 3

```py
# Taking "gfg input file.txt" as input file
# in reading mode
with open("gfg input file.txt", "r") as input:

    # Creating "gfg output file.txt" as output
    # file in write mode
    with open("gfg output file.txt", "w") as output:

        # Writing each line from input file to
        # output file using loop
        for line in input:
            output.write(line)
```

**输出:**

![](img/49ac404201f264fda6c8ba19979f7a78.png)

### 方法 2:使用文件方法

**进场:**

*   以写入模式创建/打开输出文件。
*   以读取模式打开输入文件
*   从输入文件中读取每一行，并将其写入输出文件。
*   关闭输出文件。

**以下是上述方法的实现:**

## 蟒蛇 3

```py
# Creating an output file in writing mode
output_file = open("gfg output file.txt", "w")

# Opening input file and scanning each line
# from input file and writing in output file
with open("gfg input file.txt", "r") as scan:
    output_file.write(scan.read())

# Closing the output file
output_file.close()
```

**输出:**

![](img/49ac404201f264fda6c8ba19979f7a78.png)