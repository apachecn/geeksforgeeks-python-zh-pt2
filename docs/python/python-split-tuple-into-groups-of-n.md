# Python |将元组拆分成 n 个组

> 原文:[https://www . geesforgeks . org/python-split-tuple-in-group-of-n/](https://www.geeksforgeeks.org/python-split-tuple-into-groups-of-n/)

给定一个元组，任务是将它分成 n 个更小的组。让我们讨论几个方法来完成给定的任务。

**方法#1:使用枚举和范围功能**

```
# Python code to demonstrate
# how to split tuple
# into the group of k-tuples

# initialising tuple
ini_tuple = (1, 2, 3, 4, 8, 12, 3, 34,
             67, 45, 1, 1, 43, 65, 9, 10)

# printing initial tuple
print ("initial list", str(ini_tuple))

# code to group
# tuple into size 4 tuples
res = tuple(ini_tuple[x:x + 4] 
      for x in range(0, len(ini_tuple), 4))

# printing result
print ("resultant tuples", str(res))
```

**输出:**

> 初始列表(1，2，3，4，8，12，3，34，67，45，1，1，43，65，9，10)
> 结果元组((1，2，3，4)，(8，12，3，34)，(67，45，1，1)，(43，65，9，10))

**方法 2:使用枚举和 *mod* 运算符**

```
# Python code to demonstrate
# how to split tuple
# into the group of k-tuples

# initialising tuple
ini_tuple = (1, 2, 3, 4, 8, 12, 3, 34,
             67, 45, 1, 1, 43, 65, 9, 10)

# printing initial tuple
print ("initial list", str(ini_tuple))

# code to group
# tuple into size 4 tuples
res = tuple(ini_tuple[n:n + 4] for n, i in enumerate(ini_tuple)
                                                 if n % 4 == 0)

# printing result
print ("resultant tuples", str(res))
```

**输出:**

> 初始列表(1，2，3，4，8，12，3，34，67，45，1，1，43，65，9，10)
> 结果元组((1，2，3，4)，(8，12，3，34)，(67，45，1，1)，(43，65，9，10))

**方法 3:使用 ITER tools recipes**

```
# Python code to demonstrate
# how to split tuple
# into the group of k-tuples

# function to group tuple into groups of 4
def grouper(n, iterable):
    args = [iter(iterable)] * n
    return zip(*args)

# initialising tuple
ini_tuple = (1, 2, 3, 4, 8, 12, 3, 34,
             67, 45, 1, 1, 43, 65, 9, 10)

# printing initial tuple
print ("initial list", str(ini_tuple))

# code to group
# tuple into size 4 tuples
res = tuple(grouper(4, ini_tuple))

# printing result
print ("resultant tuples", str(res))
```

**输出:**

> 初始列表(1，2，3，4，8，12，3，34，67，45，1，1，43，65，9，10)
> 结果元组((1，2，3，4)，(8，12，3，34)，(67，45，1，1)，(43，65，9，10))