# Python–元组中的最大和最小 K 个元素

> 原文:[https://www . geesforgeks . org/python-最大和最小 k 元素元组/](https://www.geeksforgeeks.org/python-maximum-and-minimum-k-elements-in-tuple/)

有时，在处理元组时，我们可能会遇到只需要提取极端的 K 元素的问题，即元组中的最大和最小 K 元素。这个问题可能会出现在网络开发和数据科学等领域。让我们讨论一下解决这个问题的某些方法。

> **输入** : test_tup = (3，7，1，18，9)，k = 2
> **输出** : (3，1，9，18)
> **输入** : test_tup = (3，7，1)，k=1
> **输出** : (1，3)

**方法#1:使用 sorted() + loop**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 sorted()执行排序操作，并使用 loop 解决最大和最小 K 元素的提取问题。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Maximum and Minimum K elements in Tuple
# Using sorted() + loop

# initializing tuple
test_tup = (5, 20, 3, 7, 6, 8)

# printing original tuple
print("The original tuple is : " + str(test_tup))

# initializing K
K = 2

# Maximum and Minimum K elements in Tuple
# Using sorted() + loop
res = []
test_tup = list(sorted(test_tup))

for idx, val in enumerate(test_tup):
    if idx < K or idx >= len(test_tup) - K:
        res.append(val)
res = tuple(res)

# printing result
print("The extracted values : " + str(res))
```

**Output : **

```
The original tuple is : (5, 20, 3, 7, 6, 8)
The extracted values : (3, 5, 8, 20)
```

**方法 2:使用列表切片+排序()**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用切片而不是强力循环逻辑来执行最大、最小提取任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Maximum and Minimum K elements in Tuple
# Using slicing + sorted()

# initializing tuple
test_tup = (5, 20, 3, 7, 6, 8)

# printing original tuple
print("The original tuple is : " + str(test_tup))

# initializing K
K = 2

# Maximum and Minimum K elements in Tuple
# Using slicing + sorted()
test_tup = list(test_tup)
temp = sorted(test_tup)
res = tuple(temp[:K] + temp[-K:])

# printing result
print("The extracted values : " + str(res))
```

**Output : **

```
The original tuple is : (5, 20, 3, 7, 6, 8)
The extracted values : (3, 5, 8, 20)
```