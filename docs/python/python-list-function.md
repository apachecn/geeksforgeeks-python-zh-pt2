# Python 列表()函数

> 原文:[https://www.geeksforgeeks.org/python-list-function/](https://www.geeksforgeeks.org/python-list-function/)

**Python list()** **函数**将任意可迭代作为参数，返回一个列表。在 Python 中，iterable 是可以迭代的对象。可数据项的一些例子是元组、字符串和列表。

**语法:**

```
list(iterable)
```

**参数:**

*   **可迭代的:**可以是序列(字符串、元组)或集合(集合、字典)或任何迭代器对象的对象。

**注意:**如果我们没有传递任何参数，那么 list()函数将返回一个零元素的列表(空列表)。

让我们看一些例子，以便更好地理解。

### 示例 1:使用 list()从字符串创建列表

## 计算机编程语言

```
# initializing a string
string = "ABCDEF"

# using list() function to create a list
list1 = list(string)

# printing list1
print(list1)
```

**输出:**

```
['A', 'B', 'C', 'D', 'E', 'F']
```

### 示例 2:使用 list()从元组创建列表

## 计算机编程语言

```
# initializing a tuple
tuple1 = ('A', 'B', 'C', 'D', 'E')

# using list() function to create a list
list1 = list(tuple1)

# printing list1
print(list1)
```

**输出:**

```
['A', 'B', 'C', 'D', 'E']
```

### 示例 3:使用 list()从集合和字典创建列表

## 计算机编程语言

```
# initializing a set
set1 = {'A', 'B', 'C', 'D', 'E'}

# initializing a dictionary
dictionary = {'A': 1, 'B': 2, 'C': 3, 'D': 4, 'E': 5}

# using list() to create a list
list1 = list(set1)
list2 = list(dictionary)

# printing
print(list1)
print(list2)
```

**输出:**

```
['C', 'E', 'D', 'B', 'A']
['A', 'B', 'C', 'D', 'E']
```

我们也可以在接收用户输入时使用 list()函数，以列表的形式直接接收输入。

### 示例 4:将用户输入作为列表

## 计算机编程语言

```
# Taking input from user as list
list1 = list(input("Please Enter List Elements: "))

# printing
print(list1)
```

**输出:**

```
Please Enter List Elements: 12345
['1', '2', '3', '4', '5']
```