# Python–按 K 旋转字典

> 原文:[https://www . geesforgeks . org/python-rotate-dictionary-by-k/](https://www.geeksforgeeks.org/python-rotate-dictionary-by-k/)

给定一个字典，通过将字典键向右旋转 k 来执行它的重新排序

**示例:**

> **输入** : test_dict = {1:6，8: 1，9: 3，10:8，12:6，4:9}，K = 2
> **输出** : {12: 6，4:9，1:6，8:1，9:3，10: 8}
> **解释**:右旋转(循环)2 个元素后，重新排列项目。
> 
> **输入** : test_dict = {1:6，8: 1，9: 3，10: 8，12:6，4:9}，K = 1
> **输出** : {4: 9，1:6，8:1，9:3，10:8，12: 6}
> **解释**:右旋转(循环)1 个元素后，项目重新排列。

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) **+** [**项()**](https://www.geeksforgeeks.org/python-dictionary-items-method/) **+** [**词典理解**](https://www.geeksforgeeks.org/python-dictionary-comprehension/)

在这种情况下，我们执行字典到元组列表的转换任务，然后执行列表旋转，将结果再次转换到字典以获得结果关键字旋转。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Rotate dictionary by K
# Using list comprehension + items() + dictionary comprehension

# initializing dictionary
test_dict = {1: 6, 8: 1, 9: 3, 10: 8, 12: 6, 4: 9}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K
K = 2

# converting to tuples list
test_dict = list(test_dict.items())

# performing rotate
res = [test_dict[(i - K) % len(test_dict)]
       for i, x in enumerate(test_dict)]

# reconverting to dictionary
res = {sub[0]: sub[1] for sub in res}

# printing result
print("The required result : " + str(res))
```

**输出:**

> 原始字典为:{1: 6，8: 1，9: 3，10: 8，12: 6，4: 9}
> 所需结果:{12: 6，4: 9，1: 6，8: 1，9: 3，10: 8}

**方法二:使用** [**德格.旋转()**](https://www.geeksforgeeks.org/deque-in-python/) **+词典理解+物品()**

在这种情况下，我们使用 deque.rotate 实用程序执行旋转任务，其余所有功能都以与上述方法类似的方式执行。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Rotate dictionary by K
# Using deque.rotate() + dictionary comprehension + items()
from collections import deque

# initializing dictionary
test_dict = {1: 6, 8: 1, 9: 3, 10: 8, 12: 6, 4: 9}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K
K = 2

# converting to tuples list
test_dict = list(test_dict.items())

# performing rotate
# using deque
test_dict = deque(test_dict)
test_dict.rotate(K)
test_dict = list(test_dict)

# reconverting to dictionary
res = {sub[0]: sub[1] for sub in test_dict}

# printing result
print("The required result : " + str(res))
```

**输出:**

> 原始字典为:{1: 6，8: 1，9: 3，10: 8，12: 6，4: 9}
> 所需结果:{12: 6，4: 9，1: 6，8: 1，9: 3，10: 8}