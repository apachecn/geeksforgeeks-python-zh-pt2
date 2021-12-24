# Python 程序向右旋转列表 n 次

> 原文:[https://www . geesforgeks . org/python-program-right-rotate-list-n/](https://www.geeksforgeeks.org/python-program-right-rotate-list-n/)

给定一个列表，将列表向右旋转 n 个位置。

**例:**

```
Input : n = 2 
         List_1 = [1, 2, 3, 4, 5, 6]
Output : List_1 = [5, 6, 1, 2, 3, 4]
We get output list after right rotating 
(clockwise) given list by 2.

Input :  n = 3
         List_1 = [3, 0, 1, 4, 2, 3]
Output : List_1 = [4, 2, 3, 3, 0, 1]
```

**方法#1 :** 逐个遍历第一个列表，然后将元素放在第二个列表中所需的位置。

## 蟒蛇 3

```
# Python program to right rotate a list by n

# Returns the rotated list

def rightRotate(lists, num):
    output_list = []

    # Will add values from n to the new list
    for item in range(len(lists) - num, len(lists)):
        output_list.append(lists[item])

    # Will add the values before
    # n to the end of new list
    for item in range(0, len(lists) - num):
        output_list.append(lists[item])

    return output_list

# Driver Code
rotate_num = 3
list_1 = [1, 2, 3, 4, 5, 6]

print(rightRotate(list_1, rotate_num))
```

**输出:**

```
[4, 5, 6, 1, 2, 3]
```

**时间复杂度:O(n)**

**方法 2 :** 使用*切片技术*解决此问题的另一种方法。切片列表的一种方法是使用 **len()** 方法。

## 蟒 3

```
# Python program to right rotate
# a list by n using list slicing
n = 3

list_1 = [1, 2, 3, 4, 5, 6]
list_1 = (list_1[len(list_1) - n:len(list_1)]
                 + list_1[0:len(list_1) - n])
print(list_1)
```

**输出:**

```
[4, 5, 6, 1, 2, 3]
```

**方法#3 :** 在上述方法中，取 list_1 的最后 n 个元素，然后取 list_1 的剩余元素。另一种方法是不使用 len()方法。

## 蟒蛇

```
# Right Rotating a list to n positions
n = 8

list_1 = [1, 2, 3, 4, 5, 6]
if n>len(list_1):
    n = int(n%len(list_1))
list_1 = (list_1[-n:] + list_1[:-n])

print(list_1)
```

**输出:**

```
[4, 5, 6, 1, 2, 3]
```

**时间复杂度:O(n)**

**注意:** list_1[:]将返回整个列表，因为切片运算符左边的空格指的是列表的开始位置，即 0，右边的空格指的是列表的结束位置。