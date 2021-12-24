# 蟒蛇套装

> 原文:[https://www.geeksforgeeks.org/python-sets/](https://www.geeksforgeeks.org/python-sets/)

在 Python 中，**集合**是一个无序的数据类型集合，它是可迭代的、可变的，并且没有重复的元素。集合中元素的顺序是未定义的，尽管它可能由各种元素组成。

与列表相比，使用集合的主要优点是，它有一个高度优化的方法来检查集合中是否包含特定元素。

### 创建集合

可以使用内置的 **set()** 函数创建集合，该函数带有一个可迭代对象或一个序列，方法是将序列放在花括号内，用“逗号”分隔。

**注意–**集合不能像列表或字典一样有可变元素，因为它是不可变的。

## 蟒蛇 3

```
# Python program to demonstrate
# Creation of Set in Python

# Creating a Set
set1 = set()
print("Initial blank Set: ")
print(set1)

# Creating a Set with
# the use of a String
set1 = set("GeeksForGeeks")
print("\nSet with the use of String: ")
print(set1)

# Creating a Set with
# the use of Constructor
# (Using object to Store String)
String = 'GeeksForGeeks'
set1 = set(String)
print("\nSet with the use of an Object: " )
print(set1)

# Creating a Set with
# the use of a List
set1 = set(["Geeks", "For", "Geeks"])
print("\nSet with the use of List: ")
print(set1)
```

**输出:**

```
Initial blank Set: 
set()

Set with the use of String: 
{'e', 'r', 'k', 'o', 'G', 's', 'F'}

Set with the use of an Object: 
{'r', 'o', 'e', 'F', 's', 'k', 'G'}

Set with the use of List: 
{'Geeks', 'For'}
```

一个集合只包含唯一的元素，但是在集合创建时，也可以传递多个重复的值。集合中元素的顺序是未定义的，也是不可改变的。集合中元素的类型不必相同，各种混合的数据类型值也可以传递给集合。

## 蟒蛇 3

```
# Creating a Set with
# a List of Numbers
# (Having duplicate values)
set1 = set([1, 2, 4, 4, 3, 3, 3, 6, 5])
print("\nSet with the use of Numbers: ")
print(set1)

# Creating a Set with
# a mixed type of values
# (Having numbers and strings)
set1 = set([1, 2, 'Geeks', 4, 'For', 6, 'Geeks'])
print("\nSet with the use of Mixed Values")
print(set1)
```

**输出:**

```
Set with the use of Numbers: 
{1, 2, 3, 4, 5, 6}

Set with the use of Mixed Values
{1, 2, 4, 'Geeks', 6, 'For'}
```

### 向集合中添加元素

#### 使用 add()方法

可以使用内置的 **add()** 功能将元素添加到集合中。使用 add()方法一次只能向集合中添加一个元素，使用 add()方法使用循环一次添加多个元素。

**注意–**列表不能作为元素添加到集合中，因为列表不可散列，而元组可以添加，因为元组是不可变的，因此是可散列的。

## 蟒蛇 3

```
# Python program to demonstrate
# Addition of elements in a Set

# Creating a Set
set1 = set()
print("Initial blank Set: ")
print(set1)

# Adding element and tuple to the Set
set1.add(8)
set1.add(9)
set1.add((6,7))
print("\nSet after Addition of Three elements: ")
print(set1)

# Adding elements to the Set
# using Iterator
for i in range(1, 6):
    set1.add(i)
print("\nSet after Addition of elements from 1-5: ")
print(set1)
```

**输出:**

```
Initial blank Set: 
set()

Set after Addition of Three elements: 
{8, 9, (6, 7)}

Set after Addition of elements from 1-5: 
{1, 2, 3, (6, 7), 4, 5, 8, 9}
```

#### 使用 update()方法

对于两个或更多元素的添加，使用 Update()方法。update()方法接受列表、字符串、元组以及其他集合作为参数。在所有这些情况下，都避免了重复的元素。

## 蟒蛇 3

```
# Python program to demonstrate
# Addition of elements in a Set

# Addition of elements to the Set
# using Update function
set1 = set([ 4, 5, (6, 7)])
set1.update([10, 11])
print("\nSet after Addition of elements using Update: ")
print(set1)
```

**输出:**

```
Set after Addition of elements using Update: 
{10, 11, 4, 5, (6, 7)}

```

### 访问集合

集合项不能通过引用索引来访问，因为集合是无序的，项没有索引。但是您可以使用 for 循环遍历集合项，或者使用 in 关键字询问集合中是否存在指定的值。

## 蟒蛇 3

```
# Python program to demonstrate
# Accessing of elements in a set

# Creating a set
set1 = set(["Geeks", "For", "Geeks"])
print("\nInitial set")
print(set1)

# Accessing element using
# for loop
print("\nElements of set: ")
for i in set1:
    print(i, end=" ")

# Checking the element
# using in keyword
print("Geeks" in set1)
```

**输出:**

```
Initial set: 
{'Geeks', 'For'}

Elements of set: 
Geeks For 

True 
```

### 从集合中移除元素

#### 使用 remove()方法或 discard()方法

可以使用内置的 remove()函数从集合中移除元素，但是如果集合中不存在元素，则会出现键错误。要从没有键错误的集合中移除元素，请使用 discard()，如果该元素不存在于集合中，它将保持不变。

## 蟒蛇 3

```
# Python program to demonstrate
# Deletion of elements in a Set

# Creating a Set
set1 = set([1, 2, 3, 4, 5, 6,
            7, 8, 9, 10, 11, 12])
print("Initial Set: ")
print(set1)

# Removing elements from Set
# using Remove() method
set1.remove(5)
set1.remove(6)
print("\nSet after Removal of two elements: ")
print(set1)

# Removing elements from Set
# using Discard() method
set1.discard(8)
set1.discard(9)
print("\nSet after Discarding two elements: ")
print(set1)

# Removing elements from Set
# using iterator method
for i in range(1, 5):
    set1.remove(i)
print("\nSet after Removing a range of elements: ")
print(set1)
```

**输出:**

```
Initial Set: 
{1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12}

Set after Removal of two elements: 
{1, 2, 3, 4, 7, 8, 9, 10, 11, 12}

Set after Discarding two elements: 
{1, 2, 3, 4, 7, 10, 11, 12}

Set after Removing a range of elements: 
{7, 10, 11, 12}
```

#### 使用 pop()方法

Pop()函数也可用于从集合中移除和返回元素，但它仅移除集合的最后一个元素。
**注意–**如果集合是无序的，那么就没有办法通过使用 pop()函数来确定弹出哪个元素。

## 蟒蛇 3

```
# Python program to demonstrate
# Deletion of elements in a Set

# Creating a Set
set1 = set([1, 2, 3, 4, 5, 6,
            7, 8, 9, 10, 11, 12])
print("Initial Set: ")
print(set1)

# Removing element from the
# Set using the pop() method
set1.pop()
print("\nSet after popping an element: ")
print(set1)
```

**输出:**

```
Initial Set: 
{1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12}

Set after popping an element: 
{2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12}
```

#### 使用 clear()方法

要从集合中移除所有元素，请使用 clear()函数。

## 蟒蛇 3

```
#Creating a set
set1 = set([1,2,3,4,5])
print("\n Initial set: ")
print(set1)

# Removing all the elements from
# Set using clear() method
set1.clear()
print("\nSet after clearing all the elements: ")
print(set1)
```

**输出:**

```
Initial set:
{1, 2, 3, 4, 5}

Set after clearing all the elements: 
set()
```

**Python 中的冻结集**是不可变的对象，它们只支持产生结果的方法和运算符，而不影响应用它们的一个或多个冻结集。虽然集合的元素可以随时修改，但冻结集合的元素在创建后保持不变。

如果没有传递任何参数，它将返回一个空的 frozenset。

## 蟒蛇 3

```
# Python program to demonstrate
# working of a FrozenSet

# Creating a Set
String = ('G', 'e', 'e', 'k', 's', 'F', 'o', 'r')

Fset1 = frozenset(String)
print("The FrozenSet is: ")
print(Fset1)

# To print Empty Frozen Set
# No parameter is passed
print("\nEmpty FrozenSet: ")
print(frozenset())
```

### 设置方法

<figure class="table">

| 功能 | 描述 |
| --- | --- |
| [添加()](https://www.geeksforgeeks.org/set-add-python/) | 向集合中添加元素 |
| [移除()](https://www.geeksforgeeks.org/python-remove-discard-sets/) | 从集合中移除元素。如果元素不在集合中，则引发键错误 |
| [晴()](https://www.geeksforgeeks.org/set-clear-python/) | 从集合中移除所有元素 |
| [副本()](https://www.geeksforgeeks.org/set-copy-python/) | 返回集合的浅拷贝 |
| [pop()](https://www.geeksforgeeks.org/python-set-pop/) | 移除并返回任意集合元素。如果集合为空，则引发键错误 |
| [更新()](https://www.geeksforgeeks.org/python-set-update/) | 用集合本身和其他集合的并集更新集合 |
| [union()](https://www.geeksforgeeks.org/union-function-python/) | 返回新集合中集合的并集 |
| [差异()](https://www.geeksforgeeks.org/python-set-difference/) | 将两个或多个集合的差作为新集合返回 |
| [差异 _ 更新()](https://www.geeksforgeeks.org/python-set-difference_update/) | 从该集合中移除另一集合的所有元素 |
| [丢弃()](https://www.geeksforgeeks.org/python-remove-discard-sets/) | 如果元素是成员，则从集合中移除该元素。(如果元素未设置，则不执行任何操作) |
| [交点()](https://www.geeksforgeeks.org/intersection-function-python/) | 将两个集合的交集作为新集合返回 |
| 交集 _ 更新() | 用集合本身和另一个集合的交集更新集合 |
| isdisjoint() | 如果两个集合有空交集，则返回真 |
| [isssubset()](https://www.geeksforgeeks.org/issubset-in-python/) | 如果另一个集合包含此集合，则返回真 |
| [这是上集()](https://www.geeksforgeeks.org/issuperset-in-python/) | 如果此集合包含另一个集合，则返回真 |
| [对称 _ 差()](https://www.geeksforgeeks.org/python-set-symmetric_difference-2/) | 将两个集合的对称差作为新集合返回 |
| [对称 _ 差异 _ 更新()](https://www.geeksforgeeks.org/python-set-symmetric_difference_update/) | 用一个集合和另一个集合的对称差更新该集合 |

</figure>

### [最近关于 Python 集的文章](https://www.geeksforgeeks.org/tag/python-set/)

### 设置程序

*   [接受包含所有元音的字符串的程序](https://www.geeksforgeeks.org/python-program-to-accept-the-strings-which-contains-all-vowels/)
*   [Python 程序使用集合](https://www.geeksforgeeks.org/python-program-find-common-elements-three-lists-using-sets/)在三个列表中查找公共元素
*   [在两个列表中查找缺失值和附加值](https://www.geeksforgeeks.org/python-find-missing-additional-values-two-lists/)
*   [两组成对的完整琴弦](https://www.geeksforgeeks.org/python-set-pairs-complete-strings-two-sets/)
*   [检查给定的字符串是否为异码](https://www.geeksforgeeks.org/python-set-check-whether-given-string-heterogram-not/)
*   [一组中的最大值和最小值](https://www.geeksforgeeks.org/python-maximum-minimum-set/)
*   [从器械包中取出物品](https://www.geeksforgeeks.org/python-remove-items-set/)
*   [Python 设置差异从重复数组中查找丢失的元素](https://www.geeksforgeeks.org/python-set-difference-find-lost-element-duplicated-array/)
*   [使用计数器](https://www.geeksforgeeks.org/python-minimum-number-subsets-distinct-elements-using-counter/)具有不同元素的子集的最小数量
*   [检查两个列表是否至少有一个公共元素](https://www.geeksforgeeks.org/python-check-two-lists-least-one-element-common/)
*   [使用给定字符串中的集合计算元音数量的程序](https://www.geeksforgeeks.org/python-program-count-number-vowels-using-sets-given-string/)
*   [两个列表的区别](https://www.geeksforgeeks.org/python-difference-two-lists/)
*   [Python 设置检查字符串是否为 panagram](https://www.geeksforgeeks.org/python-set-check-string-panagram/)
*   [Python 集合运算(并集、交集、差集和对称差集)](https://www.geeksforgeeks.org/python-set-operations-union-intersection-difference-symmetric-difference/)
*   [Python 中包含不常见字符的串联字符串](https://www.geeksforgeeks.org/concatenated-string-uncommon-characters-python/)
*   [Python 字典，设置并计数检查频率是否可以相同](https://www.geeksforgeeks.org/python-dictionary-set-counter-check-frequencies-can-become/)
*   [在 Python Pangram 检查中使用 Set()](https://www.geeksforgeeks.org/using-set-python-pangram-checking/)
*   [在 Python 中设置 update()做 n 个数组的并集](https://www.geeksforgeeks.org/set-update-python-union-n-arrays/)

#### 有用的链接

*   [Python 程序输出–设置](https://www.geeksforgeeks.org/output-python-programs-set-24-sets/)
*   [最近关于 Python 集的文章](https://www.geeksforgeeks.org/tag/python-set/)
*   [选择题–Python](https://www.geeksforgeeks.org/python-multiple-choice-questions/)
*   [Python 类别的所有文章](https://www.geeksforgeeks.org/category/python/)