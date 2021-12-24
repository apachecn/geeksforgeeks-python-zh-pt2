# Python 程序拆分相连的连续相似字符

> 原文:[https://www . geesforgeks . org/python-程序-拆分-连接-连续-相似-字符/](https://www.geeksforgeeks.org/python-program-to-split-joined-consecutive-similar-characters/)

给定一个字符串，我们的任务是编写一个 Python 程序，在出现不相似的字符时进行拆分。

> **输入:**test _ str = ' ggggffggisssbbbessstt '
> 
> **输出:** ['gggg '，' ff '，' gg '，' I '，' sss '，' bbb '，' ee '，' sss '，' tt']
> 
> **说明:**所有相似的连续字符都转换为单独的字符串。
> 
> **输入:**test _ str =‘ggggffgg’
> 
> **输出:** ['gggg '，' ff '，' gg']
> 
> **说明:**所有相似的连续字符都转换为单独的字符串。

**方法一:使用** [**加入()**](https://www.geeksforgeeks.org/join-function-python/) **+** [**列表理解**](https://www.geeksforgeeks.org/comprehensions-in-python/)**+**[**group by()**](https://www.geeksforgeeks.org/itertools-groupby-in-python/)

在这种情况下，使用 groupby()根据相似性对字符进行分组，join()用于重组字符串列表。列表理解执行迭代构造组的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Split joined consecutive similar characters
# Using join() + list comprehension + groupby()
from itertools import groupby

# initializing string
test_str = 'ggggffggisssbbbeessssstt'

# printing original string
print("The original string is : " + str(test_str))

# groupby groups the elements, join joining Consecutive groups
res = ["".join(group) for ele, group in groupby(test_str)]

# printing result
print("Consecutive split string is : " + str(res))
```

**输出:**

> 原始字符串是:ggggggffggsbbbebeesst
> 
> 连续的拆分字符串为:['gggg '，' ff '，' gg '，' I '，' sss '，' bbb '，' ee '，' sss '，' tt']

**方法 2:使用 finditer()+**[**regex**](https://www.geeksforgeeks.org/pattern-matching-python-regex/)**+列表理解**

在这种情况下，regex 用于检查连续的相等序列。finditer()执行在字符串中查找匹配正则表达式的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Split joined consecutive similar characters
# Using finditer() + regex + list comprehension
import re

# initializing string
test_str = 'ggggffggisssbbbeessssstt'

# printing original string
print("The original string is : " + str(test_str))

# list comprehension iterates for all the formed groups found by regex
# if consecutive numbers need to search "d" can be used.
res = [iters.group(0) for iters in re.finditer(r"(\D)\1*", test_str)]

# printing result
print("Consecutive split string is : " + str(res))
```

**输出:**

> 原始字符串是:ggggggffggsbbbebeesst
> 
> 连续的拆分字符串为:['gggg '，' ff '，' gg '，' I '，' sss '，' bbb '，' ee '，' sss '，' tt']