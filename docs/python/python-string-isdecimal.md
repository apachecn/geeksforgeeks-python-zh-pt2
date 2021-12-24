# Python 字符串| isdiction()

> 原文:[https://www.geeksforgeeks.org/python-string-isdecimal/](https://www.geeksforgeeks.org/python-string-isdecimal/)

**isdecimal()-** 这是 Python 中的一个函数，如果字符串中的所有字符都是十进制的，则返回 true。如果所有字符都不是十进制，则返回 false。

**语法:**

> string_name . is descimal()
> 这里 string _ name 是要检查其字符的字符串

**参数:**该方法不取任何参数。

**返回值:**

> true–所有字符都是十进制
> False–一个或多个字符不是十进制。

*下面是 isdecimal()方法的 Python3 实现:*

```
# Python3 program to demonstrate the use
# of isdecimal() 

s = "12345"
print(s.isdecimal())

# contains alphabets
s = "12geeks34"
print(s.isdecimal())

# contains numbers and spaces
s = "12 34"
print(s.isdecimal())
```

输出:

```
True
False
False

```