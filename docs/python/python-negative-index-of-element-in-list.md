# Python–列表中元素的负索引

> 原文:[https://www . geesforgeks . org/python-列表中元素的负索引/](https://www.geeksforgeeks.org/python-negative-index-of-element-in-list/)

给定一个元素列表，在列表中找到它的负索引。

> **输入** : test_list = [5，7，8，2，3，5，1]，K = 2
> **输出** : -4
> **说明** : 2 是从后数第 4 个元素。
> 
> **输入** : test_list = [5，7，8，2，3，5，1]，K = 5
> **输出** : -2
> **说明** : 5 是从后数第 2 个元素。

**方法#1:使用** [**指数()**](https://www.geeksforgeeks.org/python-list-index/)**+**[**len()**](https://www.geeksforgeeks.org/python-string-length-len/)

在这种情况下，我们使用 index()获取元素的索引，然后从列表长度中减去它，以获得所需的结果。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Negative index of Element
# Using index() + len()

# initializing list
test_list = [5, 7, 8, 2, 3, 5, 1]

# printing original list
print("The original list is : " + str(test_list))

# initializing Element
K = 3

# getting length using len() and subtracting index from it
res = len(test_list) - test_list.index(K)

# printing result
print("The required Negative index : -" + str(res))
```

**输出:**

```py
The original list is : [5, 7, 8, 2, 3, 5, 1]
The required Negative index : -3
```

**方法 2:使用~运算符+** [**列表切片**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) **+索引()**

在这种情况下，我们使用切片来反转列表，并使用~运算符来获得否定，使用 index()来获得所需的否定索引。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Negative index of Element
# Using ~ operator + list slicing + index()

# initializing list
test_list = [5, 7, 8, 2, 3, 5, 1]

# printing original list
print("The original list is : " + str(test_list))

# initializing Element
K = 3

# -1 operator to reverse list, index() used to get index
res = ~test_list[::-1].index(K)

# printing result
print("The required Negative index : " + str(res))
```

**输出:**

```py
The original list is : [5, 7, 8, 2, 3, 5, 1]
The required Negative index : -3
```