# Python |将字符串填充到固定长度

> 原文:[https://www . geesforgeks . org/python-padding-a-string-up-fixed-length/](https://www.geeksforgeeks.org/python-padding-a-string-upto-fixed-length/)

给定一个字符串，任务是用空格将字符串填充到给定的特定长度。让我们讨论几个解决给定任务的方法。

**方法一:使用`ljust()`**

```
# Python code to demonstrate
# pad spaces in string
# upto fixed length

# initialising string
ini_string = "123abcjw"
padding_size = 15

# printing string and its length
print ("initial string : ", ini_string, len(ini_string))

# code to pad spaces in string
res = ini_string.ljust(padding_size)

# printing string and its length
print ("final string : ", res, len(res))
```

**输出:**

```
initial string :  123abcjw 8
final string :  123abcjw        15

```