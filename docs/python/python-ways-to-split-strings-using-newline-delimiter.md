# Python |使用换行符拆分字符串的方法

> 原文:[https://www . geesforgeks . org/python-使用换行符拆分字符串的方法/](https://www.geeksforgeeks.org/python-ways-to-split-strings-using-newline-delimiter/)

给定一个字符串，编写一个 Python 程序根据换行符拆分字符串。下面给出了一些解决给定任务的方法。

**方法#1:使用`splitlines()`**

```py
# Python code to demonstrate 
# to split strings
# on newline delimiter

# Initialising string
ini_str = 'Geeks\nFor\nGeeks\n'

# Printing Initial string
print ("Initial String", ini_str)

# Splitting on newline delimiter
res_list = ini_str.splitlines()

# Printing result
print("Resultant prefix", str(res_list))
```

**Output:**

```py
Initial String Geeks
For
Geeks

Resultant prefix ['Geeks', 'For', 'Geeks']

```

**方法 2:使用`split()`方法**

```py
# Python code to demonstrate 
# to split strings
# on newline delimiter

# Initialising string
ini_str = 'Geeks\nFor\nGeeks\n'

# Printing Initial string
print ("Initial String", ini_str)

# Splitting on newline delimiter
res_list = (ini_str.rstrip().split('\n'))

# Printing result
print("Resultant prefix", str(res_list))
```

**Output:**

```py
Initial String Geeks
For
Geeks

Resultant prefix ['Geeks', 'For', 'Geeks']

```