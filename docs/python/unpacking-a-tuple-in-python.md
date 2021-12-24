# 在 Python 中解包元组

> 原文:[https://www.geeksforgeeks.org/unpacking-a-tuple-in-python/](https://www.geeksforgeeks.org/unpacking-a-tuple-in-python/)

**Python 元组**在 Python 中[元组](https://www.geeksforgeeks.org/python-tuples/)用于存储不可变对象。Python 元组与列表非常相似，除了在某些情况下。Python 元组是不可变的，这意味着它们不能在整个程序中被修改。

**打包和解包元组:**在 Python 中，有一个非常强大的元组赋值特性，可以将值的右侧赋值到左侧。换句话说，它被称为将一个元组解包成一个变量。在打包时，我们将值放入一个新的元组中，而在解包时，我们将这些值提取到一个变量中。

**例 1**

## 蟒蛇 3

```
# Program to understand about
# packing and unpacking in Python

# this lines PACKS values
# into variable a
a = ("MNNIT Allahabad", 5000, "Engineering") 

# this lines UNPACKS values
# of variable a
(college, student, type_ofcollege) = a 

# print college name
print(college)

# print no of student
print(student)

# print type of college
print(type_ofcollege)
```

**Output:** 

```
MNNIT Allahabad
5000
Engineering
```

**注意:**在元组解包中，左侧变量的数量应该等于给定元组 a 中的值的数量。
Python 使用特殊语法传递可选参数(*args)进行元组解包。这意味着在 python 中可以有许多参数来代替(*args)。所有值将被分配给左侧的每个变量，所有剩余值将被分配给*args。为了更好地理解，请考虑下面的代码。

**例 2**

## 蟒蛇 3

```
# Python3 code to study about
# unpacking python tuple using *

# first and last will be assigned to x and z
# remaining will be assigned to y
x, *y, z = (10, "Geeks ", " for ", "Geeks ", 50)

# print details
print(x)
print(y)
print(z)

# first and second will be assigned to x and y
# remaining will be assigned to z
x, y, *z = (10, "Geeks ", " for ", "Geeks ", 50)
print(x)
print(y)
print(z)
```

**Output:** 

```
10
['Geeks ', ' for ', 'Geeks ']
50
10
Geeks 
[' for ', 'Geeks ', 50]
```

在 python 中，元组可以使用函数进行解包，在函数中，元组被传递，在函数值中，元组被解包为普通变量。为了更好地理解，请考虑下面的代码。

**例 3 :**

## 蟒蛇 3

```
# Python3 code to study about
# unpacking python tuple using function

# function takes normal arguments
# and multiply them
def result(x, y):
    return x * y
# function with normal variables
print (result(10, 100))

# A tuple is created
z = (10, 100)

# Tuple is passed
# function unpacked them

print (result(*z))
```

**Output:** 

```
1000
1000
```