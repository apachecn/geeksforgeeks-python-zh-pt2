# Python |用序号列出区间

> 原文:[https://www . geeksforgeeks . org/python-用顺序号列出时间间隔/](https://www.geeksforgeeks.org/python-make-a-list-of-intervals-with-sequential-numbers/)

给定一个序列号列表，编写一个 Python 程序，将给定的列表转换成区间列表。

**示例:**

```py
Input : [2, 3, 4, 5, 7, 8, 9, 11, 15, 16]
Output : [[2, 5], [7, 11], [15, 16]]

Input : [1, 2, 3, 6, 7, 8, 9, 10]
Output : [[1, 3], [6, 10]]

```

**方法#1 :** 天真方法

首先，我们使用蛮力方法将序列号列表转换为区间。开始一个循环，直到列表的长度。在每次迭代中，使用另一个循环来检查序列的连续性。一旦序列停止，得出每个区间的下限和上限。

```py
# Python3 program to Convert list of 
# sequential number into intervals

def interval_extract(list):
    length = len(list)
    i = 0
    while (i< length):
        low = list[i]
        while i <length-1 and list[i]+1 == list[i + 1]:
            i += 1
        high = list[i]
        if (high - low >= 1):
            yield [low, high]
        elif (high - low == 1):
            yield [low, ]
            yield [high, ]
        else:
            yield [low, ]
        i += 1

# Driver code
l =  [2, 3, 4, 5, 7, 8, 9, 11, 15, 16]
print( list(interval_extract(l)))
```

**Output:**

```py
[[2, 5], [7, 9], [11], [15, 16]]

```

**方法 2 :** 皮托尼天真
首先，对给定的列表进行排序。用第一个元素初始化*上一个 _ 编号*和*范围 _ 开始*。开始一个循环，检查下一个数字是否是前一个数字的加法，如果是，将这个数字初始化为前一个数字，否则产生以 *range_start* 开始，以 *previous_number* 结束的新间隔。

```py
# Python3 program to Convert list of 
# sequential number into intervals

def interval_extract(list):
    list = sorted(set(list))
    range_start = previous_number = list[0]

    for number in list[1:]:
        if number == previous_number + 1:
            previous_number = number
        else:
            yield [range_start, previous_number]
            range_start = previous_number = number
    yield [range_start, previous_number]

# Driver code
l = [2, 3, 4, 5, 7, 8, 9, 11, 15, 16]
print( list(interval_extract(l)))
```

**Output:**

```py
[[2, 5], [7, 9], [11, 11], [15, 16]]

```

**方法#3 :** 使用 itertools
另一种 Python 方法是使用 Python itertools。我们用`itertools.groupby()`。其中 enumerate(iterable)被认为是可迭代的，而*λt:t[1]–t[0])*被认为是寻找区间序列的关键函数。

```py
# Python3 program to Convert list of 
# sequential number into intervals
import itertools

def intervals_extract(iterable):

    iterable = sorted(set(iterable))
    for key, group in itertools.groupby(enumerate(iterable),
    lambda t: t[1] - t[0]):
        group = list(group)
        yield [group[0][1], group[-1][1]]

# Driver code
l = [2, 3, 4, 5, 7, 8, 9, 11, 15, 16]
print( list(intervals_extract(l)))
```

**Output:**

```py
[[2, 5], [7, 9], [11, 11], [15, 16]]

```