# 用给定的数字替换某个范围内列表元素的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序-用给定的数字替换范围内的列表元素/](https://www.geeksforgeeks.org/python-program-to-replace-list-elements-within-a-range-with-a-given-number/)

给定一个范围，这里的任务是编写一个 python 程序，用指定的数字更新给定索引范围内的列表元素。

> **输入:** test_list = [4，6，8，1，2，9，0，10，12，3，9，1]，I，j = 4，8，K = 9
> 
> **输出:**【4、6、8、1、9、9、9、9、12、3、9、1】
> 
> **说明:**列表从第 4 到第 8 索引更新为 9。
> 
> **输入:** test_list = [4，6，8，1，2，9，0，10，12，3，9，1]，I，j = 4，8，K = 8
> 
> **输出:**【4、6、8、1、8、8、8、8、12、3、9、1】
> 
> **说明:**列表从第 4 到第 8 索引更新为 8。

**方法 1 :** *使用* [*切片*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) *和* [**运算符*](https://www.geeksforgeeks.org/python-operators/)

在这种情况下，我们使用切片来执行获取范围元素的任务，并使用*运算符来执行更新并提供填充更新所需的元素。

**程序:**

## 蟒蛇 3

```py
# initializing list
test_list = [4, 6, 8, 1, 2, 9, 0, 10, 12, 3, 9, 1]

# printing original list
print("The original list is : " + str(test_list))

# initializing i, j
i, j = 4, 8

# initializing K
K = 9

# getting range using slicing and
# required elements using * operator
test_list[i:j] = [K] * (j - i)

# printing result
print("Range Updated list : " + str(test_list))
```

**输出:**

> 原来的名单是:[4，6，8，1，2，9，0，10，12，3，9，1]
> 
> 范围更新列表:[4，6，8，1，2，9，0，10，12，3，9，1，9]

**方法二:** *使用* [*重复()*](https://www.geeksforgeeks.org/python-itertools-repeat/) *和* [*列表切片*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

类似的任务也可以使用 repeat()来执行，它使用未构建的构造来获取所需的元素。

**程序:**

## 蟒蛇 3

```py
from itertools import repeat

# initializing list
test_list = [4, 6, 8, 1, 2, 9, 0, 10, 12, 3, 9, 1]

# printing original list
print("The original list is : " + str(test_list))

# initializing i, j
i, j = 4, 8

# initializing K
K = 9

# getting range using slicing and
# required elements using repeat()
test_list[i:j] = repeat(K, (j - i))

# printing result
print("Range Updated list : " + str(test_list))
```

**输出:**

> 原来的名单是:[4，6，8，1，2，9，0，10，12，3，9，1]
> 
> 范围更新列表:[4，6，8，1，2，9，0，10，12，3，9，1，9]