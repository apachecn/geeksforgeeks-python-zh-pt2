# Python | set()方法

> 原文:[https://www.geeksforgeeks.org/python-set-method/](https://www.geeksforgeeks.org/python-set-method/)

**Set** 是数学中由不同语言组成的序列的术语，Python 也在其语言中对其进行了扩展，并且可以使用 Set()轻松制作。

**set()** 方法用于将任何可迭代元素转换为具有不同元素的可迭代元素序列，通常称为 set。

> **语法:**集合(可迭代)
> **参数:**任何可迭代的序列，如列表、元组或字典。
> **如果没有元素通过，返回:**一个空集合。作为参数传递的可迭代修改的非重复元素。

**如果从集合中得到一个无序列表，不用担心。集合是无序的。使用排序(set(sampleList))将其排序**

**代码#1 :** 用列表和元组演示集合()

## 蟒蛇 3

```
# Python3 code to demonstrate the
# working of set() on list and tuple

# initializing list
lis1 = [ 3, 4, 1, 4, 5 ]

# initializing tuple
tup1 = (3, 4, 1, 4, 5)

# Printing iterables before conversion
print("The list before conversion is : " + str(lis1))
print("The tuple before conversion is : " + str(tup1))

# Iterables after conversion are
# notice distinct and elements
print("The list after conversion is : " + str(set(lis1)))
print("The tuple after conversion is : " + str(set(tup1)))
```

**输出:**

```
The list before conversion is : [3, 4, 1, 4, 5]
The tuple before conversion is : (3, 4, 1, 4, 5)
The list after conversion is : {1, 3, 4, 5}
The tuple after conversion is : {1, 3, 4, 5}
```

**Properties of set()**

*   不传递任何参数来创建空集
*   也可以使用 set 创建字典，但转换后只保留键，值会丢失。

**代码#2:** 字典上集合工作的演示

## 蟒蛇 3

```
# Python3 code to demonstrate the
# working of set() on dictionary

# initializing list
dic1 = { 4 : 'geeks', 1 : 'for', 3 : 'geeks' }

# Printing dictionary before conversion
# internally sorted
print("Dictionary before conversion is : " + str(dic1))

# Dictionary after conversion are
# notice lost keys
print("Dictionary after conversion is : " + str(set(dic1)))
```

**Output**

```
Dictionary before conversion is : {4: 'geeks', 1: 'for', 3: 'geeks'}
Dictionary after conversion is : {1, 3, 4}
```