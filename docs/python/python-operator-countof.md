# Python | Operator.countOf

> 原文:[https://www.geeksforgeeks.org/python-operator-countof/](https://www.geeksforgeeks.org/python-operator-countof/)

**`Operator.countOf()`** 用于统计`a`中`b`的出现次数。它计算值的出现次数。

> **语法:** Operator.countOf(freq = a，value = b)
> **参数:**
> **freq :** 它可以是存储值的列表或任何其他数据类型
> **值:**它是我们必须计算出现次数的值
> 
> **返回:**数值出现次数的计数。

**示例#1:** 使用`Operator.countOf()`统计列表中给定值的出现次数。

```py
# Python program showing
# use of countOf() function
# in a list

from operator import * 
arr = [ 1, 2, 3, 3, 3 ]
arr1 = [ 'a', 'b', 'c', 'b', 'd' ]

print("Number of occurrence of b in arr1 =", countOf(arr1, "b"))
print("Number of occurrence of e in arr1 =", countOf(arr1, "e"))
print("Number of occurrence of 3 in arr =", countOf(arr, 3))
```

**输出:**

```py
Number of occurrence of b in arr1 = 2
Number of occurrence of e in arr1 = 0
Number of occurrence of 3 in arr = 3

```

**示例 2:** 使用`Operator.countOf()`统计字典中给定值的出现次数。

```py
# Python program showing
# use of countOf() function
# in a dictionary

from operator import *

d = {"score": 3, "score1": 1, "score2": 3, "score3": 1, "score4": 3}

print("Number of occurrence of three in dict =",countOf(d.values(),3))
print("Number of occurrence of one in dict =",countOf(d.values(),1))
print("Number of occurrence of four in dict =",countOf(d.values(),4))
```

**输出:**

```py
Number of occurrence of three in dict = 3
Number of occurrence of one in dict = 2
Number of occurrence of four in dict = 0

```

**示例#3:** 使用`Operator.countOf()`统计元组中给定值的出现次数。

```py
# Python program showing
# use of countOf() function
# in a tuples

from operator import *

tup = ( 1, 2, 3, 3, 3 )
tup1 = ( 'a', 'b', 'c', 'b', 'd' )

print("Number of occurrence of b in tuple1 =",countOf(tup1,"b"))
print("Number of occurrence of e in tuple1 =",countOf(tup1,"e"))
print("Number of occurrence of 3 in tuple =",countOf(tup,3))
```

**输出:**

```py
Number of occurrence of b in tuple1 = 2
Number of occurrence of e in tuple1 = 0
Number of occurrence of 3 in tuple = 3

```