# Python–根据元素数量大于前一个元素的数量对矩阵进行排序

> 原文:[https://www . geesforgeks . org/python-按元素数量排序矩阵-大于其前一个元素/](https://www.geeksforgeeks.org/python-sort-matrix-by-number-of-elements-greater-than-its-previous-element/)

给定一个矩阵，按下一个元素大于当前元素的出现次数排序。计算每个列表中 i < i + 1 的计数，根据每行中每个条件的计数对每行进行排序。

> **输入** : test_list = [[4，6，2，9，10]，[5，3，2，5]，[2，4，5，6，7，7]，[6，3，2]]
> **输出** : [[6，3，2]，[5，3，2，5]，[4，6，2，9，10]，[2，4，5，6，7]]
> **解释**:为[4，5As，0 < 1 < 3 < 4 所以行的顺序是[6，3，2]，[5，3，2，5]，[4，6，2，9，10]，[2，4，5，6，7，7]
> 
> **输入** : test_list = [[5，3，2，5]，[2，4，5，6，7，7]，[6，3，2]]
> **输出** : [[6，3，2]，[5，3，2，5]，[2，4，5，6，7，7]]
> **解释** : 0 < 1 < 4，是越大的下一个元素计数越大。第一个列表中没有更大的下一个元素。

**方法#1:使用 sort() + len()**

在这种情况下，我们使用 *sort()* 执行排序任务，并调用外部函数作为解决下一个元素更大的元素计数问题的关键。使用*透镜()*计算尺寸。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort Matrix by Next Greater Frequency
# Using sort() + len()

# getting frequency of next greater
def get_greater_freq(row):

    # getting length
    return len([row[idx] for idx in range(0, len(row) - 1) if row[idx] < row[idx + 1]])

# initializing list
test_list = [[4, 6, 2, 9, 10], [5, 3, 2, 5], [2, 4, 5, 6, 7, 7], [6, 3, 2]]

# printing original list
print("The original list is : " + str(test_list))

# inplace sorting
test_list.sort(key=get_greater_freq)

# printing result
print("Sorted rows : " + str(test_list))
```

**输出:**

> 原始列表为:[[4，6，2，9，10]，[5，3，2，5]，[2，4，5，6，7，7]，[6，3，2]]
> 排序行:[[6，3，2]，[5，3，2，5]，[4，6，2，9，10]，[2，4，5，6，7，7]]

**方法 2:使用排序的()+ len() + lambda**

在这种情况下，我们使用 *sorted()执行排序任务，λ*和 *len()* 用于创建单行功能，以基于大于其先前元素的元素数量来执行排序。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort Matrix by Next Greater Frequency
# Using sorted() + len() + lambda

# initializing list
test_list = [[4, 6, 2, 9, 10], [5, 3, 2, 5], [2, 4, 5, 6, 7, 7], [6, 3, 2]]

# printing original list
print("The original list is : " + str(test_list))

# performing one-liner sorting
# avoiding external fnc. call
res = sorted(test_list, key=lambda row: len(
    [row[idx] for idx in range(0, len(row) - 1) if row[idx] < row[idx + 1]]))

# printing result
print("Sorted rows : " + str(res))
```

**输出:**

> 原始列表为:[[4，6，2，9，10]，[5，3，2，5]，[2，4，5，6，7，7]，[6，3，2]]
> 排序行:[[6，3，2]，[5，3，2，5]，[4，6，2，9，10]，[2，4，5，6，7，7]]