# Python 为什么叫动态类型化？

> 原文:[https://www . geesforgeks . org/why-python-is-call-dynamic-type/](https://www.geeksforgeeks.org/why-python-is-called-dynamically-typed/)

Python 变量赋值不同于一些流行的语言，如 c、c++和 java。没有变量的声明，只有赋值语句。

让我们看看为什么？
当我们**用 C 语言或类似语言声明一个变量**时，会留出一个内存区域，用于保存该变量的**数据类型**所允许的值。分配的内存将按照数据类型的建议进行解释。如果是整数变量，分配的内存将被读取为整数，以此类推。当我们用某个值分配或初始化它时，该值将被存储在该内存位置。编译时，将检查初始值或赋值。所以我们不能混合类型。示例:不允许将字符串值初始化为 int 变量，并且程序不会编译。

但是 Python 是一种**动态类型的**语言。在代码运行之前，它不知道变量的类型。所以声明没有用。它的作用是，将该值存储在某个内存位置，然后将该变量名绑定到该内存容器。并通过该变量名访问容器的内容。所以数据类型不重要。因为它将在运行时知道值的类型。

```py
# This will store 6 in the memory and binds the
# name x to it. After it runs, type of x will
# be int.
x = 6   

print(type(x))

# This will store 'hello' at some location int 
# the memory and binds name x to it. After it
# runs type of x will be str.
x = 'hello' 

print(type(x))
```

**Output:**

```py
<class 'int'>
<class 'str'>

```