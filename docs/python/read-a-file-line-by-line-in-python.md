# 在 Python 中逐行读取文件

> 原文:[https://www . geesforgeks . org/python 中逐行读取文件/](https://www.geeksforgeeks.org/read-a-file-line-by-line-in-python/)

**先决条件:**

*   [访问模式](https://www.geeksforgeeks.org/reading-writing-text-files-python/)
*   [打开文件](https://www.geeksforgeeks.org/reading-writing-text-files-python/)
*   [关闭文件](https://www.geeksforgeeks.org/reading-writing-text-files-python/)

Python 提供了创建、写入和读取文件的内置功能。python 中可以处理两种类型的文件，普通文本文件和二进制文件(用二进制语言编写，0 和 1)。在本文中，我们将学习从文件中一行一行地阅读。

## 逐行阅读

#### 使用读取线()

readlines()用于一次读取所有行，然后将它们作为列表中的每一行字符串元素返回。这个函数可以用于小文件，因为它将整个文件内容读入内存，然后将其拆分成单独的行。我们可以遍历列表，并使用 strip()函数删除换行符。

**示例:**

## 蟒蛇 3

```py
# Python code to
# demonstrate readlines()

L = ["Geeks\n", "for\n", "Geeks\n"]

# writing to file
file1 = open('myfile.txt', 'w')
file1.writelines(L)
file1.close()

# Using readlines()
file1 = open('myfile.txt', 'r')
Lines = file1.readlines()

count = 0
# Strips the newline character
for line in Lines:
    count += 1
    print("Line{}: {}".format(count, line.strip()))
```

**输出:**

```py
Line1: Geeks
Line2: for
Line3: Geeks
```

#### 使用 readline()

readline()函数读取文件的一行，并以字符串的形式返回。它采用参数 n，该参数指定将被读取的最大字节数。但是，不会读取多行，即使 n 超过了该行的长度。当读取一个大文件时，它将是高效的，因为它不是一次获取所有的数据，而是一行一行地获取。readline()返回文件的下一行，最后包含一个换行符。此外，如果到达文件的末尾，它将返回一个空字符串。

**示例:**

## 蟒蛇 3

```py
# Python program to
# demonstrate readline()

L = ["Geeks\n", "for\n", "Geeks\n"]

# Writing to a file
file1 = open('myfile.txt', 'w')
file1.writelines((L))
file1.close()

# Using readline()
file1 = open('myfile.txt', 'r')
count = 0

while True:
    count += 1

    # Get next line from file
    line = file1.readline()

    # if line is empty
    # end of file is reached
    if not line:
        break
    print("Line{}: {}".format(count, line.strip()))

file1.close()
```

**输出:**

```py
Line1 Geeks
Line2 for
Line3 Geeks
```

#### 用于循环

打开文件时，open()函数返回一个可迭代对象。逐行读取文件的最后一种方式包括在 for 循环中迭代文件对象。我们这样做是利用了一个内置的 Python 函数，该函数允许我们在使用可迭代对象的同时，使用 for 循环隐式迭代文件对象。这种方法需要更少的代码行，这始终是值得遵循的最佳实践。

**示例:**

## 蟒蛇 3

```py
# Python program to
# demonstrate reading files
# using for loop

L = ["Geeks\n", "for\n", "Geeks\n"]

# Writing to file
file1 = open('myfile.txt', 'w')
file1.writelines(L)
file1.close()

# Opening file
file1 = open('myfile.txt', 'r')
count = 0

# Using for loop
print("Using for loop")
for line in file1:
    count += 1
    print("Line{}: {}".format(count, line.strip()))

# Closing files
file1.close()
```

**输出:**

```py
Using for loop
Line1: Geeks
Line2: for
Line3: Geeks
```

## 带语句

在上述方法中，每次打开文件都需要显式关闭。如果忘记关闭文件，可能会在代码中引入几个错误，即文件中的许多更改只有在文件正确关闭后才会生效。为了防止这种情况，可以使用 with 语句。Python 中的 With 语句用于异常处理，以使代码更加清晰易读。它简化了文件流等公共资源的管理。观察下面的代码示例，了解如何使用 with 语句使代码更干净。与语句一起使用时，不需要调用 file.close()。with 语句本身确保了资源的正确获取和释放。

**示例:**

## 蟒蛇 3

```py
# Python program to
# demonstrate with
# statement

L = ["Geeks\n", "for\n", "Geeks\n"]

# Writing to file
with open("myfile.txt", "w") as fp:
    fp.writelines(L)

# using readlines()
count = 0
print("Using readlines()")

with open("myfile.txt") as fp:
    Lines = fp.readlines()
    for line in Lines:
        count += 1
        print("Line{}: {}".format(count, line.strip()))

# Using readline()
count = 0
print("\nUsing readline()")

with open("myfile.txt") as fp:
    while True:
        count += 1
        line = fp.readline()

        if not line:
            break
        print("Line{}: {}".format(count, line.strip()))

# Using for loop
count = 0
print("\nUsing for loop")

with open("myfile.txt") as fp:
    for line in fp:
        count += 1
        print("Line{}: {}".format(count, line.strip()))
```

**输出:**

```py
Using readlines()
Line1: Geeks
Line2: for
Line3: Geeks

Using readline()
Line1: Geeks
Line2: for
Line3: Geeks

Using for loop
Line1: Geeks
Line2: for
Line3: Geeks
```