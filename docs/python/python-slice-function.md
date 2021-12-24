# Python 切片()功能

> 原文:[https://www.geeksforgeeks.org/python-slice-function/](https://www.geeksforgeeks.org/python-slice-function/)

**Python 切片()函数**返回一个切片对象。

任何类型(字符串、字节、元组、列表或范围)的对象序列，或者实现 __getitem__()和 __len__()方法的对象，则可以使用 slice()方法对该对象进行切片。

> **语法:**
> 
> *   切片(停止)
> *   切片(开始、停止、步进)
> 
> **参数:**
> 
> *   **开始:**对象切片开始的起始索引。
> *   **停止:**对象切片停止的结束索引。
> *   **步骤:**这是一个可选参数，用于确定切片的每个索引之间的增量。
> 
> **返回类型:**返回仅包含给定范围内元素的切片对象。

**注意:**如果只通过一个参数，那么开始和步骤被认为是无。

### **例 1: Python 切片串**

## 蟒蛇 3

```
# Python program to demonstrate
# slice() operator

# String slicing
String = 'GeeksforGeeks'
s1 = slice(3)
s2 = slice(1, 5, 2)

print("String slicing")
print(String[s1])
print(String[s2])
```

**输出:**

```
String slicing
Gee
ek
```

### 示例 2: **Python 切片列表或 Python 切片数组**

## 蟒蛇 3

```
# Python program to demonstrate
# slice() operator

# List slicing
L = [1, 2, 3, 4, 5]
s1 = slice(3)
s2 = slice(1, 5, 2)
print("List slicing")
print(L[s1])
print(L[s2])
```

**输出:**

```
List slicing
[1, 2, 3]
[2, 4]
```

### 示例 3: **Python 切片元组**

## 蟒蛇 3

```
# Python program to demonstrate
# slice() operator

# Tuple slicing
T = (1, 2, 3, 4, 5)
s1 = slice(3)
s2 = slice(1, 5, 2)
print("\nTuple slicing")
print(T[s1])
print(T[s2])
```

**输出:**

```
Tuple slicing
(1, 2, 3)
(2, 4)
```

## 负索引

在 Python 中，负序索引表示从数组末尾开始的位置。slice()函数也可以有负值。在这种情况下，迭代将向后执行，即从头到尾。

## 蟒蛇 3

```
# Python program to demonstrate
# slice() operator

# String slicing
String = 'GeeksforGeeks'
s1 = slice(-3)
s2 = slice(-1, -5, -2)
print("String slicing")
print(String[s1])
print(String[s2])

# List slicing
L = [1, 2, 3, 4, 5]
s1 = slice(-3)
s2 = slice(-1, -5, -2)
print("\nList slicing")
print(L[s1])
print(L[s2])

# Tuple slicing
T = (1, 2, 3, 4, 5)
s1 = slice(-3)
s2 = slice(-1, -5, -2)
print("\nTuple slicing")
print(T[s1])
print(T[s2])
```

**输出:**

```
String slicing
GeeksforGe
se

List slicing
[1, 2]
[5, 3]

Tuple slicing
(1, 2)
(5, 3)
```