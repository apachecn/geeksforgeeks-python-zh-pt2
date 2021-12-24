# Python seek()函数

> 原文:[https://www.geeksforgeeks.org/python-seek-function/](https://www.geeksforgeeks.org/python-seek-function/)

文件处理的概念用于保存运行程序后生成的数据或信息。像 C、C++、Java 等其他编程语言一样，Python 也支持[文件处理](https://www.geeksforgeeks.org/file-handling-python/)。

> 请参考下面的文章来了解文件处理的基础知识。
> 
> *   [Python 中的文件处理。](https://www.geeksforgeeks.org/file-handling-python/)
>     
> *   [用 Python 读写文件](https://www.geeksforgeeks.org/reading-writing-text-files-python/)

#### seek()方法

在 Python 中，seek()函数用于**将文件句柄**的位置更改为给定的特定位置。文件句柄就像一个光标，它定义了从哪里读取或写入文件中的数据。

> **语法:** f.seek(offset，from_what)，其中 f 是文件指针
> **参数:**
> **Offset:** 向前移动的位置数
> **from_what:** 它定义了参考点。
> **返回:**不返回任何值

参考点由 **from_what** 参数选择。它接受三种价值观:

*   **0:** 设置文件开头的参考点

*   **1:** 设置当前文件位置的参考点

*   **2:** 设置文件末端的参考点

默认情况下，from_what 参数设置为 0。
**注意:**除了偏移量等于 0 时，在文本模式下无法设置文件当前位置/结尾的参考点。
**示例 1:** 假设我们必须读取一个名为“GfG.txt”的文件，该文件包含以下文本:

```py
"Code is like humor. When you have to explain it, it’s bad."    
```

## 蟒蛇 3

```py
# Python program to demonstrate
# seek() method

# Opening "GfG.txt" text file
f = open("GfG.txt", "r")

# Second parameter is by default 0
# sets Reference point to twentieth
# index position from the beginning
f.seek(20)

# prints current position
print(f.tell())

print(f.readline())
f.close()
```

**Output:**

```py
20
When you have to explain it, it’s bad.
```

**例 2:** 负偏移量 Seek()函数仅在文件以二进制模式打开时有效。让我们假设二进制文件包含以下文本。

```py
b'Code is like humor. When you have to explain it, its bad.'
```

## 蟒蛇 3

```py
# Python code to demonstrate
# use of seek() function

# Opening "GfG.txt" text file
# in binary mode
f = open("data.txt", "rb")

# sets Reference point to tenth
# position to the left from end
f.seek(-10, 2)

# prints current position
print(f.tell())

# Converting binary to string and
# printing
print(f.readline().decode('utf-8'))

f.close()
```

**Output:** 

```py
47
, its bad.
```