# 显示两个字符串中不常见的字母的 Python 程序

> 原文:[https://www . geeksforgeeks . org/python-显示两个字符串中不常见的字母的程序/](https://www.geeksforgeeks.org/python-program-that-displays-letters-that-are-not-common-in-two-strings/)

给定两个字符串。写一个 Python 程序就是要找出这两个字符串中有哪些字母，而不是两个都有。

**例** :

```py
Input:
india
australia

Output:
s
t
r
n
d
u
l

```

**要执行的步骤:**

*   获取两个字符串输入，并将它们存储在不同的变量中。
*   将它们转换成集合，并在两个字符串中查找内部字母，但不要同时在两个字符串中查找。
*   将这些信件存放在不同的列表中。
*   打印那个列表。

**下面是实现。**

## 蟒 3

```py
# taking string inputs
string_1 = "hi"
string_2 = "virat"

# letters which are present in the two strings
# but not in both are found using the ‘^’ operator
e = list(set(string_1) ^ set(string_2))

# printing finale list
print("The letters are:")
for i in e:
    print(i)
```

**输出:**

```py
The letters are:
h
v
t
a
r

```