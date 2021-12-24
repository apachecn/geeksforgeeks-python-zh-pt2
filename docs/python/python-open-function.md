# Python open()函数

> 原文:[https://www.geeksforgeeks.org/python-open-function/](https://www.geeksforgeeks.org/python-open-function/)

python open()函数用于打开()内部存储的文件。它将文件内容作为 python 对象返回。

> **语法:**打开(文件名，模式)
> 
> **参数:**
> 
> **file_name:** 这个参数顾名思义就是我们要打开的文件的名称。
> 
> **模式:**此参数是一个字符串，用于指定打开文件的模式。以下字符串可用于激活特定模式:
> 
> *   **“r”:**该字符串用于读取(只读)文件。如果没有提供参数，它将作为默认值传递，如果不存在这样的文件，它将返回一个错误。
> *   **“w”:**该字符串用于在文件上/上方写入。如果具有所提供名称的文件不存在，它会为您创建一个。
> *   **“a”:**该字符串用于向现有文件添加(追加)内容。如果不存在这样的文件，它会为您创建一个。
> *   **“x”:**该字符串用于创建特定文件。
> *   **“b”:**当用户想要以二进制模式处理文件时，使用该字符串。这通常用于处理图像文件。
> *   **“t”:**该字符串用于处理文本模式下的文件。默认情况下，open()函数使用文本模式。

### **示例 1:创建文本文件**

以下代码可用于创建文件。这里我们将创建一个名为“geeksforgeeks.txt”的文本文件。

## 蟒蛇 3

```py
created_file = open("geeksforgeeks.txt","x")

# Check the file
print(open("geeksforgeeks.txt","r").read() == False)
```

**输出:**

```py
True
```

### **例 2:读写文件**

这里我们将把下面的字符串写到刚刚创建的 *geeksforgeeks.txt* 文件中，并再次读取同一个文件。

> 极客 forgeeks 最适合 DSA

下面的代码可以用于同样的目的:

## 蟒蛇 3

```py
my_file = open("geeksforgeeks.txt", "w")
my_file.write("Geeksforgeeks is best for DSA")
my_file.close()

#let's read the contents of the file now
my_file = open("geeksforgeeks.txt","r")
print(my_file.read())
```

**输出:**

```py
Geeksforgeeks is best for DSA
```

### **示例 3:将内容追加到文件中**

在这里，我们将把下面的文本附加到 geeksforgeeks.txt 文件中，并再次读取相同的内容:

## 蟒蛇 3

```py
my_file = open("geeksforgeeks.txt","a")
my_file.write("..>>Visit geeksforgeeks.org for more!!<<..")
my_file.close()

# reading the file
my_file = open("geeksforgeeks.txt","r")
print(my_file.read())
```

**输出:**

> 极客 forgeeks 最适合 DSA..> >访问 geeksforgeeks.org 了解更多信息！！<<../>

**注意:**“w”和“r”的区别在于一个覆盖现有内容，而后者将内容添加到现有文件中，保持内容不变。