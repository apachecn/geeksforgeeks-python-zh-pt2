# Python–将数字串拆分为 K 位整数

> 原文:[https://www . geesforgeks . org/python-split-numeric-string-in-k-digital-integers/](https://www.geeksforgeeks.org/python-split-numeric-string-into-k-digit-integers/)

给定一个字符串，将其转换为 K 位整数

> **输入** : test_str = '457336 '，K = 2
> **输出**:【45，73，36】
> **解释**:除以 2 位整数。
> 
> **输入** : test_str = '457336 '，K = 3
> **输出**:【457，336】
> **说明**:除以 3 位整数。

**方法#1:使用 int() + slice + loop**

在这种情况下，我们对字符串进行迭代并执行切片直到 K 个数字，然后使用 int()执行转换为整数的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Split Numeric String into K digit integers
# Using int() + slice + loop

# initializing string
test_str = '457336842'

# printing original string
print("The original string is : " + str(test_str))

# initializing substring
K = 3

res = []
for idx in range(0, len(test_str), K):

    # converting to int, after slicing
    res.append(int(test_str[idx : idx + K]))

# printing result 
print("Converted number list : " + str(res)) 
```

**Output**

```py
The original string is : 457336842
Converted number list : [457, 336, 842]

```

**方法二:使用列表理解+ int() +切片**

类似上面的方法，只是解决这个问题的一种速记。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Split Numeric String into K digit integers
# Using list comprehension + int() + slicing

# initializing string
test_str = '457336842'

# printing original string
print("The original string is : " + str(test_str))

# initializing substring
K = 3

# one liner to solve problem
res = [int(test_str[idx : idx + K]) for idx in range(0, len(test_str), K)]

# printing result 
print("Converted number list : " + str(res)) 
```

**Output**

```py
The original string is : 457336842
Converted number list : [457, 336, 842]

```