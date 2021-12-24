# Python 列表插入()

> 原文:[https://www.geeksforgeeks.org/python-list-insert/](https://www.geeksforgeeks.org/python-list-insert/)

Python List***insert()***方法是 Python 中的一个内置函数，它在列表中给定的索引处插入给定的元素。

> **语法:**
> 
> list_name.insert(索引，元素)
> 
> **参数:**
> 
> *   **索引:**必须插入元素的索引。
> *   **元素:**列表中要插入的元素。
> 
> **返回:**
> 
> 此方法不返回任何值，但会在给定的索引处插入给定的元素。
> 
> **错误:**
> 
> 如果在 insert()中使用了列表以外的任何内容，那么它将返回一个 AttributeError。
> 
> **注:**
> 
> 如果给定的索引> =长度(列表)，它将插入列表的末尾。

### **示例 1:** 将元素插入列表

## 蟒蛇 3

```py
# Python3 program for use  
# of insert() method 

list1 = [ 1, 2, 3, 4, 5, 6, 7 ] 

# insert 10 at 4th index 
list1.insert(4, 10) 
print(list1) 

list2 = ['a', 'b', 'c', 'd', 'e'] 

# insert z at the front of the list
list2.insert(0, 'z')
print(list2)
```

**输出:**

```py
[1, 2, 3, 4, 10, 5, 6, 7]
['z', 'a', 'b', 'c', 'd', 'e']
```

### **例 2:**insert()方法错误

## 蟒蛇 3

```py
# Python3 program for error  
# of insert() method 

# attribute error 
string = "1234567"

string.insert(10, 1)
print(string)
```

**输出:**

```py
Traceback (most recent call last):
  File "/home/2fe54bd8723cd0ae89a17325da8b2eb5.py", line 7, in 
    string.insert(10, 1)
AttributeError: 'str' object has no attribute 'insert'
```

### **示例 3:** 在任何元素之前插入列表

## 蟒蛇 3

```py
# Python3 program for Insertion in a list  
# before any element using insert() method 

list1 = [ 1, 2, 3, 4, 5, 6 ]

# Element to be inserted 
element = 13 

# Element to be inserted before 3
beforeElement = 3 

# Find index
index = list1.index(beforeElement) 

# Insert element at beforeElement 
list1.insert(index, element) 
print(list1)
```

**输出:**

```py
[1, 2, 13, 3, 4, 5, 6]
```

### **示例 4:** 将元组插入列表

## 蟒蛇 3

```py
list1 = [ 1, 2, 3, 4, 5, 6 ]

# tuple of numbers
num_tuple = (4, 5, 6)

# inserting a tuple to the list
list1.insert(2, num_tuple)

print(list1)
```

**输出:**

```py
[1, 2, (4, 5, 6), 3, 4, 5, 6]
```