# Python–改造 K 位元素

> 原文:[https://www . geeksforgeeks . org/python-reform-k-digit-elements/](https://www.geeksforgeeks.org/python-reform-k-digit-elements/)

给定 Python 列表，将元素改革为在单个元素中有 K 个数字。

> **输入**:test _ list =【223，67，332，1，239，2，931】，K = 2
> **输出**:【22，36，73，32，12，39，29，31】
> **解释**:元素重组为每个元素分配 2 位数字。
> 
> **输入**:test _ list =【223，67，3327】，K = 3
> **输出**:【223，673，327】
> **解释**:元素重组为每个元素分配 3 位数字。

**方法#1:使用** [**切片**](https://www.geeksforgeeks.org/string-slicing-in-python/) **+** [**连接()**](https://www.geeksforgeeks.org/join-function-python/) **+循环**

在这种情况下，我们执行将所有元素连接到单个字符串的任务，然后对 K 个数字进行切片，并重新转换到列表。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Reform K digit elements
# Using slicing + join() + loop

# initializing list
test_list = [223, 67, 332, 1, 239, 2, 931]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 2

# converting to string
temp = ''.join([str(ele) for ele in test_list])

# getting K digit slices
res = []
for idx in range(0, len(temp), K):
    res.append(int(temp[idx: idx + K]))

# printing result
print("Reforming K digits : " + str(res))
```

**Output**

```py
The original list is : [223, 67, 332, 1, 239, 2, 931]
Reforming K digits : [22, 36, 73, 32, 12, 39, 29, 31]

```

**方法二:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) **+加入()**

在这种情况下，使用列表理解来完成改革列表的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Reform K digit elements
# Using list comprehension + join()

# initializing list
test_list = [223, 67, 332, 1, 239, 2, 931]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 2

# converting to string
temp = ''.join([str(ele) for ele in test_list])

# getting K digit slices
# using 1 liner list comprehension
res = [int(temp[idx: idx + K]) for idx in range(0, len(temp), K)]

# printing result
print("Reforming K digits : " + str(res))
```

**Output**

```py
The original list is : [223, 67, 332, 1, 239, 2, 931]
Reforming K digits : [22, 36, 73, 32, 12, 39, 29, 31]

```