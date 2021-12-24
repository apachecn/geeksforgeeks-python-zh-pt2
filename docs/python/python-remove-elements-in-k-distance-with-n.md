# Python–用 N 去除 K 距离内的元素

> 原文:[https://www . geesforgeks . org/python-remove-elements-in-k-distance-with-n/](https://www.geeksforgeeks.org/python-remove-elements-in-k-distance-with-n/)

给定一个列表，用 n 移除 K 距离内的所有元素

> **输入** : test_list = [4，5，9，1，10，6，13 ]，K = 3，N = 5
> **输出** : [9，1，10，13]
> **解释** : 4 去掉为 5–4 = 1<3，因此其在距离之内。
> 
> **输入** : test_list = [1，10，6，13 ]，K = 3，N = 5
> **输出** : [1，10，13]
> **解释** : 4 作为 5–4 = 1<3 移除，因此其在距离内。

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，我们使用列表理解进行比较，只提取那些在安全距离 K 到 N 的元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Remove Elements in K distance with N
# Using list comprehension

# initializing list
test_list = [4, 5, 9, 1, 10, 6, 13 ]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 3

# initializing N 
N = 5

# checking for elements in safe zone with respect to N
res = [ele for ele in test_list if ele < N - K or ele > N + K]

# printing result 
print("Filtered elements : " + str(res))
```

**Output**

```py
The original list is : [4, 5, 9, 1, 10, 6, 13]
Filtered elements : [9, 1, 10, 13]

```

**方法 2:使用** [**滤镜()**](https://www.geeksforgeeks.org/filter-in-python/)**+**[**λ**](https://www.geeksforgeeks.org/python-lambda/)

在这种情况下，使用 filter()和 lambda 函数完成过滤任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Remove Elements in K distance with N
# Using filter() + lambda

# initializing list
test_list = [4, 5, 9, 1, 10, 6, 13 ]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 3

# initializing N 
N = 5

# checking for elements in safe zone with respect to N
res = list(filter(lambda ele : ele < N - K or ele > N + K, test_list))

# printing result 
print("Filtered elements : " + str(res))
```

**Output**

```py
The original list is : [4, 5, 9, 1, 10, 6, 13]
Filtered elements : [9, 1, 10, 13]

```