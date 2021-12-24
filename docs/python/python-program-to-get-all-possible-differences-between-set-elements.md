# Python 程序获取集合元素之间所有可能的差异

> 原文:[https://www . geesforgeks . org/python-program-获取集合元素之间所有可能的差异/](https://www.geeksforgeeks.org/python-program-to-get-all-possible-differences-between-set-elements/)

给定一个集合，任务是编写一个 Python 程序来获取其元素之间所有可能的差异。

```py
Input : test_set = {1, 5, 2, 7, 3, 4, 10, 14}
Output : {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13}
Explanation : All possible differences are computed.

Input : test_set = {1, 5, 2, 7}
Output : {1, 2, 3, 4, 5, 6}
Explanation : All possible differences are computed.
```

**方法#1:使用** [**组合()**](https://www.geeksforgeeks.org/python-itertools-combinations-function/)**+**[**ABS()**](https://www.geeksforgeeks.org/abs-in-python/)**+循环**

在这种情况下，使用组合()提取所有可能的对。然后用循环遍历，用 abs()求差。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# All elements difference in Set
# Using combinations + abs() + loop
from itertools import combinations

# initializing strings set
test_set = {1, 5, 2, 7, 3, 4, 10, 14}

# printing original string
print("The original set is : " + str(test_set))

# getting combinations
combos = combinations(test_set, 2)

res = set()

# adding differences in set
for x, y in combos:
    res.add(abs(x - y))

# printing result
print("All possible differences : " + str(res))
```

**输出:**

> 原始集合为:{1，2，3，4，5，7，10，14}
> 
> 所有可能的差异:{1，2，3，4，5，6，7，8，9，10，11，12，13}

**方法 2:使用集合理解+组合()+ abs()**

在本文中，我们使用集合理解作为解决问题的一种线性方法来执行获取和设置所有元素的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# All elements difference in Set
# Using set comprehension + combinations() + abs()
from itertools import combinations

# initializing strings set
test_set = {1, 5, 2, 7, 3, 4, 10, 14}

# printing original string
print("The original set is : " + str(test_set))

# set comprehension providing consize solution
res = {abs(x - y) for x, y in combinations(test_set, 2)}

# printing result
print("All possible differences : " + str(res))
```

**输出:**

> 原始集合为:{1，2，3，4，5，7，10，14}
> 
> 所有可能的差异:{1，2，3，4，5，6，7，8，9，10，11，12，13}