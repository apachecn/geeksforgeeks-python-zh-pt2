# Python–多集交集

> 原文:[https://www . geesforgeks . org/python-多集-交集/](https://www.geeksforgeeks.org/python-multiple-sets-intersection/)

在本文给出的集合列表中，任务是编写一个 Python 程序来执行它们的交集。

**示例:**

> **输入:** test_list = [{5，3，6，7}，{1，3，5，2}，{7，3，8，5}，{8，4，5，3}]
> 
> **输出:** {3，5}
> 
> **说明:** 3 和 5 出现在所有的集合中。
> 
> **输入:** test_list = [{5，3，6，7}，{1，3，5，2}，{7，3，8，5}，{8，4，5，4}]
> 
> **输出:** {5}
> 
> **说明:** 5 出现在所有的集合中。

**方法#1:使用** [**交点()**](https://www.geeksforgeeks.org/intersection-function-python/) **+ *运算符**

在本文中，我们使用交集()执行获取交集的任务，并使用*运算符将所有集合打包在一起。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Multiple Sets Intersection
# Using intersection() + * operator

# initializing list
test_list = [{5, 3, 6, 7}, {1, 3, 5, 2}, {7, 3, 8, 5}, {8, 4, 5, 3}]

# printing original list
print("The original list is : " + str(test_list))

# getting all sets intersection using intersection()
res = set.intersection(*test_list)

# printing result
print("Intersected Sets : " + str(res))
```

**输出:**

> 原始列表为:[{3，5，6，7}，{1，2，3，5}，{8，3，5，7}，{8，3，4，5}]
> 
> 相交集:{3，5}

**方法 2:使用** [**减少()**](https://www.geeksforgeeks.org/reduce-in-python/) **+和 _ 运算符**

在本例中，我们使用 and_ operator 执行交集任务，reduce()执行将所有集合打包在一起进行所需操作的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Multiple Sets Intersection
# Using reduce() + and_ operator
from operator import and_
from functools import reduce

# initializing list
test_list = [{5, 3, 6, 7}, {1, 3, 5, 2}, {7, 3, 8, 5}, {8, 4, 5, 3}]

# printing original list
print("The original list is : " + str(test_list))

# getting all sets intersection using and_ operator
res = set(reduce(and_, test_list))

# printing result
print("Intersected Sets : " + str(res))
```

**输出:**

> 原始列表为:[{3，5，6，7}，{1，2，3，5}，{8，3，5，7}，{8，3，4，5}]
> 
> 相交集:{3，5}