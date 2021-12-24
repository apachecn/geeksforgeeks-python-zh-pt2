# Python–测试连续元素矩阵

> 原文:[https://www . geesforgeks . org/python-test-continuous-element-matrix/](https://www.geeksforgeeks.org/python-test-consecutive-element-matrix/)

给定一个矩阵，测试它是否由连续的元素组成。

> **输入** : test_list = [[4，5，6]，[7]，[8，9，10]，[11，12]]
> **输出** : True
> **解释**:矩阵中的元素范围为 4 到 12。
> 
> **输入** : test_list = [[4，5，6]，[7]，[8，18，10]，[11，12]]
> **输出** : False
> **解释**:元素不连续，不在范围内。

**方法#1:使用循环**

在这种情况下，我们检查行内的连续性，并且在每行之前，检查第一个元素是否紧挨着前一行的最后一个元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test Consecutive Element Matrix
# Using loop

# initializing list
test_list = [[4, 5, 6], [7], [8, 9, 10], [11, 12]]

# printing original list
print("The original list is : " + str(test_list))

res = True
mem_list = []
for sub in test_list:
    flag = True
    for ele in sub:

        # checking for last element to be Consecutive
        if len(mem_list) != 0:
            if mem_list[-1] != ele - 1:
                flag = False
                break
        mem_list.append(ele)

    if not flag:
        res = False
        break

# printing result
print("Is Matrix Consecutive ? : " + str(res))
```

**Output**

```
The original list is : [[4, 5, 6], [7], [8, 9, 10], [11, 12]]
Is Matrix Consecutive ? : True
```

**方法 2:使用 chain.from_iterable() + all()**

在这种情况下，我们将矩阵展平为列表，然后使用 all()检查序列中的所有元素，使其比展平矩阵中的前一个元素大 1。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test Consecutive Element Matrix
# Using chain.from_iterable() + all()
from itertools import chain

# initializing list
test_list = [[4, 5, 6], [7], [8, 9, 10], [11, 12]]

# printing original list
print("The original list is : " + str(test_list))

# flattening matrix
test_list = list(chain.from_iterable(test_list))

# checking for boolean true
res = all(test_list[idx - 1] == test_list[idx] -
          1 for idx in range(1, len(test_list)))

# printing result
print("Is Matrix Consecutive ? : " + str(res))
```

**Output**

```
The original list is : [[4, 5, 6], [7], [8, 9, 10], [11, 12]]
Is Matrix Consecutive ? : True
```