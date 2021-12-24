# Python |按频率排序列表元素

> 原文:[https://www . geesforgeks . org/python-sort-list-elements-by-frequency/](https://www.geeksforgeeks.org/python-sort-list-elements-by-frequency/)

给定包含重复和不重复元素的列表，任务是根据元素的频率对给定列表进行排序。让我们讨论几个相同的方法。

### **方法#1:使用 collections.counter()**

## 蟒蛇 3

```py
# Python code to demonstrate
# sort list by frequency
# of elements

from collections import Counter

ini_list = [1, 2, 3, 4, 4, 5, 5, 5, 5, 7,
            1, 1, 2, 4, 7, 8, 9, 6, 6, 6]

# printing initial ini_list
print ("initial list", str(ini_list))

# sorting on bais of frequency of elements
result = [item for items, c in Counter(ini_list).most_common()
                                      for item in [items] * c]

# printing final result
print("final list", str(result))
```

**输出:**

```py
initial list [1, 2, 3, 4, 4, 5, 5, 5, 5, 7, 1, 1, 2, 4, 7, 8, 9, 6, 6, 6]
final list [5, 5, 5, 5, 1, 1, 1, 4, 4, 4, 6, 6, 6, 2, 2, 7, 7, 3, 8, 9]
```

### 
**方法 2:使用可滴定物**

## 蟒蛇 3

```py
# Python code to demonstrate
# sort list by frequency
# of elements

from collections import Counter
from itertools import repeat, chain

ini_list = [1, 2, 3, 4, 4, 5, 5, 5, 5, 7,
            1, 1, 2, 4, 7, 8, 9, 6, 6, 6]

# printing initial ini_list
print ("initial list", str(ini_list))

# sorting on bais of frequency of elements
result = list(chain.from_iterable(repeat(i, c)
         for i, c in Counter(ini_list).most_common()))

# printing final result
print("final list", str(result))
```

**输出:**

```py
initial list [1, 2, 3, 4, 4, 5, 5, 5, 5, 7, 1, 1, 2, 4, 7, 8, 9, 6, 6, 6]
final list [5, 5, 5, 5, 1, 1, 1, 4, 4, 4, 6, 6, 6, 2, 2, 7, 7, 3, 8, 9]
```

### 
**方法三:使用排序后的**

## 蟒蛇 3

```py
# Python code to demonstrate
# sort list by frequency
# of elements

ini_list = [1, 1, 2, 2, 2, 3, 3, 3, 3, 3,
               5, 5, 5, 4, 4, 4, 4, 4, 4]

# printing initial ini_list
print ("initial list", str(ini_list))

# sorting on bais of frequency of elements
result = sorted(ini_list, key = ini_list.count,
                                reverse = True)

# printing final result
print("final list", str(result))
```

**输出:**

```py
initial list [1, 1, 2, 2, 2, 3, 3, 3, 3, 3, 5, 5, 5, 4, 4, 4, 4, 4, 4]
final list [4, 4, 4, 4, 4, 4, 3, 3, 3, 3, 3, 2, 2, 2, 5, 5, 5, 1, 1]
```