# Python |将元组转换为字符串的程序

> 原文:[https://www . geesforgeks . org/python-program-convert-a-tuple-a-string/](https://www.geeksforgeeks.org/python-program-to-convert-a-tuple-to-a-string/)

给定一个字符元组，编写一个 python 程序将元组转换成字符串。

**示例:**

```py
Input : ('a', 'b', 'c', 'd', 'e')
Output : abcde

Input : ('g', 'e', 'e', 'k', 's')
Output : geeks
```

## **接近:**

有多种方法可以将元组转换为字符串。

### **方法 1:使用简单 for 循环**

创建一个空字符串，并使用 for 循环遍历元组的元素，并继续将每个元素添加到空字符串中。这样，元组被转换成字符串。在 Python 中，将元组转换为字符串是最简单的方法之一。

## 蟒蛇 3

```py
# Python3 code to convert a tuple
# into a string using a for loop

def convertTuple(tup):
        # initialize an empty string
    str = ''
    for item in tup:
        str = str + item
    return str

# Driver code
tuple = ('g', 'e', 'e', 'k', 's')
str = convertTuple(tuple)
print(str)
```

**输出:**

```py
geeks
```

### **方法 2:使用 str.join()**

join()方法是一个字符串方法，它返回一个字符串，在该字符串中，序列的元素通过字符串分隔符连接在一起。
使用 join()我们添加元组的字符，并将其转换为字符串。

## 蟒蛇 3

```py
# Python3 code to convert a tuple
# into a string using str.join() method

def convertTuple(tup):
    str = ''.join(tup)
    return str

# Driver code
tuple = ('g', 'e', 'e', 'k', 's')
str = convertTuple(tuple)
print(str)
```

**输出:**

```py
geeks
```

### 方法 3:使用 str.join()函数和 map()函数

当我们只有字符串对象作为元组元素时，str.join()函数工作得很好，但是如果元组包含至少一个非字符串对象，那么 str.join()函数将失败，并显示一个类型错误，因为字符串对象不能添加到非字符串对象中。因此，为了避免这种类型错误，我们将在连接()中使用 map()函数。这个 map()函数将把元组和 str()函数的迭代器作为参数，并将元组的每个元素转换成一个字符串。

## 蟒蛇 3

```py
# Python3 code to convert a tuple
# into a string using str.join() & map() functions

def convertTuple(tup):
    st = ''.join(map(str, tup))
    return st

# Driver code
tuple = ('g', 'e', 'e', 'k', 's', 101)
str = convertTuple(tuple)
print(str)
```

**输出:**

```py
geeks101
```

### **方法 4:使用 reduce()函数**

reduce(fun，seq)函数用于将参数中传递的特定函数应用于在传递的序列中提到的所有列表元素。我们在函数中传递 add 运算符来连接元组的字符。

## 蟒蛇 3

```py
# Python3 code to convert a tuple
# into a string using reduce() function
import functools
import operator

def convertTuple(tup):
    str = functools.reduce(operator.add, (tup))
    return str

# Driver code
tuple = ('g', 'e', 'e', 'k', 's')
str = convertTuple(tuple)
print(str)
```

**输出:**

```py
geeks
```