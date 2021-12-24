# Python 列表索引()

> 原文:[https://www.geeksforgeeks.org/python-list-index/](https://www.geeksforgeeks.org/python-list-index/)

***【index()***是 Python 中的一个内置函数，它从列表的开头开始搜索给定的元素，并返回该元素出现的最低索引。

> **语法:**
> 
> list_name.index(元素，开始，结束)
> 
> **参数:**
> 
> *   **元素**–将返回其最低索引的元素。
> *   **开始** *(可选)*–搜索开始的位置。
> *   **结束** *(可选)*–搜索结束的位置。
> 
> **返回:**
> 
> 返回元素出现的最低索引。
> 
> **错误:**
> 
> 如果搜索任何不存在的元素，它将返回一个 ValueError

### **例 1:** 求元素的索引

## 蟒蛇 3

```
# Python3 program for demonstration  
# of list index() method

list1 = [1, 2, 3, 4, 1, 1, 1, 4, 5]

# Will print the index of '4' in list1
print(list1.index(4))

list2 = ['cat', 'bat', 'mat', 'cat', 'pet']

# Will print the index of 'cat' in list2 
print(list2.index('cat'))
```

**输出:**

```
3
0
```

**例 1.1**

## 蟒蛇 3

```
# Python3 program for demonstration 
# of index() method

list1 = [1, 2, 3, 4, 1, 1, 1, 4, 5]

# Will print index of '4' in sublist
# having index from 4 to 8.
print(list1.index(4, 4, 8))

# Will print index of '1' in sublist
# having index from 1 to 7.
print(list1.index(1, 1, 7))

list2 = ['cat', 'bat', 'mat', 'cat', 
         'get', 'cat', 'sat', 'pet']

# Will print index of 'cat' in sublist
# having index from 2 to 6
print(list2.index('cat', 2, 6 ))
```

**输出:**

```
7
4
3
```

**例 1.2**

## 蟒蛇 3

```
# Python3 program for demonstration 
# of list index() method

# Random list having sublist and tuple also
list1 = [1, 2, 3, [9, 8, 7], ('cat', 'bat')]

# Will print the index of sublist [9, 8, 7]
print(list1.index([9, 8, 7]))

# Will print the index of tuple 
# ('cat', 'bat') inside list 
print(list1.index(('cat', 'bat')))
```

**输出:**

```
3
4
```

### **示例 2:** 列表中不存在的元素的索引(值错误)

## 蟒蛇 3

```
# Python3 program for demonstration
# of index() method error

list1 = [1, 2, 3, 4, 1, 1, 1, 4, 5]

# Return ValueError
print(list1.index(10))
```

**输出:**

```
Traceback (most recent call last):
  File "/home/b910d8dcbc0f4f4b61499668654450d2.py", line 8, in 
    print(list1.index(10))
ValueError: 10 is not in list
```

### **示例 3:** 当传递 2 个参数时

当在索引函数中传递两个参数时，第一个参数被视为要搜索的元素，第二个参数是搜索开始的索引。

```
list_name.index(element, start)
```

## 蟒蛇 3

```
# Python3 program for demonstration 
# of index() method

list1 = [6 , 8 , 5 , 6 , 1 , 2]

# Will print index of '3' in sublist
# having index from 1 to end of the list.
print(list1.index(6 , 1))
```

**输出:**

```
3
```

### 示例 4:不包括作为参数传递的结束索引

第三个参数是结束，它本身不包含在从开始到结束的范围内，即搜索从开始到结束进行-1 索引。

## 蟒蛇 3

```
# Python3 program for demonstration 
# of index() method

list1 = [6 , 2 , 14 , 8 , 9 , 10]

# return error as index '4' is not included in the range 
# having index from 1 to 4.
print(list1.index(9, 1, 4))
```

**输出:**

```
Traceback (most recent call last):
  File "/home/3cbe5b7d0595ab3f8564f16af7a15172.py", line 9, in <module>
    print(list1.index(9 , 1 , 4))
ValueError: 9 is not in list
```

**例 4.1**

## 蟒蛇 3

```
# Python3 program for demonstration 
# of index() method

list1 = [6 , 2 , 14 , 8 , 9 , 10]

# Will print index of '4' in sublist as now index '4' is included 
# having index from 1 to 5.
print(list1.index(9, 1, 5))
```

**输出:**

```
4
```