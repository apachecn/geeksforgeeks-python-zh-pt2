# Python 程序将列表转换成矩阵，每行的大小增加一个数字

> 原文:[https://www . geesforgeks . org/python-program-to-convert-a-list-to-matrix-with-size-每行按数字递增/](https://www.geeksforgeeks.org/python-program-to-convert-a-list-into-matrix-with-size-of-each-row-increasing-by-a-number/)

给定一个列表和一个数字 N，这里的任务是编写一个 python 程序将其转换为矩阵，其中每行比列表中的前一行元素多 N 个元素。

> **输入:** test_list = [4，6，8，1，2，9，0，10，12，3，9，1]，N = 3
> 
> **输出:** [[4，6，8]，[4，6，8，1，2，9]，[4，6，8，1，2，9，0，10，12]，[4，6，8，1，2，9，0，10，12，3，9，1]]
> 
> **说明**:每行比上一行多 3 个元素。
> 
> **输入:** test_list = [4，6，8，1，2，9，0，10，12，3，9，1]，N = 4
> 
> **输出:** [[4，6，8，1]，[4，6，8，1，2，9，0，10]，[4，6，8，1，2，9，0，10，12，3，9，1]]
> 
> **说明:**每行比上一行多 4 个元素。

**方法 1 :** *使用* [*循环*](https://www.geeksforgeeks.org/python-for-loops/) *和* [*切片*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，我们使用切片来执行获取块的任务，并且使用循环来完成列表到矩阵的转换。

**程序:**

## 蟒蛇 3

```py
# initializing list
test_list = [4, 6, 8, 1, 2, 9, 0, 10, 12, 3, 9, 1]

# printing original list
print("The original list is : " + str(test_list))

# initializing N
N = 3

res = []
for idx in range(0, len(test_list) // N):

    # getting incremented chunks
    res.append(test_list[0: (idx + 1) * N])

# printing result
print("Constructed Chunk Matrix : " + str(res))
```

**输出:**

> 原来的名单是:[4，6，8，1，2，9，0，10，12，3，9，1]
> 
> 构造块矩阵:[[4，6，8]，[4，6，8，1，2，9]，[4，6，8，1，2，9，0，10，12]，[4，6，8，1，2，9，0，10，12，3，9，1]]

**方法二:** *使用* [*列表理解和列表切片*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在本文中，我们使用列表理解作为速记来执行设置值的任务。其余所有操作都与上述方法类似。

**程序:**

## 蟒蛇 3

```py
# initializing list
test_list = [4, 6, 8, 1, 2, 9, 0, 10, 12, 3, 9, 1]

# printing original list
print("The original list is : " + str(test_list))

# initializing N
N = 3

# getting incremented chunks
# using list comprehension as shorthand
res = [test_list[0: (idx + 1) * N] for idx in range(0, len(test_list) // N)]

# printing result
print("Constructed Chunk Matrix : " + str(res))
```

**输出:**

> 原来的名单是:[4，6，8，1，2，9，0，10，12，3，9，1]
> 
> 构造块矩阵:[[4，6，8]，[4，6，8，1，2，9]，[4，6，8，1，2，9，0，10，12]，[4，6，8，1，2，9，0，10，12，3，9，1]]