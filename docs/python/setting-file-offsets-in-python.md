# 在 Python 中设置文件偏移量

> 原文:[https://www . geesforgeks . org/setting-file-offset-in-python/](https://www.geeksforgeeks.org/setting-file-offsets-in-python/)

**先决条件:** [**求()**](https://www.geeksforgeeks.org/python-seek-function/)**[**告()**](https://www.geeksforgeeks.org/python-tell-function/)**

**Python 使得用最少的代码创建/编辑文本文件变得非常容易。要访问文本文件，我们必须创建一个文件句柄，在文本文件的开头做一个偏移。简单来说，**偏移量**就是文件内读/写指针的位置。稍后将使用 offset 在文本文件中执行操作，具体取决于给定的权限，如读、写等。**

****开始之前让我们回忆一下文件处理的一些基本方法:****

*   ****seek()** :在 Python 中，seek()函数用于**将文件句柄**的位置更改到给定的特定位置。文件句柄就像一个光标，它定义了数据在文件中的读取或写入位置。**

> *****语法:** f.seek(offset，from_what)，其中 f 是文件指针***
> 
> *****参数:***
> ***偏移量:**向前移动的位置数*
> ***from _ what:**它定义了参考点。***

*   ****tell():** [**访问模式**](https://www.geeksforgeeks.org/reading-writing-text-files-python/) 控制打开文件中可能的操作类型。它指的是文件打开后将如何使用。这些模式还定义了文件中**文件句柄**的位置。**文件句柄**就像一个光标，它定义了从哪里读取或写入文件中的数据。有时知道文件句柄的位置对我们来说变得很重要。方法可以用来获取文件句柄的位置。tell()方法返回文件对象的当前位置。此方法不接受任何参数，并返回一个整数值。最初，文件指针指向文件的开头(如果没有在追加模式下打开)。所以，tell()的初始值为零。**

> ****语法:** f.tell()**
> 
> ****Return:** 该方法返回文件读/写指针在文件内的当前位置。**

### ****让我们通过分步实现来理解这一点:****

****步骤 1:** 创建文本文件。**

**让我们创建一个包含多封电子邮件的文本文件“emails.txt”来演示 offset 的工作原理:**

## **蟒蛇 3**

```
# WRITING OPERATIONS
# creates a file named emails.txt
fhand = open("emails.txt", "w")

# this enters the values into the file
fhand.write('''stephen.marquard@uct.ac.za
stephen.marquard@uct.ac.za
louis@media.berkeley.edu
louis@media.berkeley.edu
louis@media.berkeley.edu
louis@media.berkeley.edu
ray@media.berkeley.edu
ray@media.berkeley.edu
cwen@iupui.edu
cwen@iupui.edu
cwen@iupui.edu
cwen@iupui.edu
cwen@iupui.edu
cwen@iupui.edu''')

# closing the file
fhand.close()
```

**这会创建一个文件“emails.txt”并用电子邮件填充它。**

****步骤 2:** 让我们检查一下刚刚通过编写以下代码创建的 emails.txt 文件的内容:**

## **蟒蛇 3**

```
# opening the file with reading permissions
fhand = open("emails.txt", "r")

# print the content of the whole file
print(fhand.read())

# close the file
fhand.close()
```