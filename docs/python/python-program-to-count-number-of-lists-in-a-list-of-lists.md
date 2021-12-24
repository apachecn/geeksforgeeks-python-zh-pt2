# Python |计算列表列表中列表数量的程序

> 原文:[https://www . geesforgeks . org/python-程序对列表中列表的计数数/](https://www.geeksforgeeks.org/python-program-to-count-number-of-lists-in-a-list-of-lists/)

给定一个列表，编写一个 Python 程序来计算列表中包含的列表数量。

**示例:**

```py
Input :  [[1, 2, 3], [4, 5], [6, 7, 8, 9]]
Output : 3

Input : [[1], ['Bob'], ['Delhi'], ['x', 'y']]
Output : 4

```

**方法#1 :** 使用 *len()*

```py
# Python3 program to Count number 
# of lists in a list of lists

def countList(lst):
    return len(lst)

# Driver code
lst = [[1, 2, 3], [4, 5], [6, 7, 8, 9]]
print(countList(lst))
```

**Output:**

```py
3

```

**方法 2 :** 使用*类型()*

在每次迭代中使用 for 循环来检查当前项的类型是否是列表，并相应地增加“计数”变量。这种方法比方法#1 有好处，因为它适用于异构元素列表。

```py
# Python3 program to Count number 
# of lists in a list of lists

def countList(lst):
    count = 0
    for el in lst:
        if type(el)== type([]):
            count+= 1

    return count

# Driver code
lst = [[1, 2, 3], [4, 5], [6, 7, 8, 9]]
print(countList(lst))
```

**Output:**

```py
3

```

上述代码的单行替代方法如下所示:

```py
def countList(lst):
    return sum(type(el)== type([]) for el in lst)
```

**方法#3 :** 使用*方法*

```py
# Python3 program to Count number 
# of lists in a list of lists

def countList(lst):
    return sum(isinstance(i, list) for i in lst)

# Driver code
lst = [[1, 2, 3], [4, 5], [6, 7, 8, 9]]
print(countList(lst))
```

**Output:**

```py
3

```