# 为什么 Python 字符串是不可变的？

> 原文:[https://www . geesforgeks . org/why-are-python-strings-不可变/](https://www.geeksforgeeks.org/why-are-python-strings-immutable/)

一篇一成不变的文章暗指一件物品一旦制成，它的价值一辈子都不会改变。尝试执行附带的代码:

## python 3

```py
name_1 = "Aarun" 

name_1[0] = 'T' 
```

当您需要更改字符串的内容时，您会收到一条错误消息。

```py
Traceback (latest call last):  
Record "/home/ca508dc8fa5ad71190ca982b0e3493a8.py", line 2, in <module>  
name_1[0] = 'T'  
TypeError: 'str' object doesn't uphold thing task  
```

**排列**

一种可能的安排是制造另一个具有重要变化的弦物体:

## 

```py
name_1 = "Aarun"

name_2 = "T" + name_1[1:]

print("name_1 = ", name_1, "and name_2 = ", name_2)
```

**输出:**

```py
name_1 =  Aarun and name_2 =  Tarun
```

要注意它们是各种各样的字符串，请使用 id()检查工作:

## python 3

```py
name_1 = "Aarun"
name_2 = "T" + name_1[1:]

print("id of name_1 = ", id(name_1))
print("id of name_2 = ", id(name_2))
```

**输出:**

```py
id of name_1 =  2342565667256
id of name_2 =  2342565669888
```

要了解更多关于字符串持久性的想法，请思考随附的代码:

## python 3

```py
name_1 = "Aarun"
name_2 = "Aarun"

print("id of name_1 = ", id(name_1))
print("id of name_2 = ", id(name_2))
```

在执行上述代码行时，您会发现 name_1 和 name_2 对象的 id 是等价的，这两个对象都暗指字符串“Aarun”。

要进一步挖掘，请执行附带的断言:

## 

```py
name_1 = "Aarun"
print("id of name_1 = ", id(name_1))

name_1 = "Tarun"
print("id of name_1  with new value = ", id(name_1))
```

**输出:**

```py
id of name_1 =  2342565667256
id of name_1  with new value =  2342565668656
```

从上面的模型中可以发现，当一个字符串引用用另一个值重新初始化时，它正在生成另一篇文章，而不是覆盖过去的值。

**注意:**在 Python 中，字符串是不变的，所以软件工程师无法调整项目的实质。这样可以避免多余的 bug。