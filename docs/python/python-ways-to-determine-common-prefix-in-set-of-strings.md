# Python |确定字符串集合中公共前缀的方法

> 原文:[https://www . geesforgeks . org/python-确定字符串集中公共前缀的方法/](https://www.geeksforgeeks.org/python-ways-to-determine-common-prefix-in-set-of-strings/)

给定一组字符串，编写一个 Python 程序从一组字符串中确定公共前缀。下面给出了几个解决上述任务的方法。
**方法#1:使用天真方法**

## 蟒蛇 3

```
# Python code to demonstrate
# to find common prefix
# from set of strings

# Initialising string
ini_strlist = ['akshat', 'akash', 'akshay', 'akshita']

# Finding common prefix using Naive Approach
res = ''
prefix = ini_strlist[0]

for string in ini_strlist[1:]:
    while string[:len(prefix)] != prefix and prefix:
        prefix = prefix[:len(prefix)-1]
    if not prefix:
        break
res = prefix

# Printing result
print("Resultant prefix", str(res))
```

**Output:** 

```
Resultant prefix ak
```

**方法 2:使用 itertools.takewhile 并压缩**

## 蟒蛇 3

```
# Python code to demonstrate
# to find common prefix
# from set of strings

from itertools import takewhile

# Initialising string
ini_strlist = ['akshat', 'akash', 'akshay', 'akshita']

# Finding common prefix using Naive Approach
res = ''.join(c[0] for c in takewhile(lambda x:
        all(x[0] == y for y in x), zip(*ini_strlist)))

# Printing result
print("Resultant prefix", str(res))
```

**Output:** 

```
Resultant prefix ak
```