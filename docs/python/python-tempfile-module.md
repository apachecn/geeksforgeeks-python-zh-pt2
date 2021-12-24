# Python 时间文件模块

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-tempfile-module/

**Tempfile** 是在一种情况下使用的 Python 模块，在这种情况下，我们需要读取多个文件，更改或访问文件中的数据，并根据处理数据的结果给出输出文件。程序执行期间产生的每个输出文件在程序完成后都不再需要。在这种情况下，出现了一个问题，即创建了许多输出文件，这使得文件系统中堆满了不需要的文件，每次程序运行时都需要删除这些文件。

在这种情况下，临时文件被用来创建临时文件，这样下次当我们的程序处理完它们时，我们就不必再找到 delete 了

## 处理临时文件

临时文件也可用于保护敏感数据。该模块包含许多创建临时文件和文件夹的功能，并且可以轻松访问。

### 创建临时文件

假设您的应用程序需要一个临时文件在程序中使用，即它将创建一个文件，使用它来存储一些数据，然后在使用后删除它。为了实现这一点，我们可以使用 TemporaryFile()函数。

*   首先，我们必须导入 tempfile，然后使用 TemporaryFile()函数创建文件。
*   默认情况下，文件以 w+b(读取和写入打开的文件)模式打开。
*   该函数在临时目录中创建一个临时文件，并返回一个文件对象
*   文件对象一关闭，temp 文件夹中的文件条目就会被删除

**代码:**

## 蟒蛇 3

```
import tempfile

temp = tempfile.TemporaryFile()
print('temp:',temp)
print('temp.name:', temp.name)
temp.close()
```

**输出:**

```
temp: <_io.BufferedRandom name=6>
temp.name: 6
```

### 将纯文本读写到临时文件中

类似于从文件中读取或写入，我们也可以使用相同类型的函数调用来从临时文件中执行此操作！！

*   创建一个临时文件，并向其中写入一些数据
*   写入后，您必须使用 seek()倒带文件句柄，以便从中读回数据。
*   回到开头，从文件中读取数据
*   关闭文件，它将被删除

**例 1:**

## 蟒蛇 3

```
import tempfile

temp = tempfile.TemporaryFile()

try:
    temp.write(b'Hello world!')
    temp.seek(0)

    print(temp.read())
finally:
    temp.close()
```

**输出:**

```
b'Hello world!'
```

**例 2:**

## 蟒蛇 3

```
import tempfile

f = tempfile.TemporaryFile()

try:
  f.write(b'Welcome to geeksforgeeks')
  f.seek(0)
  data=f.read()
  print(data)
finally:
  f.close()
```

**输出:**

```
b'Welcome to geeksforgeeks'
```

### **创建命名的临时文件**

如果您的应用程序跨越多个进程，甚至主机，命名文件是在应用程序各部分之间传递文件的最简单方式。函数的作用是:创建一个名为的文件，该文件可以从 name 属性中访问。

*   首先导入 tempfile，然后使用 NamedTemporaryFile()函数创建文件。
*   NamedTemporaryFile 返回一个类似文件的对象，可以用作临时存储，但是，与 TemporaryFile 相反，使用 NamedTemporaryFile 创建的文件保证在其生存期内具有可见的名称。
*   文件一关闭，临时文件就会被销毁，NamedTemporaryFile 支持删除标志，默认为 True

**例 1:**

## 蟒蛇 3

```
import tempfile

print("Creating a named temporary file..")
temp = tempfile.NamedTemporaryFile()

print("Created file is:", temp)
print("Name of the file is:", temp.name)
temp.close()
```

**输出:**

```
Creating a named temporary file..
Created file is: <tempfile._TemporaryFileWrapper object at 0x7ff135ed1710>
Name of the file is: /tmp/tmpg8efl258
```

**例 2:**

## 蟒蛇 3

```
import tempfile

fo = tempfile.NamedTemporaryFile()
print(fo.name)

fo.close()
```

**输出:**

```
/tmp/tmp6nxmoagy
```

### 提供文件名后缀和前缀

有时我们需要给临时文件的名称添加前缀或后缀。它将帮助我们识别程序创建的所有临时文件

*   我们可以使用参数“后缀”和“前缀”为命名的临时文件的名称添加后缀或前缀。
*   使用上面定义的同一个函数。在调用这个函数时，我们唯一需要添加的是两个额外的参数:后缀和前缀
*   因此，如果我们将两个额外的参数后缀和前缀传递给 NamedTemporaryFile()函数，它将自动在文件名的开头和结尾添加它们

**例 1:**

## 蟒蛇 3

```
import tempfile

temp = tempfile.NamedTemporaryFile(prefix="demoPrefix_",
                                   suffix="_demoSuffix")

print("Created file is:", temp)
print("Name of the file is:", temp.name)
temp.close()
```

**输出:**

```
Created file is: <tempfile._TemporaryFileWrapper object at 0x7fbf5d39b6d8>
Name of the file is: /tmp/demoPrefix_t_inxb7v_demoSuffix
```

**例 2:**

## 蟒蛇 3

```
import tempfile

temp=tempfile.NamedTemporaryFile(suffix='_greeks',
                                 prefix='forgreeks_')
print(temp.name)
```

**输出:**

```
/tmp/forgreeks_4sigabye_greeks
```