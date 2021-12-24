# Python 程序交换列表中的第一个和最后一个元素

> 原文:[https://www . geesforgeks . org/python-程序到交换-列表中的第一个和最后一个元素/](https://www.geeksforgeeks.org/python-program-to-interchange-first-and-last-elements-in-a-list/)

给定一个列表，编写一个 Python 程序来交换列表的第一个和最后一个元素。

**示例:**

```py
Input : [12, 35, 9, 56, 24]
Output : [24, 35, 9, 56, 12]

Input : [1, 2, 3]
Output : [3, 2, 1]
```

**方法#1:** 找到列表的长度，只需将第一个元素与第(n-1) <sup>个</sup>元素交换即可。

## 蟒蛇 3

```py
# Python3 program to swap first
# and last element of a list

# Swap function
def swapList(newList):
    size = len(newList)

    # Swapping
    temp = newList[0]
    newList[0] = newList[size - 1]
    newList[size - 1] = temp

    return newList

# Driver code
newList = [12, 35, 9, 56, 24]

print(swapList(newList))
```

**输出:**

```py
[24, 35, 9, 56, 12]
```

**方法#2:** 列表的最后一个元素可以称为列表[-1]。因此，我们可以简单地用 list[-1]交换 list[0]。

## 蟒蛇 3

```py
# Python3 program to swap first
# and last element of a list

# Swap function
def swapList(newList):

    newList[0], newList[-1] = newList[-1], newList[0]

    return newList

# Driver code
newList = [12, 35, 9, 56, 24]
print(swapList(newList))
```

**输出:**

```py
[24, 35, 9, 56, 12]
```

**方法#3:** 交换第一个和最后一个元素是使用元组变量。将第一个和最后一个元素作为一对存储在元组变量中，比如说*得到*，然后用列表中的第一个和最后一个元素解包这些元素。现在，该列表中的第一个和最后一个值被交换。

## 蟒蛇 3

```py
# Python3 program to swap first
# and last element of a list

# Swap function
def swapList(list):

    # Storing the first and last element
    # as a pair in a tuple variable get
    get = list[-1], list[0]

    # unpacking those elements
    list[0], list[-1] = get

    return list

# Driver code
newList = [12, 35, 9, 56, 24]
print(swapList(newList))
```

**输出:**

```py
[24, 35, 9, 56, 12]
```

**方法#4:** 使用*操作数。
此操作数提议对可迭代解包语法进行更改，允许指定一个“无所不包”的名称，该名称将被分配给未分配给“常规”名称的所有项目的列表。

## 蟒蛇 3

```py
# Python3 program to illustrate
# the usage of * operarnd
list = [1, 2, 3, 4]

a, *b, c = list

print(a)
print(b)
print(c)
```

**输出:**

```py
1
[2, 3]
4
```

现在让我们看看上述方法的实现:

## 蟒蛇 3

```py
# Python3 program to swap first
# and last element of a list

# Swap function
def swapList(list):

    start, *middle, end = list
    list = [end, *middle, start]

    return list

# Driver code
newList = [12, 35, 9, 56, 24]

print(swapList(newList))
```

**输出:**

```py
[24, 35, 9, 56, 12]
```

**方法#5:** 交换第一个和最后一个元素是使用内置函数 list.pop()。弹出第一个元素并将其存储在变量中。同样，弹出最后一个元素并将其存储在另一个变量中。现在在彼此的原始位置插入两个弹出的元素。

## 蟒蛇 3

```py
# Python3 program to swap first
# and last element of a list

# Swap function
def swapList(list):

    first = list.pop(0)  
    last = list.pop(-1)

    list.insert(0, last) 
    list.append(first)  

    return list

# Driver code
newList = [12, 35, 9, 56, 24]

print(swapList(newList))
```

**输出:**

```py
[24, 35, 9, 56, 12]
```