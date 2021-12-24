# 测试行的长度是否按递增顺序排列的 Python 程序

> 原文:[https://www . geeksforgeeks . org/python-要测试的程序-行的长度是否按递增顺序排列/](https://www.geeksforgeeks.org/python-program-to-test-whether-the-length-of-rows-are-in-increasing-order/)

给定一个矩阵，下面的程序用来测试一个矩阵的所有行的长度是否是递增的。如果是，则返回真，否则返回假。

> **输入** : test_list = [[3]，[1，7]，[10，2，4]，[8，6，5，1，4]]
> **输出** : True
> **解释** : 1 < 2 < 3 < 5，增加行数，因此为 True。
> **输入** : test_list = [[3]，[1，7]，[10]，[8，6，5，1，4]]
> **输出** : False
> **解释** : 1 < 2 > 1 < 5，行的长度不增加，因此为 False。

**方法 1 :** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/) *和* [*len()*](https://www.geeksforgeeks.org/python-string-length-len/#:~:text=len()%20function%20is%20an, the%20length%20of%20the%20string.&text=Parameters%3A, takes%20string%20as%20the%20parameter.)

在这种情况下，我们使用循环来检查下一行的长度是否大于当前行的长度，如果不是，结果将被标记为关闭。

## 蟒蛇 3

```
# initializing list
test_list = [[3], [1, 7], [10, 2, 4], [8, 6, 5, 1, 4]]

# printing original list
print("The original list is : " + str(test_list))

res = True 
for idx in range(len(test_list) - 1) :

    # flag off in case next length is not greater
    # than current
    if len(test_list[idx + 1]) <= len(test_list[idx]):
        res = False 
        break

# printing result 
print("Are rows of increasing lengths ? : " + str(res))
```

**输出:**

> 原始列表为:[[3]，[1，7]，[10，2，4]，[8，6，5，1，4]]
> 
> 行的长度在增加吗？:真

**方法二:** *使用* [*全部()*](https://www.geeksforgeeks.org/any-all-in-python/) *和* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在本例中，我们使用 len()测试下一个长度是否大于当前长度，并使用 all()检查所有行。

## 蟒蛇 3

```
# initializing list
test_list = [[3], [1, 7], [10, 2, 4], [8, 6, 5, 1, 4]]

# printing original list
print("The original list is : " + str(test_list))

# checking for truth for all rows in matrix
res = all(len(test_list[idx + 1]) > len(test_list[idx]) for idx in range(len(test_list) - 1))

# printing result 
print("Are rows of increasing lengths ? : " + str(res))
```

**输出:**

> 原始列表为:[[3]，[1，7]，[10，2，4]，[8，6，5，1，4]]
> 
> 行的长度在增加吗？:真