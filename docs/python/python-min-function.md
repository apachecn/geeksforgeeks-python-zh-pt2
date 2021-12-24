# Python min()函数

> 原文:[https://www.geeksforgeeks.org/python-min-function/](https://www.geeksforgeeks.org/python-min-function/)

Python min()函数返回 iterable 中作为其参数传递的值或最小项中的最小值。有两种类型的最小函数–

*   带有对象的 min()函数
*   带有可迭代

## 带有对象的 min()函数

与 C/C++的 min()函数不同，Python 中的 min()函数可以接受任何类型的对象，并返回其中最小的对象。在字符串的情况下，它返回的字典最小值。

> **语法:** min(a，b，c，…，key=func)
> 
> **参数:**
> 
> **a、b、c、..:**类似类型的数据。
> 
> **键:**自定义排序顺序的功能

**示例:**

## 蟒蛇 3

```py
# Python code to demonstrate the 
# working of min()

# printing the minimum of
# 4, 12, 43.3, 19, 100
print(min(4, 12, 43.3, 19, 100))

# printing the minimum of 
# a, b, c, d, e
print(min('a', 'b', 'c', 'd', 'e'))
```

**输出:**

```py
4
a

```

### 自定义排序顺序

要自定义排序顺序，在 min()函数中传递键参数。

**示例:**

## 蟒蛇 3

```py
# Python code to demonstrate the 
# working of min()  

# find the string with minimum 
# length
s = min("GfG", "Geeks", "GeeksWorld", key = len)
print(s)
```

**输出:**

```py
GfG

```

### **异常出现**

min()函数在比较冲突数据类型时抛出**类型错误**。

**例:**

## 蟒蛇 3

```py
# Python code to demonstrate the
# Exception of min() 

# printing the minimum of 4, 12, 43.3, 19, 
# "GeeksforGeeks" Throws Exception 
print(min(4, 12, 43.3, 19, "GeeksforGeeks"))
```

**输出:**

```py
TypeError: unorderable types: str() < int()

```

## 带有可迭代

当可迭代函数被传递给 min 函数时，它返回可迭代函数的最小项。

> **语法:** min(可迭代，默认值= obj，键= func)
> 
> **参数:**
> 
> **可重复的:**可重复的列表、元组、字符串
> 
> **默认值:**当 iterable 为空时返回的默认值
> 
> **键:**自定义排序顺序的功能

**示例:**

## 蟒蛇 3

```py
# Python code to demonstrate the
# working of min() 

# printing the minimum of [4, 12, 43.3, 19]
print(min([4, 12, 43.3, 19]))

# printing the minimum of "GeeksforGeeks"
print(min("GeeksforGeeks"))

# printing the minimum of ("A", "b", "C")
print(min(("A", "a", "C")))
```

**输出:**

```py
4
G
A

```

### 自定义排序顺序

如上所述，要定制排序顺序，在 min()函数中传递关键字参数。

**示例:**

## 蟒蛇 3

```py
# Python code to demonstrate the
# working of min() 

d = {1: "c", 2: "b", 3: "a"}

# printing the minimum key of
# dictionary
print(min(d))

# printing the key with minimum 
# value in dictionary
print(min(d, key = lambda k: d[k]))
```

**输出:**

```py
1
3

```

### **异常出现**

当传递没有默认参数的空 iterable 时，将引发**值错误**

**示例:**

## 蟒蛇 3

```py
# Python code to demonstrate the
# Exception of min() 

L = []

# printing the minimum empty list
print(min(L))
```

**输出:**

```py
ValueError: min() arg is an empty sequence

```