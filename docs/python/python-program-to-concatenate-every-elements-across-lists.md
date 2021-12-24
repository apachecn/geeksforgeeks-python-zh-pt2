# Python 程序跨列表连接每个元素

> 原文:[https://www . geesforgeks . org/python-program-to-concatenate-even-elements-cross-list/](https://www.geeksforgeeks.org/python-program-to-concatenate-every-elements-across-lists/)

给定两个列表，跨列表执行所有字符串之间的连接。

> **输入**:test _ list 1 =[“gfg”、“is”、“best”]，test _ list 2 =[“love”、“CS”]
> **输出**:[‘gfg love’，‘gfg CS’，‘is love’，‘is CS’，‘best love’，‘best CS’]
> **解释**:所有的弦都是相互耦合的。
> 
> **输入**:test _ list 1 =[“gfg”、“best”]，test _ list 2 =[“love”、“CS”]
> **输出**:[‘gfg love’，‘gfg CS’，‘best love’，‘best CS’]
> **解释**:所有的弦都是相互耦合的。

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，我们使用列表理解与每个组成对，然后使用另一个列表理解执行连接任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# All elements concatenation across lists
# Using list comprehension

# initializing lists
test_list1 = ["gfg", "is", "best"]
test_list2 = ["love", "CS"]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# forming pairs
temp = [(a, b) for a in test_list1 for b in test_list2]

# performing concatenation
res = [x + ' ' + y for (x, y) in temp]

# printing result 
print("The paired combinations : " + str(res))
```

**输出:**

> 原单 1 为:['gfg love '，' is '，' best']
> 原单 2 为:['love '，' CS']
> 配对组合:[' gfg love '，' gfg CS '，' is love '，' is CS '，' best love '，' best CS']

**方法二:使用** [**品()**](https://www.geeksforgeeks.org/python-itertools-product/) **+列表理解**

在这种情况下，我们使用乘积()执行形成组合的任务，列表理解执行连接的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# All elements concatenation across lists
# Using product() + list comprehension
from itertools import product

# initializing lists
test_list1 = ["gfg", "is", "best"]
test_list2 = ["love", "CS"]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# concatenation using formatting and pairing using product
res = ['%s %s' % (ele[0], ele[1]) for ele in product(test_list1, test_list2)]

# printing result 
print("The paired combinations : " + str(res))
```

**输出:**

> 原单 1 为:['gfg love '，' is '，' best']
> 原单 2 为:['love '，' CS']
> 配对组合:[' gfg love '，' gfg CS '，' is love '，' is CS '，' best love '，' best CS']