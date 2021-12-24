# Python 列表 VS 数组 VS 元组

> 原文:[https://www . geesforgeks . org/python-list-vs-array-vs-tuple/](https://www.geeksforgeeks.org/python-list-vs-array-vs-tuple/)

[**列表:**](https://www.geeksforgeeks.org/python-list/) 列表是可变的有序集合数据类型，这意味着它可以很容易地修改，我们可以更改它的数据值，列表可以被索引、切片和更改，每个元素都可以使用它在列表中的索引值来访问。以下是列表的主要特征:

*   该列表是数据类型的有序集合。
*   列表是可变的。
*   列表是动态的，可以包含不同数据类型的对象。
*   列表元素可以通过索引号来访问。

**示例:**

## 计算机编程语言

```
# Python program to demonstrate List

list = ["mango", "strawberry", "orange",
        "apple", "banana"]
print(list)

# we can specify the range of the
# index by specifying where to start
# and where to end
print(list[2:4])

# we can also change the item in the
# list by using its index number
list[1] = "grapes"
print(list[1])
```

**输出:**

```
['mango', 'strawberry', 'orange', 'apple', 'banana']
['orange', 'apple']
grapes
```

[**数组:**](https://www.geeksforgeeks.org/python-arrays/) 数组是存储在连续内存位置的项目集合。想法是将多个相同类型的项目存储在一起。这使得通过简单地将偏移加到基值，即数组的第一个元素的存储位置(通常由数组的名称表示)，来计算每个元素的位置变得更容易。阵列的主要特征如下:

*   数组是相似数据类型的有序集合。
*   数组是可变的。
*   可以通过使用数组的索引号来访问数组。

**示例:**

## 计算机编程语言

```
# Python program to demonstrate 
# Creation of Array 

# importing "array" for array creations
import array as arr

# creating an array with integer type
a = arr.array('i', [1, 2, 3])

# printing original array
print ("The new created array is : ", end =" ")
for i in range (0, 3):
    print (a[i], end =" ")
print()

# creating an array with float type
b = arr.array('d', [2.5, 3.2, 3.3])

# printing original array
print ("The new created array is : ", end =" ")
for i in range (0, 3):
    print (b[i], end =" ")
```

**输出:**

```
The new created array is :  1 2 3 
The new created array is :  2.5 3.2 3.3
```

[**元组:**](https://www.geeksforgeeks.org/python-tuples/) 元组是有序的、不可变的数据类型，这意味着我们不能改变它的值，元组写在圆括号里。我们可以通过引用方括号内的索引号来访问元组。以下是元组的主要特征:

*   元组是不可变的，可以存储任何类型的数据类型。
*   它是使用()定义的。
*   它不能被改变或替换，因为它是不可变的数据类型。

**示例:**

## 计算机编程语言

```
tuple = ("orange","apple","banana")
print(tuple)

# we can access the items in
# the tuple by its index number
print(tuple[2])

#we can specify the range of the
# index by specifying where to start
# and where to end
print(tuple[0:2])
```

**输出:**

```
('orange', 'apple', 'banana')
banana
('orange', 'apple')
```

## **列表、数组和元组差异表:**

<figure class="table">

| 

**列表**

 | 

**阵列**

 | 

**元组**

 |
| --- | --- | --- |
| 列表是可变的 | 数组是可变的 | 元组是不可变的 |
| 列表是有序的项目集合 | 数组是有序的项目集合 | 元组是项目的有序集合 |
| 列表中的项目可以更改或替换 | 数组中的项目可以更改或替换 | 元组中的项目不能更改或替换 |
| 列表可以存储多种数据类型 | 数组只能存储相似的数据类型 | 元组可以存储多种数据类型 |

</figure>