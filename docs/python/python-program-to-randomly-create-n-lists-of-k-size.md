# Python 程序随机创建 K 大小的 N 个列表

> 原文:[https://www . geeksforgeeks . org/python-program-to-random-create-n-list-of-k-size/](https://www.geeksforgeeks.org/python-program-to-randomly-create-n-lists-of-k-size/)

给定一个列表，任务是编写一个 Python 程序，随机生成 N 个大小为 k 的列表

**示例:**

> **输入:** test_list = [6，9，1，8，4，7]，K，N = 3，4
> 
> **输出:** [[8，7，6]，[8，6，9]，[8，1，6]，[7，8，9]]
> 
> **说明:**随机抽取 3 个长度的 4 行。
> 
> **输入:** test_list = [6，9，1，8，4，7]，K，N = 2，3
> 
> **输出:** [[7，6]，[7，9]，[1，9]]
> 
> **说明:**随机抽取 2 个长度的 3 行。

**方法一:使用** [**生成器**](https://www.geeksforgeeks.org/generators-in-python/) **+** [**洗牌()**](https://www.geeksforgeeks.org/random-shuffle-function-in-python/)

在这种情况下，获取随机元素是使用 shuffle()完成的，而使用带有切片的 yield 来获取混合列表的 K 大小。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# K sized N random elements
# Using generator + shuffle()
from random import shuffle

# get random list 
def random_list(sub, K):
    while True:
        shuffle(sub)
        yield sub[:K]

# initializing list
test_list = [6, 9, 1, 8, 4, 7]

# initializing K, N 
K, N = 3, 4

# printing original list
print("The original list is : " + str(test_list))

res = []
# getting N random elements 
for idx in range(0, N):
    res.append(next(random_list(test_list, K)))

# printing result
print("K sized N random lists : " + str(res))
```

**输出:**

```py
The original list is : [6, 9, 1, 8, 4, 7]
K sized N random lists : [[7, 1, 8], [8, 6, 1], [4, 9, 6], [6, 9, 1]]
```

**方法二:使用** [**品()**](https://www.geeksforgeeks.org/python-itertools-product/) **+** [**样()**](https://www.geeksforgeeks.org/random-shuffle-function-in-python/)

在这种情况下，使用乘积()提取 K 个元素的所有可能的排列，并从中随机抽样 N 个列表。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# K sized N random elements
# Using product() + sample()
from random import sample
import itertools

# initializing list
test_list = [6, 9, 1, 8, 4, 7]

# initializing K, N 
K, N = 3, 4

# printing original list
print("The original list is : " + str(test_list))

# get all permutations
temp = (idx for idx in itertools.product(test_list, repeat = K))

# get Random N from them
res = sample(list(temp), N)
res = list(map(list, res))

# printing result
print("K sized N random lists : " + str(res))
```

**输出:**

```py
The original list is : [6, 9, 1, 8, 4, 7]
K sized N random lists : [[1, 1, 1], [6, 9, 4], [8, 7, 6], [4, 8, 8]]
```