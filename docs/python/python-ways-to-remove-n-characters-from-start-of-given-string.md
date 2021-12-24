# Python |从给定字符串开头删除 n 个字符的方法

> 原文:[https://www . geeksforgeeks . org/python-从给定字符串开头删除 n 个字符的方法/](https://www.geeksforgeeks.org/python-ways-to-remove-n-characters-from-start-of-given-string/)

给定一个字符串和一个数字“n”，任务是从字符串的开头删除一个长度为“n”的字符串。让我们来看几个解决给定任务的方法。

**方法#1:使用天真法**

```py
# Python3 code to demonstrate 
# how to remove 'n' characters from starting
# of a string

# Initialising string
ini_string1 = 'garg_akshat'

# Initialising number of characters to be removed
n = 5

# Printing initial string
print ("Initial String", ini_string1)

# Removing n characters from string using 
# Naive method
res = ''
for i in range(0, len(ini_string1)):
    if i>= n:
        res = res + ini_string1[i]

# Printing resultant string
print ("Resultant String", res)
```

**Output:**

```py
Initial String garg_akshat
Resultant String akshat

```

**方法 2:使用`replace()`**

```py
# Python3 code to demonstrate 
# how to remove 'n' characters from starting
# of a string

# Initialising string
ini_string1 = 'garg_akshat'

# Initialising number of characters to be removed
n = 5

# Printing initial string
print ("Initial String", ini_string1)

# Removing n characters from string using 
# replace() function
res = ini_string1.replace(ini_string1[:5], '', 1)

# Printing resultant string
print ("Resultant String", res)
```

**Output:**

```py
Initial String garg_akshat
Resultant String akshat

```

**方法三:切弦**

```py
# Python3 code to demonstrate 
# how to remove 'n' characters from starting
# of a string

# Initialising string
ini_string1 = 'gargakshat123'

# Initialising number of characters to be removed
n = 5

# Printing initial string
print ("Initial String", ini_string1)

# Removing n characters from a string
# This argument count length from zero 
# So length to be stripped is passed n-1
res = ini_string1[4:]

# Printing resultant string
print ("Resultant String", res)

```

**Output:**

```py
Initial String gargakshat123
Resultant String akshat123

```