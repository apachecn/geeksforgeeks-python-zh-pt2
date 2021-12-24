# Python 字符串长度| len()

> 原文:[https://www.geeksforgeeks.org/python-string-length-len/](https://www.geeksforgeeks.org/python-string-length-len/)

**Python len()函数**返回字符串的长度。

### **Python len()语法:**

> 透镜(线)

### **len()参数:**

它采用字符串作为参数。

### **len()返回值:**

它返回一个整数，即字符串的长度。

## Python len()示例

### 示例 1:包含元组、列表和字符串的 Len()函数

## 计算机编程语言

```py
# Python program to demonstrate the use of
# len() method 

# Length of below string is 5
string = "geeks"
print(len(string))

# with tuple
tup = (1,2,3)
print(len(tup))

# with list
l = [1,2,3,4]
print(len(l))
```

**输出:**

```py
5
3
4
```

### 示例 2: Python len() TypeError

## 蟒蛇 3

```py
print(len(True))
```

**输出:**

```py
TypeError: object of type 'bool' has no len()
```

### 示例 3:带有字典和集合的 Python len()

## 蟒蛇 3

```py
# Python program to demonstrate the use of
# len() method 

dic = {'a':1, 'b': 2}
print(len(dic))

s = { 1, 2, 3, 4}
print(len(s))
```

**输出:**

```py
2
4
```

### 示例 4:带有自定义对象的 Python len()

## 蟒蛇 3

```py
class Public:
    def __init__(self, number):
        self.number = number
    def __len__(self):
        return self.number

obj = Public(12)
print(len(obj))
```

**输出:**

```py
12
```