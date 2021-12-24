# Python 程序，用于元组列表中值的唯一键计数

> 原文:[https://www . geesforgeks . org/python-程序到唯一键-元组列表中值的计数/](https://www.geeksforgeeks.org/python-program-to-unique-keys-count-for-value-in-tuple-list/)

给定二元组，获取元组中每个值的唯一键的计数。

> **输入** : test_list = [(3，4)，(1，2)，(2，4)，(8，2)，(7，2)，(8，1)，(9，1)，(8，4)，(10，4)]
> **输出** : {4: 4，2: 3，1: 2}
> **解释** : 3，2，8，10 为数值 4 的键。
> 
> **输入** : test_list = [(3，4)，(1，2)，(8，1)，(9，1)，(8，4)，(10，4)]
> **输出** : {4: 3，2: 1，1: 2}
> **解释** : 3，8，10 为数值 4 的键。

**方法#1:使用循环+ defaultdict()**

在这种情况下，我们对每个元组元素进行迭代，将键作为元组值，并用字典值列表中遇到的每个不同的键对其进行递增。接下来，通过获得映射值列表的长度，转换为 set 以获得唯一计数，使用另一次迭代来计算频率。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Unique keys count for Value in Tuple List
# Using loop + defaultdict()
from collections import defaultdict

# initializing list
test_list = [(3, 4), (1, 2), (2, 4), (8, 2), (7, 2), (8, 1), (9, 1), (8, 4), (10, 4)]

# printing original list
print("The original list is : " + str(test_list))

res = defaultdict(list)
for sub in test_list:

    # getting all keys to values
    res[sub[1]].append(sub[0])

res = dict(res)

res_dict = dict()
for key in res:

    # getting unique key counts for each value
    res_dict[key] = len(list(set(res[key])))

# printing result 
print("Unique keys for values : " + str(res_dict))
```

**输出:**

> 原清单为:[(3，4)，(1，2)，(2，4)，(8，2)，(7，2)，(8，1)，(9，1)，(8，4)，(10，4)]
> 
> 值的唯一键:{4: 4，2: 3，1: 2}

**方法 2:使用循环+ defaultdict() + Counter()**

在这种情况下，为了减少计算循环，该列表被动态地构建，仅具有唯一的值。然后使用 Counter()获取唯一值字典。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# loop + defaultdict() + Counter()
# Using loop + defaultdict() + Counter()
from collections import defaultdict, Counter

# initializing list
test_list = [(3, 4), (1, 2), (2, 4), (8, 2), (7, 2),
             (8, 1), (9, 1), (8, 4), (10, 4)]

# printing original list
print("The original list is : " + str(test_list))

mem_dict = defaultdict(list)
res = []
for sub in test_list:

    # if not in dict, add value 
    if sub[0] not in mem_dict[sub[1]]:
        mem_dict[sub[1]].append(sub[0])
        res.append(sub[1])

# getting frequency 
res = dict(Counter(res))

# printing result 
print("Unique keys for values : " + str(res))
```

**输出:**

原始列表为:[(3，4)，(1，2)，(2，4)，(8，2)，(7，2)，(8，1)，(9，1)，(8，4)，(10，4)]
值的唯一键:{4: 4，2: 3，1: 2}

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Unique keys count for Value in Tuple List
# Using loop + defaultdict()
from collections import defaultdict

# initializing list
test_list = [(3, 4), (1, 2), (2, 4), (8, 2), (7, 2), 
             (8, 1), (9, 1), (8, 4), (10, 4)]

# printing original list
print("The original list is : " + str(test_list))

res = defaultdict(list)
for sub in test_list:

    # getting all keys to values
    res[sub[1]].append(sub[0])

res = dict(res)

res_dict = dict()
for key in res:

    # getting unique key counts for each value
    res_dict[key] = len(list(set(res[key])))

# printing result 
print("Unique keys for values : " + str(res_dict))
```