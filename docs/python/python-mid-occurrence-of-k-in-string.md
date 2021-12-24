# Python–字符串中 K 的中间出现

> 原文:[https://www . geesforgeks . org/python-字符串中出现 k 的中间位置/](https://www.geeksforgeeks.org/python-mid-occurrence-of-k-in-string/)

给定一个字符串，任务是编写一个 Python 程序来提取字符的中间出现。

> **输入:** test_str =“极客 forgeeks 最适合所有极客”，K = 'e '
> 
> **输出:** 10
> 
> **说明:**出现 7 次 e .第 4 次出现[mid]在第 10 指数。
> 
> **输入:** test_str =“极客 forgeeks 最适合所有极客”，K = 'g '
> 
> **输出:** 8
> 
> **说明:**g 出现 3 次，第 2 次出现【中】在第 8 个指标。

**方法一:使用** [**枚举()**](https://www.geeksforgeeks.org/enumerate-in-python/) **+** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

在这种情况下，我们使用列表理解执行获取所有事件的任务，并枚举获取所有索引。发布列表的中间元素被打印以获得字符的中间出现。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Mid occurrence of K in string
# Using find() + max() + slice

# initializing string
test_str = "geeksforgeeks is best for all geeks"

# printing original string
print("The original string is : " + str(test_str))

# initializing K
K = 'e'

# getting all the indices of K
indices = [idx for idx, ele in enumerate(test_str) if ele == K]

# getting mid index
res = indices[len(indices) // 2]

# printing result
print("Mid occurrence of K : " + str(res))
```

**输出:**

```
The original string is : geeksforgeeks is best for all geeks
Mid occurrence of K : 10
```

**方法 2:使用 finditer() +** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)**+**[**regex**](https://www.geeksforgeeks.org/python-regex/)

在本例中，使用正则表达式和 finditer()找到字符。中间事件是索引列表的中间元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Mid occurrence of K in string
# Using finditer() + list comprehension + regex
import re

# initializing string
test_str = "geeksforgeeks is best for all geeks"

# printing original string
print("The original string is : " + str(test_str))

# initializing K
K = 'e'

# getting all the indices of K
# using regex
indices = [ele.start() for ele in re.finditer(K, test_str)]

# getting mid index
res = indices[len(indices) // 2]

# printing result
print("Mid occurrence of K : " + str(res))
```

**输出:**

```
The original string is : geeksforgeeks is best for all geeks
Mid occurrence of K : 10
```