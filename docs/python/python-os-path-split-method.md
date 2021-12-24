# Python | os.path.split()方法

> 原文:[https://www.geeksforgeeks.org/python-os-path-split-method/](https://www.geeksforgeeks.org/python-os-path-split-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。 **os.path** 模块是 Python 中 **OS 模块**的子模块，用于常见的路径名操作。

Python 中的`***os.path.split()***`方法用于将路径名拆分成一对*头*和*尾*。在这里，*尾*是最后一个路径名组件，*头*是通向那个的一切。

例如，考虑以下路径名:

```
path name = '/home/User/Desktop/file.txt'

```

上例中路径名的*【file . txt】*组件为*尾**【home/User/Desktop/】*为头。尾部永远不会包含斜线；如果路径名以斜杠结束，尾部将为空，如果路径名中没有斜杠，头部将为空。

**例如:**

```
     path                             head                 tail
'/home/user/Desktop/file.txt'   '/home/user/Desktop/'   'file.txt'
'/home/user/Desktop/'           '/home/user/Desktop/'    {empty}
'file.txt'                           {empty}            'file.txt'

```

> ***语法:*** os.path.split(路径)
> 
> ***参数:***
> **路径**:表示文件系统路径的类路径对象。类似路径的对象是表示路径的*字符串*或*字节*对象。
> 
> ***返回类型:*** 这个方法返回一个元组，表示指定路径名的头尾。

**Code #1:** Use of os.path.split() method

```
# Python program to explain os.path.split() method 

# importing os module 
import os

# path
path = '/home/User/Desktop/file.txt'

# Split the path in 
# head and tail pair
head_tail = os.path.split(path)

# print head and tail
# of the specified path
print("Head of '% s:'" % path, head_tail[0])
print("Tail of '% s:'" % path, head_tail[1], "\n")

# path
path = '/home/User/Desktop/'

# Split the path in 
# head and tail pair
head_tail = os.path.split(path)

# print head and tail
# of the specified path
print("Head of '% s:'" % path, head_tail[0])
print("Tail of '% s:'" % path, head_tail[1], "\n")

# path
path = 'file.txt'

# Split the path in 
# head and tail pair
head_tail = os.path.split(path)

# print head and tail
# of the specified path
print("Head of '% s:'" % path, head_tail[0])
print("Tail of '% s:'" % path, head_tail[1])
```

**Output:**

```
Head of '/home/User/Desktop/file.txt': /home/User/Desktop
Tail of '/home/User/Desktop/file.txt': file.txt 

Head of '/home/User/Desktop/': /home/User/Desktop
Tail of '/home/User/Desktop/':  

Head of 'file.txt': 
Tail of 'file.txt': file.txt

```

**代码#2:** 如果路径为空

```
# Python program to explain os.path.split() method 

# importing os module 
import os

# path
path = ''

# Split the path in 
# head and tail pair
head_tail = os.path.split(path)

# print head and tail
# of the specified path
print("Head of '% s':" % path, head_tail[0])
print("Tail of '% s':" % path, head_tail[1])

# os.path.split() function
# will return empty
# head and tail if 
# specified path is empty
```

**Output:**

```
Head of '': 
Tail of '':

```

**参考:**T2】https://docs.python.org/3/library/os.path.html