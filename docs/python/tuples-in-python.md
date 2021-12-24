# Python 中的元组

> 原文:[https://www.geeksforgeeks.org/tuples-in-python/](https://www.geeksforgeeks.org/tuples-in-python/)

元组是由逗号分隔的 Python 对象的集合。在某些方面，元组在索引、嵌套对象和重复方面类似于列表，但是元组是不可变的，不像列表是可变的。

**创建元组**

```py
# An empty tuple
empty_tuple = ()
print (empty_tuple)
```

输出:

```py
 ()
```

```py
# Creating non-empty tuples

# One way of creation
tup = 'python', 'geeks'
print(tup)

# Another for doing the same
tup = ('python', 'geeks')
print(tup)
```

输出

```py
('python', 'geeks')
('python', 'geeks')
```

*注意:如果你用单个元素生成一个元组，请确保在元素后添加一个逗号。*

**元组的串联**

```py
# Code for concatenating 2 tuples

tuple1 = (0, 1, 2, 3)
tuple2 = ('python', 'geek')

# Concatenating above two
print(tuple1 + tuple2)
```

输出:

```py
(0, 1, 2, 3, 'python', 'geek')
```

**元组的嵌套**

```py
# Code for creating nested tuples

tuple1 = (0, 1, 2, 3)
tuple2 = ('python', 'geek')
tuple3 = (tuple1, tuple2)
print(tuple3)
```

输出:

```py
((0, 1, 2, 3), ('python', 'geek'))
```

**元组中的重复**

```py
# Code to create a tuple with repetition

tuple3 = ('python',)*3
print(tuple3)
```

输出

```py
 ('python', 'python', 'python')
```

尝试上面没有逗号和检查。您将获得字符串形式的 tuple 3“python typhoontyson”。

**不可变元组**

```py
#code to test that tuples are immutable

tuple1 = (0, 1, 2, 3)
tuple1[0] = 4
print(tuple1)
```

输出

```py
Traceback (most recent call last):
  File "e0eaddff843a8695575daec34506f126.py", line 3, in
    tuple1[0]=4
TypeError: 'tuple' object does not support item assignment
```

**元组切片**

```py
# code to test slicing

tuple1 = (0 ,1, 2, 3)
print(tuple1[1:])
print(tuple1[::-1])
print(tuple1[2:4])
```

输出

```py
(1, 2, 3)
(3, 2, 1, 0)
(2, 3)
```

**删除元组**

```py
# Code for deleting a tuple

tuple3 = ( 0, 1)
del tuple3
print(tuple3)
```

错误:

```py
Traceback (most recent call last):
  File "d92694727db1dc9118a5250bf04dafbd.py", line 6, in <module>
    print(tuple3)
NameError: name 'tuple3' is not defined
```

输出:

```py
(0, 1)
```

**查找元组长度**

```py
# Code for printing the length of a tuple

tuple2 = ('python', 'geek')
print(len(tuple2))
```

输出

```py
 2
```

**将列表转换为元组**

```py
# Code for converting a list and a string into a tuple

list1 = [0, 1, 2]
print(tuple(list1))
print(tuple('python')) # string 'python'
```

输出

```py
(0, 1, 2)
('p', 'y', 't', 'h', 'o', 'n')
```

接受单个参数，可以是列表、字符串、集合甚至字典(只有键被视为元素)，并将它们转换为元组。

**循环中的元组**

```py
#python code for creating tuples in a loop

tup = ('geek',)
n = 5  #Number of time loop runs
for i in range(int(n)):
    tup = (tup,)
    print(tup)
```

输出:

```py
(('geek',),)
((('geek',),),)
(((('geek',),),),)
((((('geek',),),),),)
(((((('geek',),),),),),)

```

**使用 cmp()、max()、min()**

```py
# A python program to demonstrate the use of 
# cmp(), max(), min()

tuple1 = ('python', 'geek')
tuple2 = ('coder', 1)

if (cmp(tuple1, tuple2) != 0):

    # cmp() returns 0 if matched, 1 when not tuple1 
    # is longer and -1 when tuple1 is shoter
    print('Not the same')
else:
    print('Same')
print ('Maximum element in tuples 1,2: ' + 
        str(max(tuple1)) +  ',' + 
        str(max(tuple2)))
print ('Minimum element in tuples 1,2: ' + 
     str(min(tuple1)) + ','  + str(min(tuple2)))
```

输出

```py
Not the same
Maximum element in tuples 1,2: python,coder
Minimum element in tuples 1,2: geek,1

```

*注意:max()和 min()根据 ASCII 值检查。如果元组中有两个字符串，则检查字符串中的第一个不同字符。*

本文由斯里·桑凯·乌帕拉帕蒂供稿。如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。