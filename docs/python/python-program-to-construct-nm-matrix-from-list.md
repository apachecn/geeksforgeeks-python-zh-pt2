# Python 程序从列表中构造 n*m 矩阵

> 原文:[https://www . geesforgeks . org/python-程序到构造-nm-矩阵从列表/](https://www.geeksforgeeks.org/python-program-to-construct-nm-matrix-from-list/)

给定一个列表，任务是编写一个可以构造 n*m 矩阵的 python 程序。

> **输入** : test_list = [6，3，7，2，6，8，4，3，9，2，1，3]，n，m = 3，5
> **输出**:【矩阵不可能】
> **解释** : List 有 12 个元素，3*5 是 15，因此矩阵不可能。
> 
> **输入** : test_list = [6，3，7，2，6，8]，n，m = 2，3
> **输出** : [[6，3，7]，[2，6，8]]
> **解释** : List 转换为 2*3 矩阵。

**方法:** *使用* [*嵌套循环*](https://www.geeksforgeeks.org/loops-in-python/)

n*m 的约束将列表的大小严格限制为 n*m。实现这一点后，我们可以使用嵌套循环来分配适当的行和列。

**例 1:**

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Construct n*m Matrix from List
# Using loop

# initializing list
test_list = [6, 3, 7, 2, 6, 8, 4, 3, 9, 2, 1, 3]

# printing original list
print("The original list is : " + str(test_list))

# initializing n, m
n, m = 3, 4

k = 0
res = []
if n*m != len(test_list):

    # checking if Matrix Possible
    res = "Matrix Not Possible"
else:

    # Constructing Matrix
    for idx in range(0, n):
        sub = []
        for jdx in range(0, m):
            sub.append(test_list[k])
            k += 1
        res.append(sub)

# printing result
print("Constructed Matrix : " + str(res))
```

**输出:**

> 原来的名单是:[6，3，7，2，6，8，4，3，9，2，1，3]
> 
> 构造矩阵:[[6，3，7，2]，[6，8，4，3]，[9，2，1，3]]

**例 2 :**

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Construct n*m Matrix from List
# Using loop

# initializing list
test_list = [6, 3, 7, 2, 6, 8, 4, 3, 9, 2, 1, 3]

# printing original list
print("The original list is : " + str(test_list))

# initializing n, m
n, m = 5, 4

k = 0
res = []

# n*m == 20 > length, hence result not possible.
if n*m != len(test_list):

    # checking if Matrix Possible
    res = "Matrix Not Possible"
else:

    # Constructing Matrix
    for idx in range(0, n):
        sub = []
        for jdx in range(0, m):
            sub.append(test_list[k])
            k += 1
        res.append(sub)

# printing result
print("Constructed Matrix : " + str(res))
```

**输出:**

> 原来的名单是:[6，3，7，2，6，8，4，3，9，2，1，3]
> 
> 构造矩阵:矩阵不可能