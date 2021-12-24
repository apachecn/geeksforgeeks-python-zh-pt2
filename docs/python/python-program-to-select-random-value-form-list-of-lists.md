# Python 程序选择随机值形成列表列表

> 原文:[https://www . geesforgeks . org/python-程序选择-随机值-表单-列表列表/](https://www.geeksforgeeks.org/python-program-to-select-random-value-form-list-of-lists/)

给定一个列表。任务是从中提取一个随机元素。

**示例:**

```
Input : test_list = [[4, 5, 5], [2, 7, 4], [8, 6, 3]]
Output : 7
Explanation : Random number extracted from Matrix.

Input : test_list = [[4, 5, 5], [2, 7, 4], [8, 6, 3]], r_no = 2
Output : 6
Explanation : Random number extracted from 2nd row from Matrix.
```

**方法#1:使用 chain . from _ iterable()+random . choice()**

在本例中，我们使用 [from_iterable()](https://www.geeksforgeeks.org/python-itertools-chain-from_iterable/) 将矩阵展平为列表，并使用 [choice()](https://www.geeksforgeeks.org/random-choices-method-in-python/) 从列表中获取一个随机数。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Random Matrix Element
# Using chain.from_iterables() + random.choice()
from itertools import chain
import random

# initializing list
test_list = [[4, 5, 5], [2, 7, 4], [8, 6, 3]]

# printing original list
print("The original list is : " + str(test_list))

# choice() for random number, from_iterables for flattening
res = random.choice(list(chain.from_iterable(test_list)))

# printing result
print("Random number from Matrix : " + str(res))
```

**Output**

```
The original list is : [[4, 5, 5], [2, 7, 4], [8, 6, 3]]
Random number from Matrix : 6

```

**方法 2:使用 choice()从特定行**获取元素

如果提到一行，可以使用 choice()方法从该行获取随机元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Random Matrix Element
# Using random.choice() [if row number given]
import random

# initializing list
test_list = [[4, 5, 5], [2, 7, 4], [8, 6, 3]]

# printing original list
print("The original list is : " + str(test_list))

# initializing Row number
r_no = 1

# choice() for random number, from_iterables for flattening
res = random.choice(test_list[r_no])

# printing result
print("Random number from Matrix Row : " + str(res))
```

**Output**

```
The original list is : [[4, 5, 5], [2, 7, 4], [8, 6, 3]]
Random number from Matrix Row : 7

```