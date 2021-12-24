# Python–产生 K 个均匀间隔的浮点值

> 原文:[https://www . geesforgeks . org/python-product-k-等间距-float-values/](https://www.geeksforgeeks.org/python-produce-k-evenly-spaced-float-values/)

给定一个范围和元素 K，生成均匀间隔的 K 个浮点值。

> **输入** : i = 4，j = 6，K = 10
> 
> **输出**:【4.2、4.4、4.6、4.8、5.0、5.2、5.4、5.6、5.8、6.0】
> 
> **说明**:4 后加差 0.2 产生 10 个元素直到 6。
> 
> **输入** : i = 10，j = 20，K = 2
> 
> **输出**:【15.0，20.0】
> 
> **说明** : 5 是差，每次加。

**方法#1:使用循环**

这是执行这项任务的方法之一。在这种情况下，我们迭代直到 K，同时增加连续元素之间差异的计数器。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Produce K evenly spaced float values
# Using loop

# initializing range
i, j = 2, 10

# Initialize K
K = 15

# computing difference
diff = (j - i) / K
res = []

# using loop to add numbers to result
for idx in range(1, K + 1):
    res.append(i + (diff * idx))

# printing result
print("The constructed list : " + str(res))
```

**Output**

> 构建的列表:[2.53333333333333333，3.06666666666，3.6，4.133333333333，4.66666666666，5.2，5.7333，6.2666666667

**方法 2:使用列表理解**

这种方法的工作原理与上述方法相似。不同之处在于使用列表理解来制定解决方案的简洁方式。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Produce K evenly spaced float values
# Using loop

# initializing range
i, j = 2, 10

# Initialize K
K = 15

# computing difference
diff = (j - i) / K

# using list comprehension to formulate elements
res = [i + (diff * idx) for idx in range(1, K + 1)]

# printing result
print("The constructed list : " + str(res))
```

**Output**

> 构建的列表:[2.53333333333333333，3.06666666666，3.6，4.133333333333，4.66666666666，5.2，5.7333，6.2666666667