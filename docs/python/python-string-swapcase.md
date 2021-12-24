# Python 字符串| swapcase()

> 原文:[https://www.geeksforgeeks.org/python-string-swapcase/](https://www.geeksforgeeks.org/python-string-swapcase/)

string swapcase()方法将给定字符串的所有大写字符转换为小写字符，反之亦然，并返回该字符串。

**语法:**

> string_name.swapcase()
> 这里 string_name 是要交换大小写的字符串。

**参数:**swap case()方法不取任何参数。

**返回值:**

> swapcase()方法返回一个包含所有已更改案例的字符串。

下面是 swapcase()方法的 Python 实现

```
# Python program to demonstrate the use of
# swapcase() method  

string = "gEEksFORgeeks"

# prints after swappong all cases
print(string.swapcase())   

string = "striver" 
print(string.swapcase())  
```

输出:

```
GeeKSforGEEKS
STRIVER

```