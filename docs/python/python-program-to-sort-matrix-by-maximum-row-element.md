# Python 程序按最大行元素排序矩阵

> 原文:[https://www . geesforgeks . org/python-程序-按最大行元素对矩阵进行排序/](https://www.geeksforgeeks.org/python-program-to-sort-matrix-by-maximum-row-element/)

给定矩阵，按最大元素对行进行排序。

> **输入** : test_list = [[5，7，8]，[9，10，3]，
> [10，18，3]，[0，3，5]]
> **输出** : [[10，18，3]，[9，10，3]，[5，7，8]，[0，3，5]]
> **解释** : 18，10，8 和 5 是行中的最大元素，因此排序。
> **输入** : test_list = [[9，10，3]，
> [10，18，3]，[0，3，5]]
> **输出** : [[10，18，3]，[9，10，3]，[0，3，5]]
> **解释** : 18，10，5 为最大行数元素，因此排序。

**方法#1:使用 sort() + max()**

在本例中，我们使用 sort()执行排序任务，键是每行的最大元素。reverse 关键字用于排序，方法是将最大元素行保持在起始位置，并从该位置开始递减。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sort Matrix by Maximum Row element
# Using sort() + max()

def max_sort(row):
    return max(row)

# initializing list
test_list = [[5, 7, 8], [9, 10, 3],
             [10, 18, 3], [0, 3, 5]]

# printing original list
print("The original list is : " + str(test_list))

# sort() for sorting, max to get maximum values
test_list.sort(key = max_sort, reverse = True)

# printing result 
print("The maximum sorted Matrix : " + str(test_list))
```

**输出:**

> 原始列表为:[[5，7，8]，[9，10，3]，[10，18，3]，[0，3，5]]
> 最大排序矩阵:[[10，18，3]，[9，10，3]，[5，7，8]，[0，3，5]]

**方法 2:使用排序的()+λ+max()**

在本例中，我们使用 sorted()对非就地排序执行排序任务，使用 lambda 函数代替外部函数来包含行逻辑中的最大元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sort Matrix by Maximum Row element
# Using sorted() + lambda + max()

# initializing list
test_list = [[5, 7, 8], [9, 10, 3],
             [10, 18, 3], [0, 3, 5]]

# printing original list
print("The original list is : " + str(test_list))

# sorted() for sorting, max to get maximum values
# reverse for reversed order
res = sorted(test_list, key = lambda row : max(row), reverse=True)

# printing result 
print("The maximum sorted Matrix : " + str(res))
```

**输出:**

> 原始列表为:[[5，7，8]，[9，10，3]，[10，18，3]，[0，3，5]]
> 最大排序矩阵:[[10，18，3]，[9，10，3]，[5，7，8]，[0，3，5]]