# Python–K 值的下 N 个元素

> 原文:[https://www . geesforgeks . org/python-next-n-elements-from-k-value/](https://www.geeksforgeeks.org/python-next-n-elements-from-k-value/)

给定一个列表，从列表中 K 值的出现获得下一个 N 值。

> **输入** : test_list = [3，4，6，7，8，4，7，2，1，8，4，2，3，9]，N = 1，K = 4
> **输出**:【6，7，2】
> **解释**:所有连续的元素到 4 都提取为 N = 1。
> 
> **输入** : test_list = [3，4，6，7，8，4，7，2，1，8，4，2，3，9]，N = 2，K = 7
> **输出**:【8，4，2，1】
> **解释**:提取每次出现 7 后的两个元素。

**方法一:使用列表理解+切片**

在这种情况下，我们使用列表理解来提取所有索引，然后使用循环来附加元素，并从列表中期望的 K 值出现中作为单个字符串加入。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Next N elements of K value
# Using list comprehension + slicing

# initializing list
test_list = [3, 4, 6, 7, 8, 4, 7, 2, 1, 8, 4, 2, 3, 9]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 4

# initializing N
N = 2

# getting indices of K
temp = [idx for idx in range(len(test_list)) if test_list[idx] == K]

# getting next N elements from K using loop
res = []
for ele in temp:

    # appending slice
    res.extend(test_list[ele + 1: ele + N + 1])

# printing result
print("Constructed Result List : " + str(res))
```

**Output**

```py
The original list is : [3, 4, 6, 7, 8, 4, 7, 2, 1, 8, 4, 2, 3, 9]
Constructed Result List : [6, 7, 7, 2, 2, 3]

```

**方法 2:使用滤波器()+λ+环路**

这类似于上述方法，区别在于使用 filter()和 lambda 函数来执行索引的过滤。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Next N elements of K value
# Using filter() + lambda + loop

# initializing list
test_list = [3, 4, 6, 7, 8, 4, 7, 2, 1, 8, 4, 2, 3, 9]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 4

# initializing N
N = 2

# getting indices of K
# using filter() and lambda
temp = list(filter(lambda ele: test_list[ele] == K, range(len(test_list))))

# getting next N elements from K using loop
res = []
for ele in temp:

    # appending slice
    res.extend(test_list[ele + 1: ele + N + 1])

# printing result
print("Constructed Result List : " + str(res))
```

**Output**

```py
The original list is : [3, 4, 6, 7, 8, 4, 7, 2, 1, 8, 4, 2, 3, 9]
Constructed Result List : [6, 7, 7, 2, 2, 3]

```