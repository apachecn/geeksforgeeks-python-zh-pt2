# Python–删除重复元素的列

> 原文:[https://www . geesforgeks . org/python-移除重复元素列/](https://www.geeksforgeeks.org/python-remove-columns-of-duplicate-elements/)

给定一个矩阵，编写一个 Python 程序，如果任何一行出现重复，就删除整个列。

**示例:**

> **输入** : test_list = [[4，3，5，2，3]，[6，4，2，1，1]，[4，3，9，3，9]，[5，4，3，2，1]]
> **输出** : [[4，3，5]，[6，4，2]，[4，3，9]，[5，4，3]]
> **解释** : 1 有重复作为下一个元素，因此删除第 5 列。3 作为第二个和第四个索引出现，因此第四个索引被删除。
> 
> **输入** : test_list = [[6，4，2，1，1]，[4，3，9，3，9]，[5，4，3，2，1]]
> **输出** : [[6，4，2]，[4，3，9]，[5，4，3]]
> **解释** : 1 有重复作为下一个元素，因此删除第 5 列。3 作为第二个和第四个索引出现，因此第四个索引被删除。

**处理方式:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/) **+** [**集()**](https://www.geeksforgeeks.org/python-set-method/) **+** [**链. from _ iterable()**](https://www.geeksforgeeks.org/python-itertools-chain-from_iterable/)**+**[T21】生成器](https://www.geeksforgeeks.org/generators-in-python/) **+循环**

在这种情况下，作为第一步，使用生成器函数和集合()提取重复元素的索引。第二步，矩阵重构时，排除所有需要的列。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Remove Columns of Duplicate Elements
# Using list comprehension + set() + 
# chain.from_iterable() + generator + loop
from itertools import chain

def dup_idx(sub):

    memo = set()
    for idx, ele in enumerate(sub):

        # adding element if not there
        if ele not in memo:
            memo.add(ele)
        else:

            # return index is Duplicate
            yield idx

# initializing list
test_list = [[4, 3, 5, 2, 3], [6, 4, 2, 1, 1],
             [4, 3, 9, 3, 9], [5, 4, 3, 2, 1]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 3

# passing each row to generator function
# flattening indices at end
temp_idxs = set(chain.from_iterable(dup_idx(sub) for sub in test_list))

# extracting columns with only non-duplicate indices values
res = [[ele for idx, ele in enumerate(
    sub) if idx not in temp_idxs] for sub in test_list]

# printing result
print("The filtered Matrix : " + str(res))
```

**输出:**

> 原始列表为:[[4，3，5，2，3]，[6，4，2，1，1]，[4，3，9，3，9]，[5，4，3，2，1]]
> 过滤后的矩阵:[[4，3，5]，[6，4，2]，[4，3，9]，[5，4，3]]