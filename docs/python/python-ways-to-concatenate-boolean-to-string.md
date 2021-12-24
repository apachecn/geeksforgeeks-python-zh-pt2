# Python |将布尔值连接到字符串的方法

> 原文:[https://www . geesforgeks . org/python-连接方式-布尔到字符串/](https://www.geeksforgeeks.org/python-ways-to-concatenate-boolean-to-string/)

给定一个字符串和一个布尔值，编写一个 Python 程序将字符串和布尔值连接起来，下面给出了几个解决这个任务的方法。

**方法一:使用`format()`**

```py
# Python code to demonstrate 
# to concatenate boolean value
# with string

# Initialising string and boolean value
ini_string = "Facts are"
value = True

# Concatenate using format
res = str(ini_string+" {}").format(value)

# Printing resultant string
print ("Resultant String : ", res)
```

**输出:**

```py
Resultant String :  Facts are True

```