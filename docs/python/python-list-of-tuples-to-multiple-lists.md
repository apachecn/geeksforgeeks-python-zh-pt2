# Python–元组列表到多个列表

> 原文:[https://www . geesforgeks . org/python-元组到多列表列表/](https://www.geeksforgeeks.org/python-list-of-tuples-to-multiple-lists/)

在本文中，我们将讨论如何将元组列表转换为多个列表。我们可以使用 [map()](https://www.geeksforgeeks.org/python-map-function/) 函数将元组列表转换为多个列表

> **语法** : map(list，zip(* list _ of _ 元组)

**示例:**

```py
Input: [('a', 'b', 'c'), (1,2,3), ('1','3','4')]
Output: ['a', 'b', 'c'], [1, 2, 3], ('1', '3', '4')
```

**示例 1:** 显示元组列表并显示的 Python 代码。

## 蟒蛇 3

```py
# list of tuple for student data
# with both integer and strings
a = [(1, 2,3,4,5),
     ("sravan","bobby","ojaswi","rohith","Gnanesh"), 
     (96,89,78,90,78)]

# display
print("Original list of tuple")
print(a)

# list of tuple for student data 
# with both integer and strings
a = [(1, 2,3,4,5),
     ("sravan","bobby","ojaswi","rohith","Gnanesh"),
     (96,89,78,90,78)]

# convert list of tuple to multiple lists
data = map(list, zip(*a))

print("")

# display 
print("List")
for i in data:
  print(i)
```

**输出:**

> 元组的原始列表
> 
> [(1，2，3，4，5)[“范”、“巴比”、“奥哈撒维”、“罗希”、“纳尼什”](96，89，78，90，78)]
> 
> 目录
> 
> [1，' sravan '，96]
> 
> [2，'鲍比'，89]
> 
> [3，' ojaswi '，78]
> 
> [4，' rohith '，90]
> 
> [5，‘Gnanesh’，78]

**示例 2:** 将元组列表转换为多个列表的 Python 代码

## 蟒蛇 3

```py
# list of tuple for student
# data with both integer and strings
a = [(1, 2,3,4,5), 
     ("sravan","bobby","ojaswi","rohith","Gnanesh"),
     (96,89,78,90,78),
     ("kakumanu","kakumanu","hyd","hyd","hyd")]

# convert list of tuple to multiple lists
data = map(list, zip(*a))

# display 
for i in data:
  print(i)
```

**输出:**

```py
[1, 'sravan', 96, 'kakumanu']
[2, 'bobby', 89, 'kakumanu']
[3, 'ojaswi', 78, 'hyd']
[4, 'rohith', 90, 'hyd']
[5, 'Gnanesh', 78, 'hyd']
```