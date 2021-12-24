# Python 程序，通过在每个元素后添加给定的字符串将元组转换为列表

> 原文:[https://www . geesforgeks . org/python-通过在每个元素后添加给定的字符串来将程序转换为元组列表/](https://www.geeksforgeeks.org/python-program-to-covert-tuple-into-list-by-adding-the-given-string-after-every-element/)

给定一个元组。任务是通过在每个元素后添加给定的字符串将其转换为列表。

**示例:**

```
Input : test_tup = (5, 6, 7), K = "Gfg" 
Output : [5, 'Gfg', 6, 'Gfg', 7, 'Gfg'] 
Explanation : Added "Gfg" as succeeding element.

Input : test_tup = (5, 6), K = "Gfg" 
Output : [5, 'Gfg', 6, 'Gfg'] 
Explanation : Added "Gfg" as succeeding element.
```

**方法一:使用列表理解**

在这种情况下，我们用后续元素构建元组的每个元素的元组，然后运行嵌套循环来使用列表理解来展平每个构建的元组。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert tuple to List with succeeding element
# Using list comprehension

# initializing tuple
test_tup = (5, 6, 7, 4, 9)

# printing original tuple
print("The original tuple is : ", test_tup)

# initializing K
K = "Gfg"

# list comprehension for nested loop for flatten
res = [ele for sub in test_tup for ele in (sub, K)]

# printing result
print("Converted Tuple with K : ", res)
```

**输出:**

> 原始元组为:(5，6，7，4，9)
> K 为的转换元组:[5，‘Gfg’，6，‘Gfg’，7，‘Gfg’，4，‘Gfg’，9，‘Gfg’

**方法 2:使用 chain.from_iterable() + list() +生成器表达式**

这与上述方法类似，不同之处在于，通过使用 chain.from_iterable()进行平面化，避免了嵌套循环。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert tuple to List with succeeding element
# Using chain.from_iterable() + list() + generator expression
from itertools import chain

# initializing tuple
test_tup = (5, 6, 7, 4, 9)

# printing original tuple
print("The original tuple is : ", test_tup)

# initializing K
K = "Gfg"

# list comprehension for nested loop for flatten
res = list(chain.from_iterable((ele, K) for ele in test_tup))

# printing result
print("Converted Tuple with K : ", res)
```

**输出:**

> 原始元组为:(5，6，7，4，9)
> K 为的转换元组:[5，‘Gfg’，6，‘Gfg’，7，‘Gfg’，4，‘Gfg’，9，‘Gfg’