# 在 Python 中检索和更新搁置中包含的数据

> 原文:[https://www . geesforgeks . org/检索和更新数据-包含在 python 中的搁置中/](https://www.geeksforgeeks.org/retrieving-and-updating-data-contained-in-shelve-in-python/)

在 Python 框架中，您可以随机访问密钥。为了在 python 框架中随机访问密钥，我们使用`open()`函数。这个函数的工作原理很像文件处理中的文件 [open()](https://www.geeksforgeeks.org/file-handling-python/) 函数。使用 Python 搁置打开文件的语法

```py
shelve.open(filename, flag='c' , writeback=True)

```

为了在 Python 中随机访问搁置中的密钥，我们必须采取三个步骤:

*   存储 Python 搁置数据
*   正在检索 Python 搁置数据
*   更新 Python 搁置数据

**存储 python 搁置数据:**
为了存储 Python 搁置数据，我们必须创建一个充满数据集的文件，并用`open()`函数打开它们这个函数打开一个我们已经创建的文件。

```py
# At first, we have to import the 'Shelve' module.
import shelve

# In this step, we create a shelf file.
shfile = shelve.open("shelf_file")

# we create a data object which in this case is a book_list.
my_book_list =['bared_to_you', 'The_fault_in_our_stars',
              'The_boy_who_never_let_her_go']

# we are assigning a dictionary key to the list 
# which we will want to retrieve
shfile['book_list']= my_book_list

# now, we simply close the shelf file.
shfile.close()
```

**检索 Python 搁置数据:**
存储搁置数据后，我们必须从文件中检索一些数据，以便像在列表和许多其他数据类型中一样使用索引运算符[]。

```py
# At first, we import the 'Shelve' module.
import shelve

# In this step, we create a shelf file.
var = shelve.open("shelf_file")

# Now, this 'var' variable points to all the 
# data objects in the file 'shelf_file'.
print(var['book_list'])

# now, we simply close the file 'shelf_file'.
var.close()
```

**输出:**

```py
['bared_to_you', 'The_fault_in_our_stars', 'The_boy_who_never_let_her_go']

```

**注意:**输出将取决于您在文件中存储了什么

**更新 python 搁置数据:**
为了更新 Python 搁置数据，我们使用 append()函数，或者我们可以像在列表和其他数据类型中一样轻松更新。为了使我们的改变永久化，我们使用`sync()`功能。

```py
# At first, we have to import the 'Shelve' module.
import shelve

# In this step, we create a shelf file.
var = shelve.open("shelf_file", writeback = True)

# inputting total values we want to add 
# to the already existing list in shelf_file.
val1 = int(input("Enter the number of values "))

for x in range(val1):

   val = input("\n Enter the value\t")

   var['book_list'].append(val)

# Now, this 'var' variable will help in printing
# the data objects in the file 'shelf_file'.
print(var['book_list'])

# to make our changes permanent, we use 
# synchronize function.
var.sync()

# now, we simply close the file 'shelf_file'.
var.close()
```

**输入:**

```py
 Enter the number of values 5
 Enter the value    Who moved my cheese?
 Enter the value    Our impossible love
 Enter the value    Bourne Identity
 Enter the value    Hush
 Enter the value    Knock-Knock
```

**输出:**

```py
['bared_to_you', 'The_fault_in_our_stars', 'The_boy_who_never_let_her_go',
 'Who moved my cheese?', 'Our impossible love', 'Bourne Identity', 
 'Hush', 'Knock-Knock']
```

**注意:**输入和输出取决于用户，用户可以根据用户输入更新文件中用户想要的任何内容，输出将会改变。