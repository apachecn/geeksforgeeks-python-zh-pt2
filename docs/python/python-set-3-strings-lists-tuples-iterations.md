# Python |集合 3(字符串、列表、元组、迭代)

> 原文:[https://www . geesforgeks . org/python-set-3-strings-list-元组-iterations/](https://www.geeksforgeeks.org/python-set-3-strings-lists-tuples-iterations/)

在[之前的](https://www.geeksforgeeks.org/python-set-2-variables-expressions-conditions-and-functions/)文章中，我们读到了 Python 的基础知识。现在，我们继续一些更多的 python 概念。

**Python 中的字符串**
字符串是一个字符序列。它可以用 python 通过双引号来声明。字符串是不可变的，即不能更改。

## 计算机编程语言

```py
# Assigning string to a variable
a = "This is a string"
print (a)
```

**Python 中的列表**
列表是 Python 中最强大的工具之一。它们就像用其他语言声明的数组一样。但最强大的是，列表不必总是同质的。单个列表可以包含字符串、整数以及对象。列表也可以用于实现堆栈和队列。列表是可变的，也就是说，一旦声明，它们就可以改变。

## 计算机编程语言

```py
# Declaring a list
L = [1, "a" , "string" , 1+2]
print L
L.append(6)
print L
L.pop()
print L
print L[1]
```

输出结果是:

```py
[1, 'a', 'string', 3]
[1, 'a', 'string', 3, 6]
[1, 'a', 'string', 3]
a
```

**Python 中的元组**
元组是一系列不可变的 Python 对象。元组就像列表一样，只是元组一旦声明就不能更改。元组通常比列表快。

## 计算机编程语言

```py
tup = (1, "a", "string", 1+2)
print(tup)
print(tup[1])
```

输出结果是:

```py
(1, 'a', 'string', 3)
a
```

**Python 中的迭代**
Python 中的迭代或循环可以通过“for”和“while”循环来执行。除了迭代特定的条件，我们还可以迭代字符串、列表和元组。
示例 1:条件的 while 循环迭代

## 计算机编程语言

```py
i = 1
while (i < 10):
    print(i)
    i += 1
```

输出结果是:

```py
1
2
3
4
5
6
7
8
9 
```

示例 2:通过对字符串执行 for 循环进行迭代

## 计算机编程语言

```py
s = "Hello World"
for i in s :
    print (i)
```

输出结果是:

```py
H
e
l
l
o

W
o
r
l
d
```

示例 3:通过列表上的 for 循环进行迭代

## 计算机编程语言

```py
L = [1, 4, 5, 7, 8, 9]
for  i in L:
    print (i)
```

输出结果是:

```py
1
4
5
7
8
9
```

示例 4:范围的 for 循环迭代

## 计算机编程语言

```py
for i in range(0, 10):
    print (i)
```

输出结果是:

```py
0
1
2
3
4
5
6
7
8
9 
```

https://www.youtube.com/watch?v=pCoB45

*   下一篇文章–[Python:字典和关键词](https://www.geeksforgeeks.org/python-set-4-dictionary-keywords-python/)
*   [Python 中数据类型的测验](https://www.geeksforgeeks.org/data-type-gq/)