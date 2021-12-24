# Python 列表计数()方法

> 原文:[https://www.geeksforgeeks.org/python-list-count-method/](https://www.geeksforgeeks.org/python-list-count-method/)

Python 列表 **count()** 是 Python 中的一个内置函数，它返回给定对象在[列表](https://www.geeksforgeeks.org/python-list/)中出现的次数。count()函数用于对列表和字符串中的元素进行计数。

> **语法:**
> 
> list_name.count(对象)
> 
> **参数:**
> 
> 对象是要返回其计数的东西。
> 
> **返回:**
> 
> count()方法返回对象在列表中出现的次数计数。
> 
> 例外:
> 
> 如果在 count()方法中传递了 1 个以上的参数，它将返回一个**类型错误**。

### **例 1:** 使用 count()**T3】**

## 蟒蛇 3

```
# Python3 program to count the number of times
# an object appears in a list using count() method

list1 = [1, 1, 1, 2, 3, 2, 1]

# Counts the number of times 1 appears in list1
print(list1.count(1))

list2 = ['a', 'a', 'a', 'b', 'b', 'a', 'c', 'b']

# Counts the number of times 'b' appears in list2
print(list2.count('b'))

list3 = ['Cat', 'Bat', 'Sat', 'Cat', 'cat', 'Mat']

# Counts the number of times 'Cat' appears in list3
print(list3.count('Cat'))
```

**输出:**

```
4
3
2
```

### **例 2:类型错误**

## 蟒蛇 3

```
# Python3 program to demonstrate
# the error in count() method

list1 = [1, 1, 1, 2, 3, 2, 1]

# Error when two parameters is passed.
print(list1.count(1, 2))
```

**输出:**

```
Traceback (most recent call last):
  File "/home/41d2d7646b4b549b399b0dfe29e38c53.py", line 7, in 
    print(list1.count(1, 2))  
TypeError: count() takes exactly one argument (2 given)
```

### **示例 3:** 统计列表中的元组和列表元素

## 蟒蛇 3

```
# Python3 program to count the number of times
# an object appears in a list using count() method

list1 = [ ('Cat', 'Bat'), ('Sat', 'Cat'), ('Cat', 'Bat'),
          ('Cat', 'Bat', 'Sat'), [1, 2], [1, 2, 3], [1, 2] ]

# Counts the number of times 'Cat' appears in list1
print(list1.count(('Cat', 'Bat')))

# Count the number of times sublist
# '[1, 2]' appears in list1
print(list1.count([1, 2]))
```

**输出:**

```
2
2
```

### **实际应用**

假设我们想对一个列表中的每个元素进行计数，并将其存储在另一个列表或比如字典中。

## 蟒蛇 3

```
# Python3 program to count the number of times
# an object appears in a list using count() method

lst = ['Cat', 'Bat', 'Sat', 'Cat', 'Mat', 'Cat', 'Sat']

# To get the number of occurrences
# of each item in a list
print ([ [l, lst.count(l)] for l in set(lst)])

# To get the number of occurrences
# of each item in a dictionary
print (dict( (l, lst.count(l) ) for l in set(lst)))
```

**输出:**

```
[['Mat', 1], ['Cat', 3], ['Sat', 2], ['Bat', 1]]
{'Bat': 1, 'Cat': 3, 'Sat': 2, 'Mat': 1}
```