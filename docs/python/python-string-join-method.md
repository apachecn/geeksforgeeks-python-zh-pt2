# Python 字符串连接()方法

> 原文:[https://www.geeksforgeeks.org/python-string-join-method/](https://www.geeksforgeeks.org/python-string-join-method/)

Python String join()方法是一个字符串方法，它返回一个字符串，在该字符串中，序列的元素通过字符串分隔符连接在一起。

> **语法:**
> 
> *字符串 _ 名称*。连接(可迭代)
> 
> **参数:**
> 
> join()方法接受 iterable–能够一次返回一个成员的对象。例如**列表、元组、字符串、字典**、**和集合**
> 
> **返回值:**
> 
> join()方法返回一个与*可迭代*元素连接的字符串。
> 
> **类型错误**:
> 
> 如果 iterable 包含任何非字符串值，它将引发 TypeError 异常。

### 示例 join()方法的工作原理

## 计算机编程语言

```py
# Python program to demonstrate the
# use of join function to join list
# elements with a character.

list1 = ['1','2','3','4'] 

s = "-"

# joins elements of list1 by '-'
# and stores in sting s
s = s.join(list1)

# join use to join a list of
# strings to a separator s
print(s)
```

**输出:**

```py
1-2-3-4
```

### **例 2:用**连接**空弦**

## 计算机编程语言

```py
# Python program to demonstrate the
# use of join function to join list
# elements without any separator.

# Joining with empty separator
list1 = ['g','e','e','k', 's'] 
print("".join(list1))
```

**输出:**

```py
geeks
```