# Python 程序省略 K 长度行

> 原文:[https://www . geesforgeks . org/python-program-to-省略-k-length-rows/](https://www.geeksforgeeks.org/python-program-to-omit-k-length-rows/)

给定一个矩阵，删除长度为 k 的行

> **输入** : test_list = [[4，7]，[8，10，12，8]，[10，11]，[6，8，10]]，K = 2
> **输出** : [[8，10，12，8]，[6，8，10]]
> **解释** : [4，7]和[10，11]省略为长度 2 行。
> 
> **输入** : test_list = [[4，7]，[8，10，12，8]，[10，11]，[6，8，10]]，K = 3
> **输出** : [[4，7]，[8，10，12，8]，[10，11]]
> **解释** : [6，8，10]省略为长度 3 行。

**方法#1:使用 loop + len()**

在本文中，我们使用 len()检查每行的长度，如果发现等于 K，则从 Matrix 中省略该行。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Omit K length Rows
# Using loop + len()

# initializing list
test_list = [[4, 7],
             [8, 10, 12, 8],
             [10, 11], 
             [6, 8, 10]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 2

res = []
for row in test_list:

    # checking rows not K length
    if len(row) != K :
        res.append(row)

# printing result 
print("Filtered Matrix : " + str(res))
```

**输出:**

> 原始列表为:[[4，7]，[8，10，12，8]，[10，11]，[6，8，10]]
> 过滤矩阵:[[8，10，12，8]，[6，8，10]]

**方法 2:使用滤镜()+λ+len()**

在本文中，我们使用 filter()来提取长度不是 k 的行。lambda 函数用于呈现长度计算逻辑。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Omit K length Rows
# Using filter() + lambda + len()

# initializing list
test_list = [[4, 7],
             [8, 10, 12, 8],
             [10, 11], 
             [6, 8, 10]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 4

# getting elements with length other than K 
res = list(filter(lambda row : len(row) != K, test_list))

# printing result 
print("Filtered Matrix : " + str(res))
```

**输出:**

> 原始列表为:[[4，7]，[8，10，12，8]，[10，11]，[6，8，10]]
> 过滤矩阵:[[4，7]，[10，11]，[6，8，10]]