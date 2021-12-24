# Python 列表

> 原文:[https://www.geeksforgeeks.org/python-list/](https://www.geeksforgeeks.org/python-list/)

**列表**就像动态大小的数组，用其他语言声明(C++中的 vector 和 Java 中的 ArrayList)。列表不必总是相同的，这使得它成为 [Python](https://www.geeksforgeeks.org/python-programming-language/) 中最强大的工具。单个列表可能包含整数、字符串和对象等数据类型。列表是可变的，因此，即使在创建之后，它们也可以被更改。

Python 中的列表是有序的，并且有明确的计数。列表中的元素按照一定的顺序进行索引，列表的索引以 0 作为第一个索引。列表中的每个元素在列表中都有其明确的位置，这允许复制列表中的元素，每个元素都有其独特的位置和可信度。

**注意-** 列表是保存数据序列并对其进行进一步迭代的有用工具。

> **目录:**
> 
> *   [创建列表](#cl)
> *   [知道列表的大小](#ksl)
> *   [向列表中添加元素:](#ael)
>     *   [使用追加()方法](#uam)
>     *   [使用插入()方法](#uim)
>     *   [使用 extend()方法](#uem)
> *   [从列表中访问元素](#ael)
> *   [从列表中删除元素:](#rel)
>     *   [使用移除()方法](#urm)
>     *   [使用 pop()方法](#upm)
> *   [列表切片](#sl)
> *   [列表理解](#lc)
> *   [列表上的操作](#ool)
> *   [列出方法](#lm)

## 创建列表

Python 中的列表可以通过将序列放在方括号[]中来创建。与[设置](https://www.geeksforgeeks.org/python-sets/)不同，列表不需要内置函数来创建列表。

**注意–**与集合不同，列表可能包含可变元素。

## 蟒蛇 3

```
# Python program to demonstrate
# Creation of List

# Creating a List
List = []
print("Blank List: ")
print(List)

# Creating a List of numbers
List = [10, 20, 14]
print("\nList of numbers: ")
print(List)

# Creating a List of strings and accessing
# using index
List = ["Geeks", "For", "Geeks"]
print("\nList Items: ")
print(List[0])
print(List[2])

# Creating a Multi-Dimensional List
# (By Nesting a list inside a List)
List = [['Geeks', 'For'] , ['Geeks']]
print("\nMulti-Dimensional List: ")
print(List)
```

**Output:** 

```
Blank List: 
[]

List of numbers: 
[10, 20, 14]

List Items
Geeks
Geeks

Multi-Dimensional List: 
[['Geeks', 'For'], ['Geeks']]
```

### 创建包含多个不同或重复元素的列表

一个列表可能包含具有不同位置的重复值，因此，在创建列表时，多个不同或重复的值可以作为一个序列传递。

## 蟒蛇 3

```
# Creating a List with
# the use of Numbers
# (Having duplicate values)
List = [1, 2, 4, 4, 3, 3, 3, 6, 5]
print("\nList with the use of Numbers: ")
print(List)

# Creating a List with
# mixed type of values
# (Having numbers and strings)
List = [1, 2, 'Geeks', 4, 'For', 6, 'Geeks']
print("\nList with the use of Mixed Values: ")
print(List)
```

**Output:** 

```
List with the use of Numbers: 
[1, 2, 4, 4, 3, 3, 3, 6, 5]

List with the use of Mixed Values: 
[1, 2, 'Geeks', 4, 'For', 6, 'Geeks']
```

## 知道列表的大小

## 蟒蛇 3

```
# Creating a List
List1 = []
print(len(List1))

# Creating a List of numbers
List2 = [10, 20, 14]
print(len(List2))
```

**Output:** 

```
0
3
```

## 向列表中添加元素

### 使用 append()方法

可以使用内置的 [**【追加】(**](https://www.geeksforgeeks.org/list-methods-python/) 功能将元素添加到列表中。使用 append()方法一次只能向列表中添加一个元素，对于使用 append()方法添加多个元素，将使用循环。还可以使用 append 方法将元组添加到列表中，因为元组是不可变的。与集合不同，也可以使用 append()方法将列表添加到现有列表中。

## 蟒蛇 3

```
# Python program to demonstrate
# Addition of elements in a List

# Creating a List
List = []
print("Initial blank List: ")
print(List)

# Addition of Elements
# in the List
List.append(1)
List.append(2)
List.append(4)
print("\nList after Addition of Three elements: ")
print(List)

# Adding elements to the List
# using Iterator
for i in range(1, 4):
    List.append(i)
print("\nList after Addition of elements from 1-3: ")
print(List)

# Adding Tuples to the List
List.append((5, 6))
print("\nList after Addition of a Tuple: ")
print(List)

# Addition of List to a List
List2 = ['For', 'Geeks']
List.append(List2)
print("\nList after Addition of a List: ")
print(List)
```

**Output:** 

```
Initial blank List: 
[]

List after Addition of Three elements: 
[1, 2, 4]

List after Addition of elements from 1-3: 
[1, 2, 4, 1, 2, 3]

List after Addition of a Tuple: 
[1, 2, 4, 1, 2, 3, (5, 6)]

List after Addition of a List: 
[1, 2, 4, 1, 2, 3, (5, 6), ['For', 'Geeks']]
```

### 使用 insert()方法

append()方法仅适用于在列表末尾添加元素，对于在所需位置添加元素，则使用 insert()方法。与只接受一个参数的 append()不同，insert()方法需要两个参数(位置、值)。

## 蟒蛇 3

```
# Python program to demonstrate
# Addition of elements in a List

# Creating a List
List = [1,2,3,4]
print("Initial List: ")
print(List)

# Addition of Element at
# specific Position
# (using Insert Method)
List.insert(3, 12)
List.insert(0, 'Geeks')
print("\nList after performing Insert Operation: ")
print(List)
```

**Output:** 

```
Initial List: 
[1, 2, 3, 4]

List after performing Insert Operation: 
['Geeks', 1, 2, 3, 12, 4]
```

### 使用扩展()方法

除了 append()和 insert()方法之外，还有一种添加元素的方法， [**extend()**](https://www.geeksforgeeks.org/append-extend-python/) ，这种方法用于在列表末尾同时添加多个元素。
**注意–**[追加()和扩展()](https://www.geeksforgeeks.org/append-extend-python/)方法只能在末尾添加元素。

## 蟒蛇 3

```
# Python program to demonstrate
# Addition of elements in a List

# Creating a List
List = [1,2,3,4]
print("Initial List: ")
print(List)

# Addition of multiple elements
# to the List at the end
# (using Extend Method)
List.extend([8, 'Geeks', 'Always'])
print("\nList after performing Extend Operation: ")
print(List)
```

**Output:** 

```
Initial List: 
[1, 2, 3, 4]

List after performing Extend Operation: 
[1, 2, 3, 4, 8, 'Geeks', 'Always']
```

## 从列表中访问元素

为了访问列表项，请参考索引号。使用索引运算符[ ]访问列表中的项目。索引必须是整数。使用嵌套索引访问嵌套列表。

## 蟒蛇 3

```
# Python program to demonstrate
# accessing of element from list

# Creating a List with
# the use of multiple values
List = ["Geeks", "For", "Geeks"]

# accessing a element from the
# list using index number
print("Accessing a element from the list")
print(List[0])
print(List[2])

# Creating a Multi-Dimensional List
# (By Nesting a list inside a List)
List = [['Geeks', 'For'] , ['Geeks']]

# accessing an element from the
# Multi-Dimensional List using
# index number
print("Accessing a element from a Multi-Dimensional list")
print(List[0][1])
print(List[1][0])
```

**Output:** 

```
Accessing a element from the list
Geeks
Geeks
Accessing a element from a Multi-Dimensional list
For
Geeks
```

### 负索引

在 Python 中，负序索引表示从数组末尾开始的位置。不必像列表[len(List)-3]那样计算偏移量，只需编写 List[-3]就足够了。负索引表示从末尾开始，-1 表示最后一项，-2 表示倒数第二项，等等。

## 蟒蛇 3

```
List = [1, 2, 'Geeks', 4, 'For', 6, 'Geeks']

# accessing an element using
# negative indexing
print("Accessing element using negative indexing")

# print the last element of list
print(List[-1])

# print the third last element of list
print(List[-3])
```

**Output:** 

```
Accessing element using negative indexing
Geeks
For
```

## 从列表中删除元素

### 使用 remove()方法

可以使用内置的 [**【移除()**](https://www.geeksforgeeks.org/python-list-remove/) 功能从列表中移除元素，但是如果元素不在集合中，则会出现错误。 [Remove()](https://www.geeksforgeeks.org/python-list-remove/) 方法一次只移除一个元素，要移除一系列元素，就要用到迭代器。remove()方法移除指定的项。

**注意–**列表中的移除方法只会移除搜索到的元素的第一个匹配项。

## 蟒蛇 3

```
# Python program to demonstrate
# Removal of elements in a List

# Creating a List
List = [1, 2, 3, 4, 5, 6,
        7, 8, 9, 10, 11, 12]
print("Initial List: ")
print(List)

# Removing elements from List
# using Remove() method
List.remove(5)
List.remove(6)
print("\nList after Removal of two elements: ")
print(List)

# Removing elements from List
# using iterator method
for i in range(1, 5):
    List.remove(i)
print("\nList after Removing a range of elements: ")
print(List)
```

**Output:** 

```
Initial List: 
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12]

List after Removal of two elements: 
[1, 2, 3, 4, 7, 8, 9, 10, 11, 12]

List after Removing a range of elements: 
[7, 8, 9, 10, 11, 12]
```

### 使用 pop()方法

[Pop()](https://www.geeksforgeeks.org/python-list-pop/) 函数也可以用来从集合中移除并返回一个元素，但默认情况下它只移除集合的最后一个元素，要从 List 的特定位置移除一个元素，元素的索引作为参数传递给 Pop()方法。

## 蟒蛇 3

```
List = [1,2,3,4,5]

# Removing element from the
# Set using the pop() method
List.pop()
print("\nList after popping an element: ")
print(List)

# Removing element at a
# specific location from the
# Set using the pop() method
List.pop(2)
print("\nList after popping a specific element: ")
print(List)
```

**Output:** 

```
List after popping an element: 
[1, 2, 3, 4]

List after popping a specific element: 
[1, 2, 4]
```

## 列表切片

在 Python List 中，有多种方法可以打印包含所有元素的整个 List，但是要打印列表中特定范围的元素，我们使用[切片操作](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)。使用冒号(:)对列表执行切片操作。要打印从开始到某个范围的元素，请使用[: Index]，要打印从最终使用[:-Index]的元素，要打印从特定索引到最终使用[Index:]的元素，要打印某个范围内的元素，请使用[Start Index:End Index]，要使用切片操作打印整个列表，请使用[:]。此外，要以相反的顺序打印整个列表，请使用[::-1]。
**注意–**要从后端打印列表元素，请使用负索引。

![python-list-slicing](img/b92681e804461529d2d34b90d3e9ea3d.png)

## 蟒蛇 3

```
# Python program to demonstrate
# Removal of elements in a List

# Creating a List
List = ['G','E','E','K','S','F',
        'O','R','G','E','E','K','S']
print("Initial List: ")
print(List)

# Print elements of a range
# using Slice operation
Sliced_List = List[3:8]
print("\nSlicing elements in a range 3-8: ")
print(Sliced_List)

# Print elements from a
# pre-defined point to end
Sliced_List = List[5:]
print("\nElements sliced from 5th "
      "element till the end: ")
print(Sliced_List)

# Printing elements from
# beginning till end
Sliced_List = List[:]
print("\nPrinting all elements using slice operation: ")
print(Sliced_List)
```

**Output:** 

```
Initial List: 
['G', 'E', 'E', 'K', 'S', 'F', 'O', 'R', 'G', 'E', 'E', 'K', 'S']

Slicing elements in a range 3-8: 
['K', 'S', 'F', 'O', 'R']

Elements sliced from 5th element till the end: 
['F', 'O', 'R', 'G', 'E', 'E', 'K', 'S']

Printing all elements using slice operation: 
['G', 'E', 'E', 'K', 'S', 'F', 'O', 'R', 'G', 'E', 'E', 'K', 'S']
```

### 负索引列表切片

## 蟒蛇 3

```
# Creating a List
List = ['G','E','E','K','S','F',
        'O','R','G','E','E','K','S']
print("Initial List: ")
print(List)

# Print elements from beginning
# to a pre-defined point using Slice
Sliced_List = List[:-6]
print("\nElements sliced till 6th element from last: ")
print(Sliced_List)

# Print elements of a range
# using negative index List slicing
Sliced_List = List[-6:-1]
print("\nElements sliced from index -6 to -1")
print(Sliced_List)

# Printing elements in reverse
# using Slice operation
Sliced_List = List[::-1]
print("\nPrinting List in reverse: ")
print(Sliced_List)
```

**Output:** 

```
Initial List: 
['G', 'E', 'E', 'K', 'S', 'F', 'O', 'R', 'G', 'E', 'E', 'K', 'S']

Elements sliced till 6th element from last: 
['G', 'E', 'E', 'K', 'S', 'F', 'O']

Elements sliced from index -6 to -1
['R', 'G', 'E', 'E', 'K']

Printing List in reverse: 
['S', 'K', 'E', 'E', 'G', 'R', 'O', 'F', 'S', 'K', 'E', 'E', 'G']
```

## 列表理解

[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/) 用于从元组、字符串、数组、列表等其他项创建新列表。
列表理解由包含表达式的括号组成，该表达式与 for 循环一起对每个元素执行，以迭代每个元素。

**语法:**

> 新列表= [旧列表中元素的表达式(元素)if 条件]

**示例:**

## 蟒蛇 3

```
# Python program to demonstrate list
# comprehension in Python

# below list contains square of all
# odd numbers from range 1 to 10
odd_square = [x ** 2 for x in range(1, 11) if x % 2 == 1]
print (odd_square)
```

**输出:**

```
[1, 9, 25, 49, 81]
```

为了更好地理解，上面的代码类似于–

## 蟒蛇 3

```
# for understanding, above generation is same as,
odd_square = []

for x in range(1, 11):
    if x % 2 == 1:
        odd_square.append(x**2)

print (odd_square)
```

**输出:**

```
[1, 9, 25, 49, 81]
```

参考下面的文章来获得关于列表理解的详细信息。

*   [Python 列表理解和切片](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)
*   [Python 中的嵌套列表理解](https://www.geeksforgeeks.org/nested-list-comprehensions-in-python/)
*   [用 Python 列出理解和顺序()](https://www.geeksforgeeks.org/list-comprehension-and-ord-in-python-to-remove-all-characters-other-than-alphabets/)

## 列表上的操作

*   [查找列表长度](https://www.geeksforgeeks.org/python-ways-to-find-length-of-list/)
*   [在 Python 中遍历列表](https://www.geeksforgeeks.org/iterate-over-a-list-in-python/)
*   [在 Python 中连接两个列表](https://www.geeksforgeeks.org/python-ways-to-concatenate-two-lists/)
*   [列表会员测试](https://www.geeksforgeeks.org/python-membership-identity-operators-not-not/)

## 列出方法

<figure class="table">

| 功能 | 描述 |
| --- | --- |
| [追加()](https://www.geeksforgeeks.org/append-extend-python/) | 在列表的末尾添加一个元素 |
| [Extend()](https://www.geeksforgeeks.org/append-extend-python/) | 将列表中的所有元素添加到另一个列表中 |
| [插入()](https://www.geeksforgeeks.org/list-methods-in-python-set-2-del-remove-sort-insert-pop-extend/) | 在定义的索引处插入一个项目 |
| [移除()](https://www.geeksforgeeks.org/list-methods-in-python-set-2-del-remove-sort-insert-pop-extend/) | 从列表中移除项目 |
| [Pop()](https://www.geeksforgeeks.org/list-methods-in-python-set-2-del-remove-sort-insert-pop-extend/) | 移除并返回给定索引处的元素 |
| [Clear()](https://www.geeksforgeeks.org/list-methods-in-python-set-2-del-remove-sort-insert-pop-extend/) | 从列表中删除所有项目 |
| [指数()](https://www.geeksforgeeks.org/python-list-index/) | 返回第一个匹配项的索引 |
| [计数()](https://www.geeksforgeeks.org/python-list-function-count/) | 返回作为参数传递的项目数的计数 |
| [排序()](https://www.geeksforgeeks.org/sort-in-python/) | 按升序对列表中的项目进行排序 |
| [反转()](https://www.geeksforgeeks.org/list-methods-in-python-set-2-del-remove-sort-insert-pop-extend/) | 颠倒列表中项目的顺序 |
| [副本()](https://www.geeksforgeeks.org/python-list-copy-method/) | 返回列表的副本 |

</figure>

### 带有列表的内置函数

<figure class="table">

| 功能 | 描述 |
| --- | --- |
| [减少()](https://www.geeksforgeeks.org/reduce-in-python/) | 将参数中传递的特定函数应用于所有列表元素会存储中间结果，并且只返回最终的求和值 |
| [sum()](https://www.geeksforgeeks.org/sum-function-python/) | 总结列表中的数字 |
| [字数 （）](https://www.geeksforgeeks.org/ord-function-python/) | 返回一个整数，表示给定 Unicode 字符的 Unicode 代码点 |
| CMP() | 如果第一个列表比第二个列表“大”，这个函数返回 1 |
| 最大值() | 返回给定列表的最大元素 |
| 最小值() | 返回给定列表的最小元素 |
| [all()](https://www.geeksforgeeks.org/any-all-in-python/) | 如果所有元素都为真或列表为空，则返回真 |
| [任意()](https://www.geeksforgeeks.org/any-all-in-python/) | 如果列表中的任何元素为真，则返回 true。如果列表为空，则返回 false |
| len() | 返回列表的长度或列表的大小 |
| [枚举()](https://www.geeksforgeeks.org/enumerate-in-python/) | 返回列表的枚举对象 |
| 累积() | 将参数中传递的特定函数应用于所有列表元素会返回一个包含中间结果的列表 |
| [过滤器()](https://www.geeksforgeeks.org/filter-in-python/) | 测试列表中的每个元素是否为真 |
| [地图()](https://www.geeksforgeeks.org/python-map-function/) | 将给定函数应用于给定 iterable 的每个项目后，返回结果列表 |
| [λ()](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/) | 此函数可以有任意数量的参数，但只能有一个表达式，该表达式将被计算并返回。 |

</figure>

### [列表上最近的文章](https://www.geeksforgeeks.org/tag/python-list/)

> **更多 Python List 视频:**
> [Python List–第二集](https://youtu.be/1Ej7ry6jacg)

### 关于 Python 列表的更多信息–

*   [创建三维列表](https://www.geeksforgeeks.org/python-creating-3d-list/)
*   [在 Python 中遍历列表](https://www.geeksforgeeks.org/iterate-over-a-list-in-python/)
*   [同时迭代多个列表](https://www.geeksforgeeks.org/python-iterate-multiple-lists-simultaneously/)
*   [Python 中列表的内部工作](https://www.geeksforgeeks.org/internal-working-of-list-in-python/)
*   [蟒蛇切片](https://www.geeksforgeeks.org/python-slicing-reverse-array-groups-given-size/)
*   [Python 列表理解与生成器表达式](https://www.geeksforgeeks.org/python-list-comprehensions-vs-generator-expressions/)
*   Python 中的列表方法–[第 1 集](https://www.geeksforgeeks.org/list-methods-in-python-set-1-in-not-in-len-min-max/) [第 2 集](https://www.geeksforgeeks.org/list-methods-python/)
*   [λ表达式和过滤功能](https://www.geeksforgeeks.org/intersection-two-arrays-python-lambda-expression-filter-function/)

**有用链接:**

*   [Python 列表近期文章](https://www.geeksforgeeks.org/tag/python-list/)
*   [Python 教程](https://www.geeksforgeeks.org/python-programming-language/)
*   列表中的 Python 输出程序:[第 6 集](https://www.geeksforgeeks.org/output-python-program-set-6/)、[第 11 集](https://www.geeksforgeeks.org/output-python-program-set-11lists/)、[第 12 集](https://www.geeksforgeeks.org/output-python-program-set-12lists-tuples/)、[第 13 集](https://www.geeksforgeeks.org/output-python-program-set-13lists-tuples/)
*   [选择题](https://www.geeksforgeeks.org/python-multiple-choice-questions/)
*   [Python 类别的所有文章](https://www.geeksforgeeks.org/category/python/)