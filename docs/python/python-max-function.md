# Python–max()函数

> 原文:[https://www.geeksforgeeks.org/python-max-function/](https://www.geeksforgeeks.org/python-max-function/)

**Python max()函数 r** 返回可迭代表中最大的项目或两个或多个参数中最大的一个。

**它有两种形态。**

*   带对象的 max()函数
*   可迭代的 max()函数

## 带对象的 max()函数

与 C/C++的 max()函数不同，Python 中的 max()函数可以取任意类型的对象，并返回其中最大的一个。对于字符串，它返回字典中最大的值。

> **语法:** max(arg1，arg2，*args[，key])
> 
> **参数:**
> 
> *   **arg1、arg2 :** 相同数据类型的对象
> *   ***参数:**多个对象
> *   **键:**根据返回值进行可迭代比较的功能
> 
> **返回:**最大值

## Python max()函数示例

### **例 1:** 求 3 个整数变量的最大值

## 蟒蛇 3

```py
var1 = 4
var2 = 8
var3 = 2

max_val = max(var1, var2, var3)
print(max_val)
```

**输出:**

```py
8
```

### **例 2:** 求 3 个字符串变量的最大值

默认情况下，它将返回具有最大 lexographic 值的字符串。

## 蟒蛇 3

```py
var1 = "geeks"
var2 = "for"
var3 = "geek"

max_val = max(var1, var2, var3)
print(max_val)
```

**输出:**

```py
for
```

### **例 3:** 根据长度求 3 个字符串变量的最大值

我们将在 max()方法中传递一个关键函数。

## 蟒蛇 3

```py
var1 = "geeks"
var2 = "for"
var3 = "geek"

max_val = max(var1, var2, var3,
              key=len)
print(max_val)
```

**输出:**

```py
geeks
```

### **例 4: Python max()异常**

如果我们传递不同数据类型的参数，那么就会引发异常。

## 蟒蛇 3

```py
integer = 5
string = "geek"

max_val = max(integer, string)
print(max_val)
```

**输出:**

```py
TypeError: '>' not supported between instances of 'str' and 'int'
```

### 示例 5: Python max()浮点

## 蟒蛇 3

```py
list = [1.2, 1.3, 0.1]
max_value = max(list)
print(max_value)
```

**输出:**

```py
1.3
```

### 示例 6: Python max()索引

## 蟒蛇 3

```py
# function to find minimum and maximum position in list
def minimum(a, n):

    # inbuilt function to find the position of maximum
    maxpos = a.index(max(a))

    # printing the position
    print ("The maximum is at position", maxpos + 1)

# driver code
a = [3, 4, 1, 3, 4, 5]
minimum(a, len(a))
```

**输出:**

```py
The maximum is at position 6
```

## 可迭代的 max()函数

当 iterable 传递给 max()函数时，它返回 iterable 的最大项。

> **语法:** max(可迭代，*可迭代[，键，默认值])
> **参数:**
> 
> *   **可迭代:**列表或字符串等可迭代对象。
> *   ***迭代次数:**多个迭代次数
> *   **键:**根据返回值进行可迭代比较的功能
> *   **默认值:**值，如果可重复项为空
> 
> **返回:**最大值。

### **示例 1:** 查找字符串中字典序最大的字符

## 蟒蛇 3

```py
string = "GeeksforGeeks"

max_val = max(string)
print(max_val)
```

**输出:**

```py
s
```

### **示例 2:** 在字符串列表中查找字典序最大字符串

## 蟒蛇 3

```py
string_list = ["Geeks", "for", "Geeks"]

max_val = max(string_list)
print(max_val)
```

**输出:**

```py
for
```

### **例 3:** 查找字符串列表中最长的字符串。

## 蟒蛇 3

```py
string_list = ["Geeks", "for", "Geek"]

max_val = max(string_list, key=len)
print(max_val)
```

**输出:**

```py
Geeks
```

### **示例 4:** 如果可滴定区域为空，将显示默认值

## 蟒蛇 3

```py
dictionary = {}

max_val = max(dictionary,
              default={1: "Geek"})
print(max_val)
```

**输出:**

```py
{1: 'Geek'}
```