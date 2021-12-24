# Python 程序获取两个列表的所有唯一组合

> 原文:[https://www . geesforgeks . org/python-program-to-get-all-unique-two-list 组合/](https://www.geeksforgeeks.org/python-program-to-get-all-unique-combinations-of-two-lists/)

组合是一种数学技术，它计算项目或列表集合中可能排列的数量。在组合中选择的顺序并不重要。Python 中两个列表的唯一组合可以通过将第一个列表的每个元素与第二个列表的元素配对来形成。

**示例:**

```
List_1 = ["a","b"]
List_2 = [1,2]
Unique_combination = [[('a',1),('b',2)],[('a',2),('b',1)]] 
```

**方法 1 :** 使用 itertools 包的**置换()**和 **zip()** 功能。

**进场:**

*   导入 itertools 包并初始化 list_1 和 list_2。
*   创建一个“unique_combinations”的空列表来存储由此获得的组合。
*   调用 itertools .置换( )，它将返回长度为 list_2 的 list_1 的置换。通常，取较短列表的长度，如果两个列表相等，则使用其中一个。
*   使用 For 循环，并调用 zip()函数将每个排列和较短的列表元素配对到组合中。
*   然后每个组合被转换成一个列表，并追加到组合列表中。

下面是实现。

## 蟒蛇 3

```
# python program to demonstrate
# unique combination of two lists
# using zip() and permutation of itertools

# import itertools package
import itertools
from itertools import permutations

# initialize lists
list_1 = ["a", "b", "c","d"]
list_2 = [1,4,9]

# create empty list to store the
# combinations
unique_combinations = []

# Getting all permutations of list_1
# with length of list_2
permut = itertools.permutations(list_1, len(list_2))

# zip() is called to pair each permutation
# and shorter list element into combination
for comb in permut:
    zipped = zip(comb, list_2)
    unique_combinations.append(list(zipped))

# printing unique_combination list
print(unique_combinations)
```

**输出:**

> [[[(a)、(1)、(b)、(4)、(c)、(9)][(a)、(1)、(b)、(4)、(d)、(9)][(a)、(1)、(c)、(4)、(b)、(9)][(a)、(1)、(1)、(c)、(4)、(d)、(9)][(a)、(4)、(9)][(a)、(1)、(d)、(4)、(b)、(9)][(a)、(1)、(d)、(4)、(c)、(9)][(b)) (4)、[(c)、(1)、(b)、(4)、(a)、(9)][(c)、(1)、(b)、(4)、(d)、(9)][(c)、(1)、(d)、(4)、(a)、(9)][(c)、(1)、(1)、(d)、(4)、(9)][(c)、(1)、(d)、(4)、(b)、(9)][(d)、(1)、(a)、(4)、(b)、(9)][(d)、(1)、(a)、(4)、(c)]

**方法 2 :** 使用 itertools 包的**产品()**和 **zip()** 功能。

**进场:**

*   导入 itertools 包并初始化 list_1 和 list_2。
*   创建一个“unique_combinations”的空列表来存储由此获得的组合。
*   调用 product()来查找所有可能的元素组合。
*   zip()用于将所有这些组合配对，将每个元素转换成一个列表，并将它们附加到所需的组合列表中。

下面是实现。

## 蟒蛇 3

```
# python program to demonstrate
# unique combination of two lists
# using zip() and product() of itertools

# import itertools package
import itertools
from itertools import product

# initialize lists
list_1 = ["b","c","d"]
list_2 = [1,4,9]

# create empty list to store the combinations
unique_combinations = []

# Extract Combination Mapping in two lists
# using zip() + product()
unique_combinations = list(list(zip(list_1, element))
                           for element in product(list_2, repeat = len(list_1)))

# printing unique_combination list
print(unique_combinations)
```

**输出:**

> [[[(' b '，1)、(' c '，1)、[' b '，1)、[' c '，1)、(' d '，4)][' b '，1)、[' c '，1)、[' d '，1)、[' d '，9)][' b '，1)、[' c '，4、[' d '，1][(' b '，1)、[' c '，4)][` d '，4][` b '，1][' c '，4][` d '，9][' b ' (4)、[(b)、(4)、(c)、(4)、(4)、(d)、(9)][(b)、(4)、(c)、(9)、(d)、(1)][(b)、(4)、(c)、(9)、(d)、(4)][(b)、(4)、(c)、(9)、(4)][(b)、(4)、(c)、(9)、(d)、(9)][(b)、(9)、(c)、(1)、(d)、(1)][(b)、(9)、(c)、(1)][(d)、(d)、(1))