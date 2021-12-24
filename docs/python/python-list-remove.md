# Python 列表移除()

> 原文:[https://www.geeksforgeeks.org/python-list-remove/](https://www.geeksforgeeks.org/python-list-remove/)

Python 列表 **remove()** 是 Python 编程语言中的一个内置函数，用于从[列表](https://www.geeksforgeeks.org/python-list/)中移除给定的对象。

> **语法:**
> 
> list_name.remove(obj)
> 
> **参数:**
> 
> *   **对象:**要从列表中删除的对象
> 
> **返回:**
> 
> 方法不返回任何值，但从列表中移除给定的对象。
> 
> 例外:
> 
> 如果元素不存在，它将抛出 ValueError: list.remove(x): x 不在列表异常中。
> 
> **注:**
> 
> 它从列表中移除对象的第一个匹配项。

### **示例 1:** 从列表中删除元素

## 蟒蛇 3

```py
# Python3 program to demonstrate the use of
# remove() method

# the first occurrence of 1 is removed from the list
list1 = [ 1, 2, 1, 1, 4, 5 ]
list1.remove(1)
print(list1)

# removes 'a' from list2
list2 = [ 'a', 'b', 'c', 'd' ]
list2.remove('a')
print(list2)
```

**输出:**

```py
[2, 1, 1, 4, 5]
['b', 'c', 'd']
```

### **例 2:** 删除不存在的元素

## 蟒蛇 3

```py
# Python3 program for the error in
# remove() method

# removes 'e' from list2
list2 = [ 'a', 'b', 'c', 'd' ]

list2.remove('e')
print(list2)
```

**输出:**

```py
Traceback (most recent call last):
  File "/home/e35b642d8d5c06d24e9b31c7e7b9a7fa.py", line 8, in 
    list2.remove('e') 
ValueError: list.remove(x): x not in list
```

### **示例 3:在具有重复元素**T5 的 **L** 上使用**移除()方法**

## 蟒蛇 3

```py
# My List
list2 = [ 'a', 'b', 'c', 'd', 'd', 'e', 'd' ]

# removing 'd'
list2.remove('d')

print(list2)
```

**输出:**

```py
['a', 'b', 'c', 'd', 'e', 'd']
```

> **注意**:如果列表包含重复元素，则从列表中删除对象的第一个匹配项。

### 示例 4:给定一个列表，从列表中删除所有的 1 并打印该列表

## 蟒蛇 3

```py
# Python3 program for practical application
# of removing 1 until all 1 are removed from the list

list1 = [1, 2, 3, 4, 1, 1, 1, 4, 5]

# looping till all 1's are removed
while (list1.count(1)):
    list1.remove(1)

print(list1)
```

**输出:**

```py
[2, 3, 4, 4, 5]
```

### **示例 5:给定一个列表，使用 in 关键字**从列表中移除所有 2

## 蟒蛇 3

```py
# Python3 program for practical application
# of removing 2 until all 2 are removed from the list

mylist = [1, 2, 3, 2, 2]

# looping till all 2's are removed
while 2 in mylist: mylist.remove(2)

print(mylist)
```

**输出:**

```py
[1, 3]
```