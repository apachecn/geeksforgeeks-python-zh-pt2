# Python 程序，用 K 值从两个列表中渲染字典

> 原文:[https://www . geeksforgeeks . org/python-program-rendering-a-dictionary-from-two-list-with-k-values/](https://www.geeksforgeeks.org/python-program-that-renders-a-dictionary-from-two-list-with-k-values/)

给定两个列表，一个用于提供字典的键，另一个用于值。以下程序从第二个列表中获取 K 值，并将其分配给每个键，创建以下类型的字典:

> **输入**:test _ list =[“gfg”，“best”]，val_list = [1，4，5，6，7，8，8，5]，K = 4
> **输出**:{‘gfg’:[1，4，5，6]，‘best]:[7，8，8，5]}
> **解释:**:每个按键配对的相等元素。
> **输入** : test_list = ["gfg"]，val_list = [1，4，5，6]，K = 4
> **输出** : {'gfg': [1，4，5，6]}
> **解释**:所有元素只赋给键。

**方法:** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/) *和* [*切片*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

## 蟒蛇 3

```
from collections import defaultdict

# initializing list
test_list = ["gfg", "is", "best", "good"]

# printing original list
print("The original list is : " + str(test_list))

# initializing values list
val_list = [1, 4, 5, 6, 7, 8, 8, 5, 4]

# initializing K
K = 2

# work list
val_list = val_list[:(len(test_list) * K)]

# gets required dictionary list
res = defaultdict(list)
key_cnt = 0
for idx in range(0, len(val_list)):

    # append values to required keys   
    res[test_list[key_cnt]].append(val_list[idx])

    # increment keys when K
    if (idx + 1) % K == 0:
        key_cnt += 1

# printing result
print("The constructed dictionary : " + str(dict(res)))
```