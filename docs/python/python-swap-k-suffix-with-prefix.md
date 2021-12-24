# Python–用前缀

交换 K 后缀

> 原文:[https://www . geesforgeks . org/python-swap-k-后缀加前缀/](https://www.geeksforgeeks.org/python-swap-k-suffix-with-prefix/)

给定一个列表，执行 K 前缀和后缀的交换。

**示例:**

> **输入** : test_list = [5，6，3，1，0，1，3，5，7，9]，K = 2
> **输出** : [7，9，3，1，0，1，3，5，5，6]
> **解释**:后置 2 和前置 2 元素互换。
> 
> **输入** : test_list = [5，6，3，1，0，1，3，5，7，9]，K = 1
> **输出** : [9，6，3，1，0，1，3，5，7，5]
> **解释**:后置 1 和前置 1 元素互换。

**方法#1:使用切片和范围交换**

在本文中，我们使用列表切片来执行获取所需切片的任务，并执行范围交换来交换元素。这是解决这个问题的就地方法。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Swap K suffix with prefix
# Using range swap + slice()

# initializing list
test_list = [5, 6, 3, 1, 0, 1, 3, 5, 7, 9]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 3

# performing range swap
test_list[:K], test_list[len(
    test_list) - K:] = test_list[len(test_list) - K:], test_list[:K]

# printing result
print("After prefix suffix swap : " + str(test_list))
```

**Output**

```py
The original list is : [5, 6, 3, 1, 0, 1, 3, 5, 7, 9]
After prefix suffix swap : [5, 7, 9, 1, 0, 1, 3, 5, 6, 3]

```

**方法 2:使用切片符号**

在这种情况下，我们使用切片来执行列表元素的重建，每个列表执行切片。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Swap K suffix with prefix
# Using slice notation

# initializing list
test_list = [5, 6, 3, 1, 0, 1, 3, 5, 7, 9]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 3

# joining parts using slice
res = test_list[len(test_list) - K:] + \
    test_list[K: len(test_list) - K] + test_list[:K]

# printing result
print("After prefix suffix swap : " + str(res))
```

**Output**

```py
The original list is : [5, 6, 3, 1, 0, 1, 3, 5, 7, 9]
After prefix suffix swap : [5, 7, 9, 1, 0, 1, 3, 5, 6, 3]

```